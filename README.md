Data preparation

path/to/dataset/
  annotations/  # annotation json files
  train/    # train images
  val/      # val images

Train

  python main.py \
	--output_dir output_path -c config/DINO/DINO_4scale.py --coco_path dataset_path \
	--options dn_scalar=100 embed_init_tgt=TRUE \
	dn_label_coef=1.0 dn_bbox_coef=1.0 use_ema=False \
	dn_box_noise_scale=1.0
