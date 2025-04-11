# Progressive Spectral-Frequency-Spatial Guidance Network for Hy perspectral Image Dehazing 

# two_step_training_model
 
 
1. Dataset preparation
   
 The dataset can be downloaded from the following URL: https://pan.baidu.com/s/1yr7Ee-mtIy1oFAfgq_HyBA (kz1x). After downloading, put the dataset address in the corresponding section of the code.


2. Train the model
   
 First run 'trainsfgnet.py' in the 'net' folder to train the first model. Its parameters are:

 --net=sfgnet --bs=1 --lr=0.0001 --trainset=HSI_train --testset=HSI_test --steps=14000 --eval_step=200

 Then run 'main.py' in the 'net' folder to train the model in step 2. Its parameters are:

  --net=ffa --blocks=8 --gps=3 --bs=1 --lr=0.0001 --trainset=HSI_train --testset=HSI_test --steps=14000 --eval_step=200
 

3. Model testing
   
 Download the pre-trained model at the following URL: https://pan.baidu.com/s/18FMc4w69gSk9pgV4MESngA (9i36). Then put the downloaded pre-trained weight file into the 'trained_models' folder.

 Run 'vis_result.py' to generate the visual results of the dehazed HSIs (the channels corresponding to R, G, and B are selected to display the visual results).

 Run ‘cal_rmse.py’, ‘cal_uqi.py’ and ‘cal_ssim.py’ to test the quantitative indicators of the model on the test set.
