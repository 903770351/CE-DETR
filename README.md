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

The proposed innovations

co-training encoder:
main.py 96-113, 302-318
engine.py 49-73
models/dino/dino.py 
models/dino/deformable_transformer.py 256-276, 341-344

NECK:
models/dino/dino.py 191-199, 276
models/dino/bifpn.py

Hybrid Dynamic Query Selection Based on IoU-aware:
models/dino/dino.py 402-427, 459-461
