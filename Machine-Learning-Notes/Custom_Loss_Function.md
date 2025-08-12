# Custom Loss Function

Huber Class Function

# def huber_fn(y_true, y_pred):

    error = y_true - y_pred
    is_small_error = tf.abs(error) < 1  # condition: small vs large error
    squared_loss = tf.square(error) / 2  # for small errors: quadratic
    linear_loss = tf.abs(error) - 0.5    # for large errors: linear
    return tf.where(is_small_error, squared_loss, linear_loss)
    model.compile(loss=huber_fn,optimizer="nadam")
    model.fit(X_train,y_train)

# ✅ Why it works

    Huber loss blends MSE (Mean Squared Error) and MAE (Mean Absolute Error).
    If the error is small (<1), it uses squared loss (smooth, less sensitive to small noise).
    If the error is large (≥1), it switches to linear loss (less sensitive to outliers).
    tf.where(condition, A, B) chooses between A and B element-wise.

# Huber loss function with a custom threshold.

# def create_huber(threshold=1.0):

    def huber_fn(y_true, y_pred):
        error = y_true - y_pred
        is_small_error = tf.abs(error) < threshold
        squared_loss = tf.square(error) / 2
        linear_loss  = threshold * tf.abs(error) - threshold ** 2 / 2
        return tf.where(is_small_error, squared_loss, linear_loss)
    return huber_fn
    model.compile(loss=create_huber(2.0), optimizer="nadam", metrics=["mae"])

# ✅ Why this is useful

    create_huber returns a loss function tailored to a given threshold without hardcoding it.
    The returned huber_fn can be passed directly into model.compile().

# vectorized version of your Huber loss without tf.where:

# def create_huber(threshold=1.0):

    def huber_fn(y_true, y_pred):
        error = y_true - y_pred
        abs_error = tf.abs(error)
        # min() handles the small-error part, max() handles the large-error part
        quadratic = tf.minimum(abs_error, threshold)
        linear = abs_error - quadratic
        return 0.5 * tf.square(quadratic) + threshold * linear
    return huber_fn

# ✅Why this is faster

    Instead of branching with tf.where (which still computes both sides of the branch),
    this version splits the error into two parts:
    quadratic: the portion clamped at threshold
    linear: the portion above threshold
    Then it calculates:
        0.5 * quadratic² + threshold * linear

which is mathematically equivalent to the classic Huber definition.
