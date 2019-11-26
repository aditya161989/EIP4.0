**Training Results**

Train on 60000 samples, validate on 10000 samples
Epoch 1/20

Epoch 00001: LearningRateScheduler setting learning rate to 0.002.
60000/60000 - 17s 285us/step - loss: 0.2237 - acc: 0.9314 - val_loss: 0.0566 - val_acc: 0.9815
Epoch 2/20

Epoch 00002: LearningRateScheduler setting learning rate to 0.0015163002.
60000/60000 - 11s 189us/step - loss: 0.0653 - acc: 0.9797 - val_loss: 0.0744 - val_acc: 0.9737
Epoch 3/20

Epoch 00003: LearningRateScheduler setting learning rate to 0.0012210012.
60000/60000 - 11s 189us/step - loss: 0.0503 - acc: 0.9842 - val_loss: 0.0336 - val_acc: 0.9891
Epoch 4/20

Epoch 00004: LearningRateScheduler setting learning rate to 0.0010219724.
60000/60000 - 11s 180us/step - loss: 0.0416 - acc: 0.9867 - val_loss: 0.0287 - val_acc: 0.9912
Epoch 5/20

Epoch 00005: LearningRateScheduler setting learning rate to 0.0008787346.
60000/60000 - 10s 163us/step - loss: 0.0351 - acc: 0.9889 - val_loss: 0.0281 - val_acc: 0.9901
Epoch 6/20

Epoch 00006: LearningRateScheduler setting learning rate to 0.0007707129.
60000/60000 - 11s 190us/step - loss: 0.0329 - acc: 0.9890 - val_loss: 0.0208 - val_acc: 0.9939
Epoch 7/20

Epoch 00007: LearningRateScheduler setting learning rate to 0.0006863418.
60000/60000 - 14s 236us/step - loss: 0.0294 - acc: 0.9910 - val_loss: 0.0202 - val_acc: 0.9933
Epoch 8/20

Epoch 00008: LearningRateScheduler setting learning rate to 0.0006186205.
60000/60000 - 14s 240us/step - loss: 0.0280 - acc: 0.9912 - val_loss: 0.0208 - val_acc: 0.9937
Epoch 9/20

Epoch 00009: LearningRateScheduler setting learning rate to 0.0005630631.
60000/60000 - 15s 247us/step - loss: 0.0267 - acc: 0.9914 - val_loss: 0.0195 - val_acc: 0.9938
Epoch 10/20

Epoch 00010: LearningRateScheduler setting learning rate to 0.0005166624.
60000/60000 - 15s 247us/step - loss: 0.0232 - acc: 0.9927 - val_loss: 0.0210 - val_acc: 0.9919
Epoch 11/20

Epoch 00011: LearningRateScheduler setting learning rate to 0.000477327.
60000/60000 - 14s 233us/step - loss: 0.0230 - acc: 0.9926 - val_loss: 0.0190 - val_acc: 0.9931
Epoch 12/20

Epoch 00012: LearningRateScheduler setting learning rate to 0.0004435573.
60000/60000 - 13s 217us/step - loss: 0.0216 - acc: 0.9931 - val_loss: 0.0178 - val_acc: 0.9942
Epoch 13/20

Epoch 00013: LearningRateScheduler setting learning rate to 0.0004142502.
60000/60000 - 14s 235us/step - loss: 0.0217 - acc: 0.9929 - val_loss: 0.0200 - val_acc: 0.9935
Epoch 14/20

Epoch 00014: LearningRateScheduler setting learning rate to 0.0003885759.
60000/60000 - 13s 220us/step - loss: 0.0196 - acc: 0.9933 - val_loss: 0.0182 - val_acc: 0.9937
Epoch 15/20

Epoch 00015: LearningRateScheduler setting learning rate to 0.0003658983.
60000/60000 - 11s 181us/step - loss: 0.0191 - acc: 0.9941 - val_loss: 0.0192 - val_acc: 0.9936
Epoch 16/20

Epoch 00016: LearningRateScheduler setting learning rate to 0.0003457217.
60000/60000 - 10s 162us/step - loss: 0.0180 - acc: 0.9945 - val_loss: 0.0174 - val_acc: 0.9941
Epoch 17/20

Epoch 00017: LearningRateScheduler setting learning rate to 0.000327654.
60000/60000 - 10s 169us/step - loss: 0.0182 - acc: 0.9940 - val_loss: 0.0167 - val_acc: 0.9944
Epoch 18/20

Epoch 00018: LearningRateScheduler setting learning rate to 0.000311381.
60000/60000 - 10s 168us/step - loss: 0.0174 - acc: 0.9942 - val_loss: 0.0171 - val_acc: 0.9939
Epoch 19/20

Epoch 00019: LearningRateScheduler setting learning rate to 0.0002966479.
60000/60000 - 10s 167us/step - loss: 0.0168 - acc: 0.9945 - val_loss: 0.0184 - val_acc: 0.9937
Epoch 20/20

Epoch 00020: LearningRateScheduler setting learning rate to 0.000283246.
60000/60000 - 10s 169us/step - loss: 0.0160 - acc: 0.9946 - val_loss: 0.0165 - val_acc: 0.9947
<keras.callbacks.History at 0x7f437a4a60f0>


**model.evaluate() Results**   
`[0.01646772253876843, 0.9947]`   

**Strategy**   
 - As a first step, I focussed on reducing the number of parameters to less than 15000.   
 - I changed the learning rate to .002
 
