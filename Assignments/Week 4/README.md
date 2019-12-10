# Assignments for Week 4

   

## Assignment 4A

This assignment was to annotate 100 images on the [online tool](https://ia.inkers.ai/) which is to be used in the next assignments.

**Status** - This assignment has been **completed** in the online tool.



## Assignment 4B

### Highlights

- **Resnet56 V2** was used to to train on CIFAR10 dataset
- A **batch size of 512** to has been selected
- **Super convergence** has been used as in the last assignment to attain higher validation accuracy
- Optimizer being used is **SGD with momentum**(.95)
- The model acquired **91% validation accuracy** on the 47th epoch

### Epoch Logs

```
Epoch 1/50
(0.009999999776482582, 0.1)
Epoch 00001: LearningRateScheduler setting learning rate to 0.1.
98/98 [==============================] - 53s 539ms/step - loss: 1.8654 - acc: 0.3096 - val_loss: 8.8256 - val_acc: 0.1684
Epoch 2/50
(0.10000000149011612, 0.16086956521739126)
Epoch 00002: LearningRateScheduler setting learning rate to 0.16086956521739126.
98/98 [==============================] - 35s 359ms/step - loss: 1.4563 - acc: 0.4683 - val_loss: 11.2000 - val_acc: 0.1132
Epoch 3/50
(0.1608695685863495, 0.22173913043478252)
Epoch 00003: LearningRateScheduler setting learning rate to 0.22173913043478252.
98/98 [==============================] - 35s 361ms/step - loss: 1.2671 - acc: 0.5453 - val_loss: 12.6447 - val_acc: 0.1158
Epoch 4/50
(0.22173912823200226, 0.2826086956521738)
Epoch 00004: LearningRateScheduler setting learning rate to 0.2826086956521738.
98/98 [==============================] - 35s 361ms/step - loss: 1.0936 - acc: 0.6087 - val_loss: 11.2365 - val_acc: 0.1446
Epoch 5/50
(0.28260868787765503, 0.343478260869565)
Epoch 00005: LearningRateScheduler setting learning rate to 0.343478260869565.
98/98 [==============================] - 35s 361ms/step - loss: 0.9848 - acc: 0.6497 - val_loss: 14.4943 - val_acc: 0.1002
Epoch 6/50
(0.343478262424469, 0.40434782608695663)
Epoch 00006: LearningRateScheduler setting learning rate to 0.40434782608695663.
98/98 [==============================] - 35s 361ms/step - loss: 0.9065 - acc: 0.6793 - val_loss: 8.6200 - val_acc: 0.2789
Epoch 7/50
(0.40434783697128296, 0.4652173913043479)
Epoch 00007: LearningRateScheduler setting learning rate to 0.4652173913043479.
98/98 [==============================] - 35s 361ms/step - loss: 0.8609 - acc: 0.6981 - val_loss: 14.2872 - val_acc: 0.1018
Epoch 8/50
(0.46521738171577454, 0.5260869565217391)
Epoch 00008: LearningRateScheduler setting learning rate to 0.5260869565217391.
98/98 [==============================] - 35s 360ms/step - loss: 0.7918 - acc: 0.7225 - val_loss: 10.8129 - val_acc: 0.2026
Epoch 9/50
(0.5260869860649109, 0.5869565217391304)
Epoch 00009: LearningRateScheduler setting learning rate to 0.5869565217391304.
98/98 [==============================] - 35s 361ms/step - loss: 0.7549 - acc: 0.7356 - val_loss: 4.4039 - val_acc: 0.3513
Epoch 10/50
(0.5869565010070801, 0.6478260869565217)
Epoch 00010: LearningRateScheduler setting learning rate to 0.6478260869565217.
98/98 [==============================] - 35s 361ms/step - loss: 0.7322 - acc: 0.7428 - val_loss: 9.8416 - val_acc: 0.2172
Epoch 11/50
(0.647826075553894, 0.7086956521739128)
Epoch 00011: LearningRateScheduler setting learning rate to 0.7086956521739128.
98/98 [==============================] - 35s 360ms/step - loss: 0.6942 - acc: 0.7575 - val_loss: 11.4316 - val_acc: 0.1728
Epoch 12/50
(0.708695650100708, 0.7695652173913041)
Epoch 00012: LearningRateScheduler setting learning rate to 0.7695652173913041.
98/98 [==============================] - 35s 360ms/step - loss: 0.6654 - acc: 0.7682 - val_loss: 10.7191 - val_acc: 0.2004
Epoch 13/50
(0.769565224647522, 0.8304347826086957)
Epoch 00013: LearningRateScheduler setting learning rate to 0.8304347826086957.
98/98 [==============================] - 35s 360ms/step - loss: 0.6471 - acc: 0.7745 - val_loss: 5.6410 - val_acc: 0.3100
Epoch 14/50
(0.8304347991943359, 0.8913043478260867)
Epoch 00014: LearningRateScheduler setting learning rate to 0.8913043478260867.
98/98 [==============================] - 35s 360ms/step - loss: 0.6139 - acc: 0.7877 - val_loss: 6.3367 - val_acc: 0.3573
Epoch 15/50
(0.8913043737411499, 0.9521739130434782)
Epoch 00015: LearningRateScheduler setting learning rate to 0.9521739130434782.
98/98 [==============================] - 35s 359ms/step - loss: 0.6127 - acc: 0.7880 - val_loss: 6.8329 - val_acc: 0.2828
Epoch 16/50
(0.9521738886833191, 1.0130434782608695)
Epoch 00016: LearningRateScheduler setting learning rate to 1.0130434782608695.
98/98 [==============================] - 35s 360ms/step - loss: 0.5927 - acc: 0.7948 - val_loss: 9.4962 - val_acc: 0.2407
Epoch 17/50
(1.0130435228347778, 1.0739130434782609)
Epoch 00017: LearningRateScheduler setting learning rate to 1.0739130434782609.
98/98 [==============================] - 35s 359ms/step - loss: 0.5751 - acc: 0.7993 - val_loss: 5.4470 - val_acc: 0.3648
Epoch 18/50
(1.0739130973815918, 1.134782608695652)
Epoch 00018: LearningRateScheduler setting learning rate to 1.134782608695652.
98/98 [==============================] - 35s 360ms/step - loss: 0.5528 - acc: 0.8093 - val_loss: 2.1817 - val_acc: 0.4220
Epoch 19/50
(1.1347825527191162, 1.1956521739130435)
Epoch 00019: LearningRateScheduler setting learning rate to 1.1956521739130435.
98/98 [==============================] - 35s 359ms/step - loss: 0.5398 - acc: 0.8109 - val_loss: 3.1317 - val_acc: 0.4778
Epoch 20/50
(1.1956521272659302, 1.2565217391304349)
Epoch 00020: LearningRateScheduler setting learning rate to 1.2565217391304349.
98/98 [==============================] - 35s 359ms/step - loss: 0.5395 - acc: 0.8109 - val_loss: 2.2572 - val_acc: 0.4166
Epoch 21/50
(1.2565217018127441, 1.3173913043478258)
Epoch 00021: LearningRateScheduler setting learning rate to 1.3173913043478258.
98/98 [==============================] - 35s 359ms/step - loss: 0.5327 - acc: 0.8161 - val_loss: 4.2052 - val_acc: 0.3782
Epoch 22/50
(1.317391276359558, 1.3782608695652174)
Epoch 00022: LearningRateScheduler setting learning rate to 1.3782608695652174.
98/98 [==============================] - 35s 362ms/step - loss: 0.5188 - acc: 0.8183 - val_loss: 3.7489 - val_acc: 0.3436
Epoch 23/50
(1.378260850906372, 1.4391304347826088)
Epoch 00023: LearningRateScheduler setting learning rate to 1.4391304347826088.
98/98 [==============================] - 35s 359ms/step - loss: 0.4992 - acc: 0.8246 - val_loss: 3.2622 - val_acc: 0.4484
Epoch 24/50
(1.439130425453186, 1.5)
Epoch 00024: LearningRateScheduler setting learning rate to 1.5.
98/98 [==============================] - 35s 359ms/step - loss: 0.4999 - acc: 0.8258 - val_loss: 1.6471 - val_acc: 0.5813
Epoch 25/50
(1.5, 1.4391304347826088)
Epoch 00025: LearningRateScheduler setting learning rate to 1.4391304347826088.
98/98 [==============================] - 35s 359ms/step - loss: 0.4748 - acc: 0.8335 - val_loss: 1.6897 - val_acc: 0.5807
Epoch 26/50
(1.439130425453186, 1.3782608695652174)
Epoch 00026: LearningRateScheduler setting learning rate to 1.3782608695652174.
98/98 [==============================] - 35s 359ms/step - loss: 0.4547 - acc: 0.8411 - val_loss: 0.7218 - val_acc: 0.7771
Epoch 27/50
(1.378260850906372, 1.3173913043478263)
Epoch 00027: LearningRateScheduler setting learning rate to 1.3173913043478263.
98/98 [==============================] - 35s 358ms/step - loss: 0.4255 - acc: 0.8508 - val_loss: 1.8576 - val_acc: 0.5834
Epoch 28/50
(1.317391276359558, 1.2565217391304346)
Epoch 00028: LearningRateScheduler setting learning rate to 1.2565217391304346.
98/98 [==============================] - 35s 359ms/step - loss: 0.4062 - acc: 0.8593 - val_loss: 0.9122 - val_acc: 0.7181
Epoch 29/50
(1.2565217018127441, 1.1956521739130435)
Epoch 00029: LearningRateScheduler setting learning rate to 1.1956521739130435.
98/98 [==============================] - 35s 359ms/step - loss: 0.3952 - acc: 0.8610 - val_loss: 0.9964 - val_acc: 0.7087
Epoch 30/50
(1.1956521272659302, 1.134782608695652)
Epoch 00030: LearningRateScheduler setting learning rate to 1.134782608695652.
98/98 [==============================] - 35s 359ms/step - loss: 0.3744 - acc: 0.8687 - val_loss: 0.5543 - val_acc: 0.8245
Epoch 31/50
(1.1347825527191162, 1.0739130434782609)
Epoch 00031: LearningRateScheduler setting learning rate to 1.0739130434782609.
98/98 [==============================] - 35s 359ms/step - loss: 0.3521 - acc: 0.8770 - val_loss: 1.3344 - val_acc: 0.6816
Epoch 32/50
(1.0739130973815918, 1.0130434782608695)
Epoch 00032: LearningRateScheduler setting learning rate to 1.0130434782608695.
98/98 [==============================] - 35s 359ms/step - loss: 0.3270 - acc: 0.8837 - val_loss: 2.0216 - val_acc: 0.6045
Epoch 33/50
(1.0130435228347778, 0.9521739130434782)
Epoch 00033: LearningRateScheduler setting learning rate to 0.9521739130434782.
98/98 [==============================] - 35s 359ms/step - loss: 0.3192 - acc: 0.8865 - val_loss: 0.5763 - val_acc: 0.8316
Epoch 34/50
(0.9521738886833191, 0.891304347826087)
Epoch 00034: LearningRateScheduler setting learning rate to 0.891304347826087.
98/98 [==============================] - 35s 358ms/step - loss: 0.3009 - acc: 0.8944 - val_loss: 0.8337 - val_acc: 0.7709
Epoch 35/50
(0.8913043737411499, 0.8304347826086957)
Epoch 00035: LearningRateScheduler setting learning rate to 0.8304347826086957.
98/98 [==============================] - 35s 359ms/step - loss: 0.2854 - acc: 0.8979 - val_loss: 0.4696 - val_acc: 0.8493
Epoch 36/50
(0.8304347991943359, 0.7695652173913041)
Epoch 00036: LearningRateScheduler setting learning rate to 0.7695652173913041.
98/98 [==============================] - 35s 359ms/step - loss: 0.2793 - acc: 0.9010 - val_loss: 0.6431 - val_acc: 0.8185
Epoch 37/50
(0.769565224647522, 0.7086956521739128)
Epoch 00037: LearningRateScheduler setting learning rate to 0.7086956521739128.
98/98 [==============================] - 35s 358ms/step - loss: 0.2540 - acc: 0.9099 - val_loss: 0.5960 - val_acc: 0.8266
Epoch 38/50
(0.708695650100708, 0.6478260869565217)
Epoch 00038: LearningRateScheduler setting learning rate to 0.6478260869565217.
98/98 [==============================] - 35s 359ms/step - loss: 0.2439 - acc: 0.9137 - val_loss: 0.5020 - val_acc: 0.8515
Epoch 39/50
(0.647826075553894, 0.5869565217391304)
Epoch 00039: LearningRateScheduler setting learning rate to 0.5869565217391304.
98/98 [==============================] - 35s 359ms/step - loss: 0.2326 - acc: 0.9176 - val_loss: 0.4179 - val_acc: 0.8699
Epoch 40/50
(0.5869565010070801, 0.5260869565217391)
Epoch 00040: LearningRateScheduler setting learning rate to 0.5260869565217391.
98/98 [==============================] - 35s 359ms/step - loss: 0.2178 - acc: 0.9219 - val_loss: 0.4566 - val_acc: 0.8667
Epoch 41/50
(0.5260869860649109, 0.4652173913043479)
Epoch 00041: LearningRateScheduler setting learning rate to 0.4652173913043479.
98/98 [==============================] - 35s 359ms/step - loss: 0.2068 - acc: 0.9257 - val_loss: 0.5457 - val_acc: 0.8570
Epoch 42/50
(0.46521738171577454, 0.40434782608695663)
Epoch 00042: LearningRateScheduler setting learning rate to 0.40434782608695663.
98/98 [==============================] - 35s 359ms/step - loss: 0.1921 - acc: 0.9317 - val_loss: 0.4087 - val_acc: 0.8785
Epoch 43/50
(0.40434783697128296, 0.34347826086956534)
Epoch 00043: LearningRateScheduler setting learning rate to 0.34347826086956534.
98/98 [==============================] - 35s 359ms/step - loss: 0.1831 - acc: 0.9343 - val_loss: 0.3703 - val_acc: 0.8902
Epoch 44/50
(0.343478262424469, 0.2826086956521738)
Epoch 00044: LearningRateScheduler setting learning rate to 0.2826086956521738.
98/98 [==============================] - 35s 359ms/step - loss: 0.1694 - acc: 0.9397 - val_loss: 0.3901 - val_acc: 0.8855
Epoch 45/50
(0.28260868787765503, 0.22173913043478252)
Epoch 00045: LearningRateScheduler setting learning rate to 0.22173913043478252.
98/98 [==============================] - 35s 358ms/step - loss: 0.1589 - acc: 0.9441 - val_loss: 0.3495 - val_acc: 0.8964
Epoch 46/50
(0.22173912823200226, 0.16086956521739126)
Epoch 00046: LearningRateScheduler setting learning rate to 0.16086956521739126.
98/98 [==============================] - 35s 359ms/step - loss: 0.1478 - acc: 0.9471 - val_loss: 0.3228 - val_acc: 0.9044
Epoch 47/50
(0.1608695685863495, 0.1)
Epoch 00047: LearningRateScheduler setting learning rate to 0.1.
98/98 [==============================] - 35s 359ms/step - loss: 0.1355 - acc: 0.9519 - val_loss: 0.3017 - val_acc: 0.9100
Epoch 48/50
(0.10000000149011612, 0.16086956521739157)
Epoch 00048: LearningRateScheduler setting learning rate to 0.1.
98/98 [==============================] - 35s 360ms/step - loss: 0.1287 - acc: 0.9542 - val_loss: 0.3096 - val_acc: 0.9073
Epoch 49/50
(0.10000000149011612, 0.22173913043478252)
Epoch 00049: LearningRateScheduler setting learning rate to 0.1.
98/98 [==============================] - 35s 359ms/step - loss: 0.1298 - acc: 0.9551 - val_loss: 0.3219 - val_acc: 0.9077
Epoch 50/50
(0.10000000149011612, 0.28260869565217406)
Epoch 00050: LearningRateScheduler setting learning rate to 0.1.
98/98 [==============================] - 35s 358ms/step - loss: 0.1290 - acc: 0.9544 - val_loss: 0.3273 - val_acc: 0.9048
```

