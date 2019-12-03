# Assignment 3

This assignment involved training a model with less than 100,000 parameters without using dense layers to beat the accuracy of a reference model(~82%).



## Highlights

- Kernel level regularization is used for every layer. As mentioned by [Cortes et al.](https://arxiv.org/ftp/arxiv/papers/1205/1205.2653.pdf) in their paper ***L2 Regularization for Learning Kernels***, L2 regularization is used. (Just took inspiration on which method to use **without** reading the full paper).
- Noticed that the model trained well when run for about 100 epochs. Hence needed something to fasten up the learning process. Hence used Super-Convergence as mentioned by [Leslie N. Smith](https://arxiv.org/abs/1708.07120) in their paper **Super-Convergence: Very Fast Training of Neural Networks Using Large Learning Rates**.
- Used **AveragePooling2D** instead of MaxPooling2D and got better results.
- Used **SGD with momentum** for better performance.
- The total number of parameters used in the model is **91,909** which is 91.9% of total number of parameters.
- Model has achieved **88.27% validation accuracy** as compared to 82.10 for the reference model.

## Model Definition   
`weight_decay = 3e-3

model_new = Sequential()
model_new.add(SeparableConv2D(32, (3,3), padding='same', kernel_regularizer=regularizers.l2(weight_decay), input_shape=(32, 32, 3)))#O = 32 , R = 3
model_new.add(Activation('relu'))
model_new.add(BatchNormalization())
model_new.add(SeparableConv2D(64, (3,3), padding='same', kernel_regularizer=regularizers.l2(weight_decay)))#O = 32 , R = 5
model_new.add(Activation('relu'))
model_new.add(BatchNormalization())
model_new.add(SeparableConv2D(128, (3,3), kernel_regularizer=regularizers.l2(weight_decay)))#O = 30 , R = 7
model_new.add(Activation('relu'))
model_new.add(BatchNormalization())
model_new.add(SeparableConv2D(128, (3,3), kernel_regularizer=regularizers.l2(weight_decay)))#O = 30 , R = 9
model_new.add(Activation('relu'))
model_new.add(BatchNormalization())
model_new.add(AveragePooling2D())#O = 15 , R = 10
model_new.add(Dropout(0.1))

model_new.add(SeparableConv2D(32,1,1,kernel_regularizer=regularizers.l2(weight_decay)))#O = 15 , R = 10

model_new.add(SeparableConv2D(32, (3,3), padding='same', kernel_regularizer=regularizers.l2(weight_decay)))#O = 15 , R = 14
model_new.add(Activation('relu'))
model_new.add(BatchNormalization())
model_new.add(SeparableConv2D(64, (3,3), padding='same', kernel_regularizer=regularizers.l2(weight_decay)))#O = 15 , R = 18
model_new.add(Activation('relu'))
model_new.add(BatchNormalization())
model_new.add(SeparableConv2D(128, (3,3), padding='same', kernel_regularizer=regularizers.l2(weight_decay)))#O = 15 , R = 22
model_new.add(Activation('relu'))
model_new.add(BatchNormalization())
model_new.add(SeparableConv2D(128, (3,3), padding='same', kernel_regularizer=regularizers.l2(weight_decay)))#O = 15 , R = 26
model_new.add(Activation('relu'))
model_new.add(BatchNormalization())
model_new.add(AveragePooling2D())#O = 7 , R = 28
model_new.add(Dropout(0.3))

model_new.add(SeparableConv2D(32,1,1,kernel_regularizer=regularizers.l2(weight_decay)))#O = 7 , R = 28

model_new.add(SeparableConv2D(32, (3,3), padding='same', kernel_regularizer=regularizers.l2(weight_decay)))#O = 7 , R = 36
model_new.add(Activation('relu'))
model_new.add(BatchNormalization())
model_new.add(SeparableConv2D(64, (3,3), padding='same', kernel_regularizer=regularizers.l2(weight_decay)))#O = 7 , R = 44
model_new.add(Activation('relu'))
model_new.add(BatchNormalization())
model_new.add(SeparableConv2D(128, (3,3), padding='same', kernel_regularizer=regularizers.l2(weight_decay)))#O = 7 , R = 52
model_new.add(Activation('relu'))
model_new.add(BatchNormalization())
'# model_new.add(SeparableConv2D(128, (3,3), padding='same', kernel_regularizer=regularizers.l2(weight_decay)))#7
'# model_new.add(Activation('relu'))
'# model_new.add(BatchNormalization())
model_new.add(AveragePooling2D())#O = 3 , R = 56
model_new.add(Dropout(0.4))

model_new.add(SeparableConv2D(32,1,1,kernel_regularizer=regularizers.l2(weight_decay)))#O = 3 , R = 56


model_new.add(SeparableConv2D(64, (3,3), kernel_regularizer=regularizers.l2(weight_decay)))#O = 1 , R = 72
model_new.add(Activation('relu'))
model_new.add(BatchNormalization())


model_new.add(SeparableConv2D(10, 1,1,kernel_regularizer=regularizers.l2(weight_decay)))
 
model_new.add(GlobalAveragePooling2D())
model_new.add(Activation('softmax'))


model_new.compile(loss='categorical_crossentropy', optimizer=SGD(momentum=0.95), metrics=['accuracy'])`

   
## Epoch logs

Epoch 1/50
(0.009999999776482582, 0.1)

Epoch 00001: LearningRateScheduler setting learning rate to 0.1.
97/97 [==============================] - 60s 619ms/step - loss: 1.8790 - acc: 0.2920 - val_loss: 13.5606 - val_acc: 0.1418
Epoch 2/50
(0.10000000149011612, 0.16086956521739126)

Epoch 00002: LearningRateScheduler setting learning rate to 0.16086956521739126.
97/97 [==============================] - 54s 552ms/step - loss: 1.5712 - acc: 0.4181 - val_loss: 11.1686 - val_acc: 0.2135
Epoch 3/50
(0.1608695685863495, 0.22173913043478252)

Epoch 00003: LearningRateScheduler setting learning rate to 0.22173913043478252.
97/97 [==============================] - 54s 556ms/step - loss: 1.4197 - acc: 0.4800 - val_loss: 10.3449 - val_acc: 0.2689
Epoch 4/50
(0.22173912823200226, 0.2826086956521738)

Epoch 00004: LearningRateScheduler setting learning rate to 0.2826086956521738.
97/97 [==============================] - 54s 554ms/step - loss: 1.2888 - acc: 0.5315 - val_loss: 10.9104 - val_acc: 0.2608
Epoch 5/50
(0.28260868787765503, 0.343478260869565)

Epoch 00005: LearningRateScheduler setting learning rate to 0.343478260869565.
97/97 [==============================] - 54s 557ms/step - loss: 1.1796 - acc: 0.5744 - val_loss: 8.6084 - val_acc: 0.3290
Epoch 6/50
(0.343478262424469, 0.40434782608695663)

Epoch 00006: LearningRateScheduler setting learning rate to 0.40434782608695663.
97/97 [==============================] - 54s 554ms/step - loss: 1.1041 - acc: 0.6059 - val_loss: 10.5466 - val_acc: 0.2276
Epoch 7/50
(0.40434783697128296, 0.4652173913043479)

Epoch 00007: LearningRateScheduler setting learning rate to 0.4652173913043479.
97/97 [==============================] - 54s 554ms/step - loss: 1.0410 - acc: 0.6283 - val_loss: 12.1566 - val_acc: 0.1646
Epoch 8/50
(0.46521738171577454, 0.5260869565217391)

Epoch 00008: LearningRateScheduler setting learning rate to 0.5260869565217391.
97/97 [==============================] - 54s 552ms/step - loss: 0.9913 - acc: 0.6470 - val_loss: 10.0089 - val_acc: 0.2634
Epoch 9/50
(0.5260869860649109, 0.5869565217391304)

Epoch 00009: LearningRateScheduler setting learning rate to 0.5869565217391304.
97/97 [==============================] - 54s 554ms/step - loss: 0.9242 - acc: 0.6744 - val_loss: 6.3858 - val_acc: 0.3868
Epoch 10/50
(0.5869565010070801, 0.6478260869565217)

Epoch 00010: LearningRateScheduler setting learning rate to 0.6478260869565217.
97/97 [==============================] - 54s 552ms/step - loss: 0.8719 - acc: 0.6938 - val_loss: 10.2396 - val_acc: 0.2702
Epoch 11/50
(0.647826075553894, 0.7086956521739128)

Epoch 00011: LearningRateScheduler setting learning rate to 0.7086956521739128.
97/97 [==============================] - 54s 556ms/step - loss: 0.8225 - acc: 0.7139 - val_loss: 7.4453 - val_acc: 0.3455
Epoch 12/50
(0.708695650100708, 0.7695652173913041)

Epoch 00012: LearningRateScheduler setting learning rate to 0.7695652173913041.
97/97 [==============================] - 54s 554ms/step - loss: 0.7790 - acc: 0.7288 - val_loss: 9.4468 - val_acc: 0.2345
Epoch 13/50
(0.769565224647522, 0.8304347826086957)

Epoch 00013: LearningRateScheduler setting learning rate to 0.8304347826086957.
97/97 [==============================] - 54s 553ms/step - loss: 0.7610 - acc: 0.7362 - val_loss: 2.9617 - val_acc: 0.5612
Epoch 14/50
(0.8304347991943359, 0.8913043478260867)

Epoch 00014: LearningRateScheduler setting learning rate to 0.8913043478260867.
97/97 [==============================] - 54s 554ms/step - loss: 0.7410 - acc: 0.7448 - val_loss: 5.3020 - val_acc: 0.4029
Epoch 15/50
(0.8913043737411499, 0.9521739130434782)

Epoch 00015: LearningRateScheduler setting learning rate to 0.9521739130434782.
97/97 [==============================] - 54s 554ms/step - loss: 0.7218 - acc: 0.7513 - val_loss: 4.1359 - val_acc: 0.5036
Epoch 16/50
(0.9521738886833191, 1.0130434782608695)

Epoch 00016: LearningRateScheduler setting learning rate to 1.0130434782608695.
97/97 [==============================] - 54s 556ms/step - loss: 0.7148 - acc: 0.7569 - val_loss: 3.8856 - val_acc: 0.5307
Epoch 17/50
(1.0130435228347778, 1.0739130434782609)

Epoch 00017: LearningRateScheduler setting learning rate to 1.0739130434782609.
97/97 [==============================] - 54s 554ms/step - loss: 0.6975 - acc: 0.7617 - val_loss: 4.5252 - val_acc: 0.4394
Epoch 18/50
(1.0739130973815918, 1.134782608695652)

Epoch 00018: LearningRateScheduler setting learning rate to 1.134782608695652.
97/97 [==============================] - 54s 553ms/step - loss: 0.6823 - acc: 0.7678 - val_loss: 2.0533 - val_acc: 0.5778
Epoch 19/50
(1.1347825527191162, 1.1956521739130435)

Epoch 00019: LearningRateScheduler setting learning rate to 1.1956521739130435.
97/97 [==============================] - 54s 554ms/step - loss: 0.6580 - acc: 0.7758 - val_loss: 3.5844 - val_acc: 0.4647
Epoch 20/50
(1.1956521272659302, 1.2565217391304349)

Epoch 00020: LearningRateScheduler setting learning rate to 1.2565217391304349.
97/97 [==============================] - 54s 553ms/step - loss: 0.6453 - acc: 0.7799 - val_loss: 1.4582 - val_acc: 0.6596
Epoch 21/50
(1.2565217018127441, 1.3173913043478258)

Epoch 00021: LearningRateScheduler setting learning rate to 1.3173913043478258.
97/97 [==============================] - 54s 552ms/step - loss: 0.6251 - acc: 0.7868 - val_loss: 2.9243 - val_acc: 0.5536
Epoch 22/50
(1.317391276359558, 1.3782608695652174)

Epoch 00022: LearningRateScheduler setting learning rate to 1.3782608695652174.
97/97 [==============================] - 54s 554ms/step - loss: 0.6197 - acc: 0.7940 - val_loss: 1.7218 - val_acc: 0.6248
Epoch 23/50
(1.378260850906372, 1.4391304347826088)

Epoch 00023: LearningRateScheduler setting learning rate to 1.4391304347826088.
97/97 [==============================] - 54s 555ms/step - loss: 0.6214 - acc: 0.7926 - val_loss: 1.5571 - val_acc: 0.6467
Epoch 24/50
(1.439130425453186, 1.5)

Epoch 00024: LearningRateScheduler setting learning rate to 1.5.
97/97 [==============================] - 53s 551ms/step - loss: 0.6131 - acc: 0.7932 - val_loss: 2.0547 - val_acc: 0.5838
Epoch 25/50
(1.5, 1.4391304347826088)

Epoch 00025: LearningRateScheduler setting learning rate to 1.4391304347826088.
97/97 [==============================] - 54s 561ms/step - loss: 0.6116 - acc: 0.7968 - val_loss: 1.3612 - val_acc: 0.7235
Epoch 26/50
(1.439130425453186, 1.3782608695652174)

Epoch 00026: LearningRateScheduler setting learning rate to 1.3782608695652174.
97/97 [==============================] - 54s 553ms/step - loss: 0.5603 - acc: 0.8118 - val_loss: 1.2343 - val_acc: 0.6743
Epoch 27/50
(1.378260850906372, 1.3173913043478263)

Epoch 00027: LearningRateScheduler setting learning rate to 1.3173913043478263.
97/97 [==============================] - 54s 557ms/step - loss: 0.5436 - acc: 0.8153 - val_loss: 1.3538 - val_acc: 0.6985
Epoch 28/50
(1.317391276359558, 1.2565217391304346)

Epoch 00028: LearningRateScheduler setting learning rate to 1.2565217391304346.
97/97 [==============================] - 53s 551ms/step - loss: 0.5352 - acc: 0.8211 - val_loss: 0.7412 - val_acc: 0.7860
Epoch 29/50
(1.2565217018127441, 1.1956521739130435)

Epoch 00029: LearningRateScheduler setting learning rate to 1.1956521739130435.
97/97 [==============================] - 54s 553ms/step - loss: 0.5183 - acc: 0.8273 - val_loss: 0.6842 - val_acc: 0.7933
Epoch 30/50
(1.1956521272659302, 1.134782608695652)

Epoch 00030: LearningRateScheduler setting learning rate to 1.134782608695652.
97/97 [==============================] - 54s 555ms/step - loss: 0.4862 - acc: 0.8366 - val_loss: 0.6050 - val_acc: 0.8102
Epoch 31/50
(1.1347825527191162, 1.0739130434782609)

Epoch 00031: LearningRateScheduler setting learning rate to 1.0739130434782609.
97/97 [==============================] - 54s 554ms/step - loss: 0.4687 - acc: 0.8411 - val_loss: 0.8726 - val_acc: 0.7523
Epoch 32/50
(1.0739130973815918, 1.0130434782608695)

Epoch 00032: LearningRateScheduler setting learning rate to 1.0130434782608695.
97/97 [==============================] - 54s 552ms/step - loss: 0.4587 - acc: 0.8454 - val_loss: 0.5635 - val_acc: 0.8350
Epoch 33/50
(1.0130435228347778, 0.9521739130434782)

Epoch 00033: LearningRateScheduler setting learning rate to 0.9521739130434782.
97/97 [==============================] - 54s 556ms/step - loss: 0.4255 - acc: 0.8541 - val_loss: 0.6496 - val_acc: 0.8033
Epoch 34/50
(0.9521738886833191, 0.891304347826087)

Epoch 00034: LearningRateScheduler setting learning rate to 0.891304347826087.
97/97 [==============================] - 54s 554ms/step - loss: 0.4226 - acc: 0.8564 - val_loss: 0.6075 - val_acc: 0.8054
Epoch 35/50
(0.8913043737411499, 0.8304347826086957)

Epoch 00035: LearningRateScheduler setting learning rate to 0.8304347826086957.
97/97 [==============================] - 54s 555ms/step - loss: 0.4101 - acc: 0.8624 - val_loss: 0.5275 - val_acc: 0.8299
Epoch 36/50
(0.8304347991943359, 0.7695652173913041)

Epoch 00036: LearningRateScheduler setting learning rate to 0.7695652173913041.
97/97 [==============================] - 54s 554ms/step - loss: 0.3927 - acc: 0.8649 - val_loss: 0.5061 - val_acc: 0.8427
Epoch 37/50
(0.769565224647522, 0.7086956521739128)

Epoch 00037: LearningRateScheduler setting learning rate to 0.7086956521739128.
97/97 [==============================] - 54s 553ms/step - loss: 0.3931 - acc: 0.8666 - val_loss: 0.5339 - val_acc: 0.8379
Epoch 38/50
(0.708695650100708, 0.6478260869565217)

Epoch 00038: LearningRateScheduler setting learning rate to 0.6478260869565217.
97/97 [==============================] - 53s 550ms/step - loss: 0.3722 - acc: 0.8729 - val_loss: 0.5043 - val_acc: 0.8384
Epoch 39/50
(0.647826075553894, 0.5869565217391304)

Epoch 00039: LearningRateScheduler setting learning rate to 0.5869565217391304.
97/97 [==============================] - 54s 556ms/step - loss: 0.3594 - acc: 0.8765 - val_loss: 0.4786 - val_acc: 0.8458
Epoch 40/50
(0.5869565010070801, 0.5260869565217391)

Epoch 00040: LearningRateScheduler setting learning rate to 0.5260869565217391.
97/97 [==============================] - 54s 554ms/step - loss: 0.3438 - acc: 0.8821 - val_loss: 0.6164 - val_acc: 0.8146
Epoch 41/50
(0.5260869860649109, 0.4652173913043479)

Epoch 00041: LearningRateScheduler setting learning rate to 0.4652173913043479.
97/97 [==============================] - 53s 551ms/step - loss: 0.3345 - acc: 0.8849 - val_loss: 0.4209 - val_acc: 0.8625
Epoch 42/50
(0.46521738171577454, 0.40434782608695663)

Epoch 00042: LearningRateScheduler setting learning rate to 0.40434782608695663.
97/97 [==============================] - 54s 552ms/step - loss: 0.3231 - acc: 0.8888 - val_loss: 0.3947 - val_acc: 0.8710
Epoch 43/50
(0.40434783697128296, 0.34347826086956534)

Epoch 00043: LearningRateScheduler setting learning rate to 0.34347826086956534.
97/97 [==============================] - 54s 554ms/step - loss: 0.3194 - acc: 0.8913 - val_loss: 0.3838 - val_acc: 0.8724
Epoch 44/50
(0.343478262424469, 0.2826086956521738)

Epoch 00044: LearningRateScheduler setting learning rate to 0.2826086956521738.
97/97 [==============================] - 53s 551ms/step - loss: 0.3076 - acc: 0.8932 - val_loss: 0.3959 - val_acc: 0.8717
Epoch 45/50
(0.28260868787765503, 0.22173913043478252)

Epoch 00045: LearningRateScheduler setting learning rate to 0.22173913043478252.
97/97 [==============================] - 54s 556ms/step - loss: 0.2929 - acc: 0.8984 - val_loss: 0.3898 - val_acc: 0.8747
Epoch 46/50
(0.22173912823200226, 0.16086956521739126)

Epoch 00046: LearningRateScheduler setting learning rate to 0.16086956521739126.
97/97 [==============================] - 54s 555ms/step - loss: 0.2925 - acc: 0.8993 - val_loss: 0.3885 - val_acc: 0.8756
Epoch 47/50
(0.1608695685863495, 0.1)

Epoch 00047: LearningRateScheduler setting learning rate to 0.1.
97/97 [==============================] - 54s 555ms/step - loss: 0.2778 - acc: 0.9047 - val_loss: 0.3725 - val_acc: 0.8817
Epoch 48/50
(0.10000000149011612, 0.16086956521739157)

Epoch 00048: LearningRateScheduler setting learning rate to 0.1.
97/97 [==============================] - 54s 554ms/step - loss: 0.2729 - acc: 0.9059 - val_loss: 0.3764 - val_acc: 0.8788
Epoch 49/50
(0.10000000149011612, 0.22173913043478252)

Epoch 00049: LearningRateScheduler setting learning rate to 0.1.
97/97 [==============================] - 53s 550ms/step - loss: 0.2713 - acc: 0.9061 - val_loss: 0.3759 - val_acc: 0.8796
Epoch 50/50
(0.10000000149011612, 0.28260869565217406)

Epoch 00050: LearningRateScheduler setting learning rate to 0.1.
97/97 [==============================] - 54s 553ms/step - loss: 0.2709 - acc: 0.9059 - val_loss: 0.3650 - val_acc: 0.8827   
New Model took 2693.93 seconds to train
