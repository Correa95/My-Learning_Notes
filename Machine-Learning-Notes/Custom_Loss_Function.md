# Custom Loss Function

Huber Class Function

# def huber_fn(y_true, y_pred):

    error = y_true - y_pred
    is_small_error = tf.abs(error) < 1
    squared_loss = tf.square(error) / 2
    linear_loss = tf.abs(error) - 0.5
    return tf.where(is_small_error, squared_loss, linear_loss)
    model.compile(loss=huber_fn,optimizer="nadam")
    model.fit(X_train,y_train)
