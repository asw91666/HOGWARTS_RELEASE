# Train

If you want to train the HOGWARTS model on the ARKitFace dataset, use the script below:

```bash
#!/usr/bin/env bash  
CUDA_VISIBLE_DEVICES=0 python -u train.py \  
 --gpu_ids 0 \  
 --display_freq 100 \  
 --seed 123 \  
 --model_cfg_path models/trg_model/configs/trg_face_config.yaml \  
 --name r18_hogwarts \  
 --csv_path_train dataset/ARKitFace/ARKitFace_list/list/ARKitFace_train.csv \  
 --csv_path_test dataset/ARKitFace/ARKitFace_list/list/ARKitFace_test.csv \  
 --num_threads 16 \  
 --batch_size 128 \  
 --n_epochs 20 \  
 --n_epochs_decay 10 \  
 --dataset_mode arkit \  
 --img_size 192 \  
 --lr 1e-4 \  
 --train_sampling 1\  
  --loop_loss_weight 0.5 \  
  --vertex_world_weight 20.0 \  
 --lmk68_loss_weight 1.25 \  
 --transl_loss_weight 0.5 \  
 --rotmat_loss_weight 10.0 \ 
 --focal_option b  
```

# Test

You can evaluate the HOGWARTS model on ARKitFace test dataset, BIWI dataset.

```bash
#!/usr/bin/env bash
CUDA_VISIBLE_DEVICES=0 python -u test.py \
  --csv_path_test dataset/ARKitFace/ARKitFace_list/list/ARKitFace_test.csv \
	--num_thread 8 \
	--batch_size 64 \
	--dataset_mode arkit \
	--epoch 30 \
	--name r18_hogwarts
```

You can evaluate the TRG model which is trained on ARKitFace dataset on BIWI dataset.

```bash
#!/usr/bin/env bash
CUDA_VISIBLE_DEVICES=0 python -u test.py \
  --csv_path_test dataset/ARKitFace/ARKitFace_list/list/ARKitFace_test.csv \
	--num_thread 8 \
	--batch_size 64 \
	--dataset_mode biwi \
	--epoch 30 \
	--name r18_hogwarts
```