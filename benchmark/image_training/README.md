# image_training

After clone the repo, pls go into the `torchdata/benchmark/image_training` folder to start training for image classification. <br>
Add all the training and validation images into subfolders of `images_dataset_ds/train` and `images_dataset_ds/val`. Each subfolder is required to represent the corresponding class of images.

Run `python3 generate_tar_datasets.py` to generate tar data files. (Please see comment in the script) <br>
To train using dataset, run `python3 ./train.py -r ./images_dataset_ds -ds`. <br> 
To train using datapipe, run `python3 ./train.py -r ./images_dataset_tar -dp -n 10`. <br>
To train using webdataset, run `python3 ./train.py -r ./images_dataset_tar -wds -n 10`.

TODO:
1. The iterable datapipe has no way to tell how many labels within the datapipe, so need to specify explicitly at the moment.
2. We currently shuffle the input files in preprocessing stage (when generating tar file). We will add a shuffle layer later for datapipe.