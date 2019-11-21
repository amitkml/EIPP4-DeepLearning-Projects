## Aim
Aim of this excercise is to follow methodical approach to finetune the network.

##Training log
Train on 60000 samples, validate on 10000 samples
Epoch 1/20

Epoch 00001: LearningRateScheduler setting learning rate to 0.003.
60000/60000 [==============================] - 17s 279us/step - loss: 0.4985 - acc: 0.8625 - val_loss: 0.1003 - val_acc: 0.9831
Epoch 2/20

Epoch 00002: LearningRateScheduler setting learning rate to 0.0022744503.
60000/60000 [==============================] - 11s 188us/step - loss: 0.2401 - acc: 0.9298 - val_loss: 0.0564 - val_acc: 0.9881
Epoch 3/20

Epoch 00003: LearningRateScheduler setting learning rate to 0.0018315018.
60000/60000 [==============================] - 11s 187us/step - loss: 0.1926 - acc: 0.9415 - val_loss: 0.0522 - val_acc: 0.9885
Epoch 4/20

Epoch 00004: LearningRateScheduler setting learning rate to 0.0015329586.
60000/60000 [==============================] - 11s 188us/step - loss: 0.1654 - acc: 0.9482 - val_loss: 0.0316 - val_acc: 0.9931
Epoch 5/20

Epoch 00005: LearningRateScheduler setting learning rate to 0.0013181019.
60000/60000 [==============================] - 11s 187us/step - loss: 0.1463 - acc: 0.9523 - val_loss: 0.0289 - val_acc: 0.9933
Epoch 6/20

Epoch 00006: LearningRateScheduler setting learning rate to 0.0011560694.
60000/60000 [==============================] - 11s 188us/step - loss: 0.1352 - acc: 0.9528 - val_loss: 0.0270 - val_acc: 0.9934
Epoch 7/20

Epoch 00007: LearningRateScheduler setting learning rate to 0.0010295127.
60000/60000 [==============================] - 11s 188us/step - loss: 0.1260 - acc: 0.9542 - val_loss: 0.0250 - val_acc: 0.9932
Epoch 8/20

Epoch 00008: LearningRateScheduler setting learning rate to 0.0009279307.
60000/60000 [==============================] - 11s 188us/step - loss: 0.1198 - acc: 0.9547 - val_loss: 0.0266 - val_acc: 0.9933
Epoch 9/20

Epoch 00009: LearningRateScheduler setting learning rate to 0.0008445946.
60000/60000 [==============================] - 11s 187us/step - loss: 0.1104 - acc: 0.9576 - val_loss: 0.0211 - val_acc: 0.9941
Epoch 10/20

Epoch 00010: LearningRateScheduler setting learning rate to 0.0007749935.
60000/60000 [==============================] - 11s 188us/step - loss: 0.1079 - acc: 0.9569 - val_loss: 0.0214 - val_acc: 0.9933
Epoch 11/20

Epoch 00011: LearningRateScheduler setting learning rate to 0.0007159905.
60000/60000 [==============================] - 11s 189us/step - loss: 0.1055 - acc: 0.9566 - val_loss: 0.0227 - val_acc: 0.9932
Epoch 12/20

Epoch 00012: LearningRateScheduler setting learning rate to 0.000665336.
60000/60000 [==============================] - 11s 188us/step - loss: 0.1029 - acc: 0.9566 - val_loss: 0.0229 - val_acc: 0.9937
Epoch 13/20

Epoch 00013: LearningRateScheduler setting learning rate to 0.0006213753.
60000/60000 [==============================] - 11s 188us/step - loss: 0.0987 - acc: 0.9576 - val_loss: 0.0249 - val_acc: 0.9933
Epoch 14/20

Epoch 00014: LearningRateScheduler setting learning rate to 0.0005828638.
60000/60000 [==============================] - 11s 188us/step - loss: 0.0976 - acc: 0.9585 - val_loss: 0.0245 - val_acc: 0.9928
Epoch 15/20

Epoch 00015: LearningRateScheduler setting learning rate to 0.0005488474.
60000/60000 [==============================] - 11s 187us/step - loss: 0.0975 - acc: 0.9571 - val_loss: 0.0196 - val_acc: 0.9940
Epoch 16/20

Epoch 00016: LearningRateScheduler setting learning rate to 0.0005185825.
60000/60000 [==============================] - 11s 187us/step - loss: 0.0948 - acc: 0.9577 - val_loss: 0.0195 - val_acc: 0.9946
Epoch 17/20

Epoch 00017: LearningRateScheduler setting learning rate to 0.000491481.
60000/60000 [==============================] - 11s 188us/step - loss: 0.0933 - acc: 0.9583 - val_loss: 0.0195 - val_acc: 0.9946
Epoch 18/20

Epoch 00018: LearningRateScheduler setting learning rate to 0.0004670715.
60000/60000 [==============================] - 11s 189us/step - loss: 0.0906 - acc: 0.9595 - val_loss: 0.0184 - val_acc: 0.9950
Epoch 19/20

Epoch 00019: LearningRateScheduler setting learning rate to 0.0004449718.
60000/60000 [==============================] - 11s 187us/step - loss: 0.0920 - acc: 0.9577 - val_loss: 0.0182 - val_acc: 0.9956
Epoch 20/20

Epoch 00020: LearningRateScheduler setting learning rate to 0.000424869.
60000/60000 [==============================] - 11s 187us/step - loss: 0.0889 - acc: 0.9584 - val_loss: 0.0184 - val_acc: 0.9949

<keras.callbacks.History at 0x7fea78fa3390>

## Model Score on Test Data
[0.01836149591547437, 0.9949]

## Strategy Taken for Network Improvement
- Added Image AUgmentation method with horizontal shift and verticial shift as True
datagen = ImageDataGenerator(horizontal_flip=True, vertical_flip=True)
