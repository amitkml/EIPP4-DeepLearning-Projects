## Aim of this Project

Use Resnet Model architecture for cifar10 and achieve atleast 88% accuracy within 50 epoch

## Strategy Taken for Model Finetunement
- Changed Stride value of 2 to 1
- Added Image augmentation of Flip with probability of 0.5
- Added Cyclic Learning Rate
- Have changed the optimiser from Adap to SGD
- Have used momentum and weight decay

## Key Achievements
- Achieved accuracy of 93.23% accuracy within 50 epocj
- Have used own github module for generating confusion matrix and gradcam

## Model Logs

    Class: <clr.OneCycleLR object at 0x7f57c1f04588>
    Values: {'validation_data': None, 'model': <keras.engine.training.Model object at 0x7f5819d2a898>, 'initial_lr': 0.31, 'end_percentage': 0.1, 'scale': 0.1, 'max_momentum': 0.9, 'min_momentum': 0.85, 'verbose': True, '_update_momentum': True, 'clr_iterations': 0.0, 'history': {}, 'epochs': None, 'batch_size': 128, 'samples': 50000, 'steps': None, 'num_iterations': None, 'mid_cycle_id': None, 'params': {'epochs': 50, 'steps': 391, 'verbose': 1, 'do_validation': True, 'metrics': ['loss', 'acc', 'val_loss', 'val_acc']}}
    Epoch 1/50
    391/391 [==============================] - 149s 381ms/step - loss: 2.7947 - acc: 0.4154 - val_loss: 3.1158 - val_acc: 0.3993
     - lr: 0.04314 - momentum: 0.90 

    Epoch 00001: val_acc improved from -inf to 0.39930, saving model to /content/saved_models/cifar10_ResNet29v2_model.h5
    Epoch 2/50
    391/391 [==============================] - 137s 351ms/step - loss: 2.3764 - acc: 0.5525 - val_loss: 2.5099 - val_acc: 0.5418
     - lr: 0.05531 - momentum: 0.90 

    Epoch 00002: val_acc improved from 0.39930 to 0.54180, saving model to /content/saved_models/cifar10_ResNet29v2_model.h5
    Epoch 3/50
    391/391 [==============================] - 137s 349ms/step - loss: 2.0933 - acc: 0.6298 - val_loss: 2.1959 - val_acc: 0.6158
     - lr: 0.06748 - momentum: 0.89 

    Epoch 00003: val_acc improved from 0.54180 to 0.61580, saving model to /content/saved_models/cifar10_ResNet29v2_model.h5
    Epoch 4/50
    391/391 [==============================] - 136s 348ms/step - loss: 1.8718 - acc: 0.6842 - val_loss: 2.0484 - val_acc: 0.6185
     - lr: 0.07965 - momentum: 0.89 

    Epoch 00004: val_acc improved from 0.61580 to 0.61850, saving model to /content/saved_models/cifar10_ResNet29v2_model.h5
    Epoch 5/50
    391/391 [==============================] - 136s 347ms/step - loss: 1.6656 - acc: 0.7341 - val_loss: 1.8223 - val_acc: 0.6971
     - lr: 0.09182 - momentum: 0.89 

    Epoch 00005: val_acc improved from 0.61850 to 0.69710, saving model to /content/saved_models/cifar10_ResNet29v2_model.h5
    Epoch 6/50
    391/391 [==============================] - 135s 346ms/step - loss: 1.5128 - acc: 0.7641 - val_loss: 1.6501 - val_acc: 0.7195
     - lr: 0.10399 - momentum: 0.89 

    Epoch 00006: val_acc improved from 0.69710 to 0.71950, saving model to /content/saved_models/cifar10_ResNet29v2_model.h5
    Epoch 7/50
    391/391 [==============================] - 136s 347ms/step - loss: 1.3812 - acc: 0.7866 - val_loss: 1.5483 - val_acc: 0.7241
     - lr: 0.11616 - momentum: 0.88 

    Epoch 00007: val_acc improved from 0.71950 to 0.72410, saving model to /content/saved_models/cifar10_ResNet29v2_model.h5
    Epoch 8/50
    391/391 [==============================] - 136s 347ms/step - loss: 1.2753 - acc: 0.8022 - val_loss: 2.0027 - val_acc: 0.6312
     - lr: 0.12833 - momentum: 0.88 

    Epoch 00008: val_acc did not improve from 0.72410
    Epoch 9/50
    391/391 [==============================] - 136s 348ms/step - loss: 1.1854 - acc: 0.8144 - val_loss: 1.3997 - val_acc: 0.7690
     - lr: 0.14050 - momentum: 0.88 

    Epoch 00009: val_acc improved from 0.72410 to 0.76900, saving model to /content/saved_models/cifar10_ResNet29v2_model.h5
    Epoch 10/50
    391/391 [==============================] - 136s 348ms/step - loss: 1.0978 - acc: 0.8272 - val_loss: 1.5095 - val_acc: 0.7212
     - lr: 0.15267 - momentum: 0.88 

    Epoch 00010: val_acc did not improve from 0.76900
    Epoch 11/50
    391/391 [==============================] - 135s 346ms/step - loss: 1.0336 - acc: 0.8324 - val_loss: 1.3036 - val_acc: 0.7531
     - lr: 0.16484 - momentum: 0.88 

    Epoch 00011: val_acc did not improve from 0.76900
    Epoch 12/50
    391/391 [==============================] - 135s 345ms/step - loss: 0.9697 - acc: 0.8413 - val_loss: 1.4400 - val_acc: 0.7219
     - lr: 0.17701 - momentum: 0.87 

    Epoch 00012: val_acc did not improve from 0.76900
    Epoch 13/50
    391/391 [==============================] - 135s 346ms/step - loss: 0.9230 - acc: 0.8451 - val_loss: 1.2057 - val_acc: 0.7608
     - lr: 0.18917 - momentum: 0.87 

    Epoch 00013: val_acc did not improve from 0.76900
    Epoch 14/50
    391/391 [==============================] - 137s 351ms/step - loss: 0.8730 - acc: 0.8518 - val_loss: 1.0910 - val_acc: 0.7848
     - lr: 0.20134 - momentum: 0.87 

    Epoch 00014: val_acc improved from 0.76900 to 0.78480, saving model to /content/saved_models/cifar10_ResNet29v2_model.h5
    Epoch 15/50
    391/391 [==============================] - 135s 345ms/step - loss: 0.8278 - acc: 0.8567 - val_loss: 1.3804 - val_acc: 0.6946
     - lr: 0.21351 - momentum: 0.87 

    Epoch 00015: val_acc did not improve from 0.78480
    Epoch 16/50
    391/391 [==============================] - 135s 345ms/step - loss: 0.8002 - acc: 0.8602 - val_loss: 1.4626 - val_acc: 0.6901
     - lr: 0.22568 - momentum: 0.87 

    Epoch 00016: val_acc did not improve from 0.78480
    Epoch 17/50
    391/391 [==============================] - 135s 344ms/step - loss: 0.7766 - acc: 0.8630 - val_loss: 1.1072 - val_acc: 0.7756
     - lr: 0.23785 - momentum: 0.86 

    Epoch 00017: val_acc did not improve from 0.78480
    Epoch 18/50
    391/391 [==============================] - 135s 344ms/step - loss: 0.7493 - acc: 0.8634 - val_loss: 0.9556 - val_acc: 0.7972
     - lr: 0.25002 - momentum: 0.86 

    Epoch 00018: val_acc improved from 0.78480 to 0.79720, saving model to /content/saved_models/cifar10_ResNet29v2_model.h5
    Epoch 19/50
    391/391 [==============================] - 135s 345ms/step - loss: 0.7271 - acc: 0.8706 - val_loss: 1.1685 - val_acc: 0.7394
     - lr: 0.26219 - momentum: 0.86 

    Epoch 00019: val_acc did not improve from 0.79720
    Epoch 20/50
    391/391 [==============================] - 135s 346ms/step - loss: 0.7113 - acc: 0.8708 - val_loss: 1.3775 - val_acc: 0.7264
     - lr: 0.27436 - momentum: 0.86 

    Epoch 00020: val_acc did not improve from 0.79720
    Epoch 21/50
    391/391 [==============================] - 135s 345ms/step - loss: 0.6922 - acc: 0.8735 - val_loss: 0.9525 - val_acc: 0.7931
     - lr: 0.28653 - momentum: 0.85 

    Epoch 00021: val_acc did not improve from 0.79720
    Epoch 22/50
    391/391 [==============================] - 135s 345ms/step - loss: 0.6799 - acc: 0.8749 - val_loss: 0.9165 - val_acc: 0.8030
     - lr: 0.29870 - momentum: 0.85 

    Epoch 00022: val_acc improved from 0.79720 to 0.80300, saving model to /content/saved_models/cifar10_ResNet29v2_model.h5
    Epoch 23/50
    391/391 [==============================] - 135s 346ms/step - loss: 0.6649 - acc: 0.8784 - val_loss: 0.7980 - val_acc: 0.8364
     - lr: 0.30913 - momentum: 0.85 

    Epoch 00023: val_acc improved from 0.80300 to 0.83640, saving model to /content/saved_models/cifar10_ResNet29v2_model.h5
    Epoch 24/50
    391/391 [==============================] - 135s 345ms/step - loss: 0.6487 - acc: 0.8815 - val_loss: 0.8091 - val_acc: 0.8305
     - lr: 0.29696 - momentum: 0.85 

    Epoch 00024: val_acc did not improve from 0.83640
    Epoch 25/50
    391/391 [==============================] - 135s 345ms/step - loss: 0.6290 - acc: 0.8873 - val_loss: 0.8032 - val_acc: 0.8330
     - lr: 0.28479 - momentum: 0.85 

    Epoch 00025: val_acc did not improve from 0.83640
    Epoch 26/50
    391/391 [==============================] - 135s 345ms/step - loss: 0.6095 - acc: 0.8922 - val_loss: 0.8862 - val_acc: 0.8169
     - lr: 0.27262 - momentum: 0.86 

    Epoch 00026: val_acc did not improve from 0.83640
    Epoch 27/50
    391/391 [==============================] - 135s 344ms/step - loss: 0.5893 - acc: 0.8965 - val_loss: 0.7594 - val_acc: 0.8422
     - lr: 0.26045 - momentum: 0.86 

    Epoch 00027: val_acc improved from 0.83640 to 0.84220, saving model to /content/saved_models/cifar10_ResNet29v2_model.h5
    Epoch 28/50
    391/391 [==============================] - 135s 344ms/step - loss: 0.5650 - acc: 0.9023 - val_loss: 0.8143 - val_acc: 0.8267
     - lr: 0.24828 - momentum: 0.86 

    Epoch 00028: val_acc did not improve from 0.84220
    Epoch 29/50
    391/391 [==============================] - 135s 344ms/step - loss: 0.5523 - acc: 0.9064 - val_loss: 1.2205 - val_acc: 0.7269
     - lr: 0.23611 - momentum: 0.86 

    Epoch 00029: val_acc did not improve from 0.84220
    Epoch 30/50
    391/391 [==============================] - 135s 345ms/step - loss: 0.5371 - acc: 0.9085 - val_loss: 0.7760 - val_acc: 0.8428
     - lr: 0.22394 - momentum: 0.87 

    Epoch 00030: val_acc improved from 0.84220 to 0.84280, saving model to /content/saved_models/cifar10_ResNet29v2_model.h5
    Epoch 31/50
    391/391 [==============================] - 136s 347ms/step - loss: 0.5186 - acc: 0.9135 - val_loss: 0.8730 - val_acc: 0.8145
     - lr: 0.21177 - momentum: 0.87 

    Epoch 00031: val_acc did not improve from 0.84280
    Epoch 32/50
    391/391 [==============================] - 138s 352ms/step - loss: 0.5004 - acc: 0.9171 - val_loss: 0.8325 - val_acc: 0.8236
     - lr: 0.19960 - momentum: 0.87 

    Epoch 00032: val_acc did not improve from 0.84280
    Epoch 33/50
    391/391 [==============================] - 135s 344ms/step - loss: 0.4834 - acc: 0.9224 - val_loss: 0.7254 - val_acc: 0.8514
     - lr: 0.18743 - momentum: 0.87 

    Epoch 00033: val_acc improved from 0.84280 to 0.85140, saving model to /content/saved_models/cifar10_ResNet29v2_model.h5
    Epoch 34/50
    391/391 [==============================] - 135s 346ms/step - loss: 0.4689 - acc: 0.9265 - val_loss: 0.6113 - val_acc: 0.8868
     - lr: 0.17526 - momentum: 0.87 

    Epoch 00034: val_acc improved from 0.85140 to 0.88680, saving model to /content/saved_models/cifar10_ResNet29v2_model.h5
    Epoch 35/50
    391/391 [==============================] - 135s 346ms/step - loss: 0.4489 - acc: 0.9317 - val_loss: 0.7521 - val_acc: 0.8519
     - lr: 0.16309 - momentum: 0.88 

    Epoch 00035: val_acc did not improve from 0.88680
    Epoch 36/50
    391/391 [==============================] - 138s 352ms/step - loss: 0.4365 - acc: 0.9327 - val_loss: 0.6789 - val_acc: 0.8657
     - lr: 0.15092 - momentum: 0.88 

    Epoch 00036: val_acc did not improve from 0.88680
    Epoch 37/50
    391/391 [==============================] - 135s 345ms/step - loss: 0.4198 - acc: 0.9381 - val_loss: 0.6290 - val_acc: 0.8709
     - lr: 0.13875 - momentum: 0.88 

    Epoch 00037: val_acc did not improve from 0.88680
    Epoch 38/50
    391/391 [==============================] - 135s 345ms/step - loss: 0.3961 - acc: 0.9448 - val_loss: 0.6846 - val_acc: 0.8701
     - lr: 0.12658 - momentum: 0.88 

    Epoch 00038: val_acc did not improve from 0.88680
    Epoch 39/50
    391/391 [==============================] - 134s 343ms/step - loss: 0.3809 - acc: 0.9486 - val_loss: 0.5465 - val_acc: 0.9031
     - lr: 0.11441 - momentum: 0.89 

    Epoch 00039: val_acc improved from 0.88680 to 0.90310, saving model to /content/saved_models/cifar10_ResNet29v2_model.h5
    Epoch 40/50
    391/391 [==============================] - 134s 342ms/step - loss: 0.3678 - acc: 0.9518 - val_loss: 0.6767 - val_acc: 0.8703
     - lr: 0.10224 - momentum: 0.89 

    Epoch 00040: val_acc did not improve from 0.90310
    Epoch 41/50
    391/391 [==============================] - 134s 342ms/step - loss: 0.3480 - acc: 0.9578 - val_loss: 0.6224 - val_acc: 0.8834
     - lr: 0.09007 - momentum: 0.89 

    Epoch 00041: val_acc did not improve from 0.90310
    Epoch 42/50
    391/391 [==============================] - 134s 342ms/step - loss: 0.3270 - acc: 0.9626 - val_loss: 0.5396 - val_acc: 0.9027
     - lr: 0.07790 - momentum: 0.89 

    Epoch 00042: val_acc did not improve from 0.90310
    Epoch 43/50
    391/391 [==============================] - 138s 353ms/step - loss: 0.3105 - acc: 0.9668 - val_loss: 0.5326 - val_acc: 0.9084
     - lr: 0.06573 - momentum: 0.89 

    Epoch 00043: val_acc improved from 0.90310 to 0.90840, saving model to /content/saved_models/cifar10_ResNet29v2_model.h5
    Epoch 44/50
    391/391 [==============================] - 135s 346ms/step - loss: 0.2852 - acc: 0.9748 - val_loss: 0.5082 - val_acc: 0.9124
     - lr: 0.05357 - momentum: 0.90 

    Epoch 00044: val_acc improved from 0.90840 to 0.91240, saving model to /content/saved_models/cifar10_ResNet29v2_model.h5
    Epoch 45/50
    391/391 [==============================] - 138s 352ms/step - loss: 0.2701 - acc: 0.9784 - val_loss: 0.4583 - val_acc: 0.9216
     - lr: 0.04140 - momentum: 0.90 

    Epoch 00045: val_acc improved from 0.91240 to 0.92160, saving model to /content/saved_models/cifar10_ResNet29v2_model.h5
    Epoch 46/50
    391/391 [==============================] - 137s 351ms/step - loss: 0.2521 - acc: 0.9841 - val_loss: 0.4662 - val_acc: 0.9246
     - lr: 0.03012 - momentum: 0.90 

    Epoch 00046: val_acc improved from 0.92160 to 0.92460, saving model to /content/saved_models/cifar10_ResNet29v2_model.h5
    Epoch 47/50
    391/391 [==============================] - 135s 345ms/step - loss: 0.2390 - acc: 0.9886 - val_loss: 0.4706 - val_acc: 0.9230
     - lr: 0.02410 - momentum: 0.90 

    Epoch 00047: val_acc did not improve from 0.92460
    Epoch 48/50
    391/391 [==============================] - 135s 345ms/step - loss: 0.2310 - acc: 0.9901 - val_loss: 0.4352 - val_acc: 0.9305
     - lr: 0.01808 - momentum: 0.90 

    Epoch 00048: val_acc improved from 0.92460 to 0.93050, saving model to /content/saved_models/cifar10_ResNet29v2_model.h5
    Epoch 49/50
    391/391 [==============================] - 135s 346ms/step - loss: 0.2253 - acc: 0.9914 - val_loss: 0.4369 - val_acc: 0.9304
     - lr: 0.01206 - momentum: 0.90 

    Epoch 00049: val_acc did not improve from 0.93050
    Epoch 50/50
    391/391 [==============================] - 135s 345ms/step - loss: 0.2194 - acc: 0.9931 - val_loss: 0.4383 - val_acc: 0.9323
     - lr: 0.00604 - momentum: 0.90 

    Epoch 00050: val_acc improved from 0.93050 to 0.93230, saving model to /content/saved_models/cifar10_ResNet29v2_model.h5

    <keras.callbacks.History at 0x7f57c1f1e160>


