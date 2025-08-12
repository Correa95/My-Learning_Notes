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
