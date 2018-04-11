# Data download guide

## Browsing and downloading the data

The data used for the paper come in four sets:

1. `train`: The train data, including predictions on the train data, as multi-channel images for easy viewing.
1. `train_single_channel_images`: The train data, including predictions on the train data, as single-channel images. The filenames of these images identify the transmitted light modality or fluorescent label.
1. `test`: The test data, including predictions on the test data, as multi-channel images for easy viewing.
1. `test_single_channel_images`: The test data, including predictions on the test data, as single-channel images. The filenames of these images identify the transmitted light modality or fluorescent label.

These images may be viewed in a browser or downloaded in bulk using [`gsutil`](https://cloud.google.com/storage/docs/gsutil).
The browser links are:
[`train`](https://storage.googleapis.com/in-silico-labeling/paper_data/train_data_index.html),
[`train_single_channel_images`](https://storage.googleapis.com/in-silico-labeling/paper_data/train_single_channel_images_data_index.html),
[`test`](https://storage.googleapis.com/in-silico-labeling/paper_data/test_data_index.html), and
[`test_single_channel_images`](https://storage.googleapis.com/in-silico-labeling/paper_data/test_single_channel_images_data_index.html).

To download in bulk, first install [`gsutil`](https://cloud.google.com/storage/docs/gsutil) and then execute command like this:

    gsutil -m cp -r gs://in-silico-labeling/paper_data/train .
    gsutil -m cp -r gs://in-silico-labeling/paper_data/train_single_channel_images .
    gsutil -m cp -r gs://in-silico-labeling/paper_data/test .
    gsutil -m cp -r gs://in-silico-labeling/paper_data/test_single_channel_images .

## Understanding the data

The file paths in the datasets have the following structure: `<lab>/<condition>/<descriptive_filename>.png`.

The naming for the labs and conditions differs from the paper.
The key is:

1. `Rubin/scott_1_0` → `Condition A`.
1. `Finkbeiner/kevan_0_{7,8,9,10}` → `Condition B`.
1. `Finkbeiner/alicia_2_0` → `Condition C`.
1. `Finkbeiner/yusha_0_1` → `Condition D`.
1. `GLS/2015_06_26` → `Condition E`.

The filenames themselves contain enough information to understand the contents of each image.
For example, the following is the set of images from the well A4 in the `kevan_0_8` condition:
`
1. `lab-Finkbeiner,condition-kevan_0_8,acquisition_date,year-2015,month-9,day-28,well-A4,depth_computation,value-MAXPROJECT,channel,value-DAPI_CONFOCAL,is_mask-false,kind,value-ORIGINAL.png`
1. `lab-Finkbeiner,condition-kevan_0_8,acquisition_date,year-2015,month-9,day-28,well-A4,depth_computation,value-MAXPROJECT,channel,value-DAPI_CONFOCAL,statistic,value-MEDIAN,kind,value-PREDICTED.png`
1. `lab-Finkbeiner,condition-kevan_0_8,acquisition_date,year-2015,month-9,day-28,well-A4,depth_computation,value-MAXPROJECT,channel,value-MAP2_CONFOCAL,is_mask-false,kind,value-ORIGINAL.png`
1. `lab-Finkbeiner,condition-kevan_0_8,acquisition_date,year-2015,month-9,day-28,well-A4,depth_computation,value-MAXPROJECT,channel,value-MAP2_CONFOCAL,statistic,value-MEDIAN,kind,value-PREDICTED.png`
1. `lab-Finkbeiner,condition-kevan_0_8,acquisition_date,year-2015,month-9,day-28,well-A4,depth_computation,value-MAXPROJECT,channel,value-NEURITE_CONFOCAL,is_mask-false,kind,value-ORIGINAL.png`
1. `lab-Finkbeiner,condition-kevan_0_8,acquisition_date,year-2015,month-9,day-28,well-A4,depth_computation,value-MAXPROJECT,channel,value-NEURITE_CONFOCAL,statistic,value-MEDIAN,kind,value-PREDICTED.png`
1. `lab-Finkbeiner,condition-kevan_0_8,acquisition_date,year-2015,month-9,day-28,well-A4,depth_computation,value-MAXPROJECT,channel,value-NFH_CONFOCAL,is_mask-false,kind,value-ORIGINAL.png`
1. `lab-Finkbeiner,condition-kevan_0_8,acquisition_date,year-2015,month-9,day-28,well-A4,depth_computation,value-MAXPROJECT,channel,value-NFH_CONFOCAL,statistic,value-MEDIAN,kind,value-PREDICTED.png`
1. `lab-Finkbeiner,condition-kevan_0_8,acquisition_date,year-2015,month-9,day-28,well-A4,z_depth-0,channel,value-PHASE_CONTRAST,is_mask-false,kind,value-ORIGINAL.png`
1. `lab-Finkbeiner,condition-kevan_0_8,acquisition_date,year-2015,month-9,day-28,well-A4,z_depth-10,channel,value-PHASE_CONTRAST,is_mask-false,kind,value-ORIGINAL.png`
1. `lab-Finkbeiner,condition-kevan_0_8,acquisition_date,year-2015,month-9,day-28,well-A4,z_depth-11,channel,value-PHASE_CONTRAST,is_mask-false,kind,value-ORIGINAL.png`
1. `lab-Finkbeiner,condition-kevan_0_8,acquisition_date,year-2015,month-9,day-28,well-A4,z_depth-12,channel,value-PHASE_CONTRAST,is_mask-false,kind,value-ORIGINAL.png`
1. `lab-Finkbeiner,condition-kevan_0_8,acquisition_date,year-2015,month-9,day-28,well-A4,z_depth-1,channel,value-PHASE_CONTRAST,is_mask-false,kind,value-ORIGINAL.png`
1. `lab-Finkbeiner,condition-kevan_0_8,acquisition_date,year-2015,month-9,day-28,well-A4,z_depth-2,channel,value-PHASE_CONTRAST,is_mask-false,kind,value-ORIGINAL.png`
1. `lab-Finkbeiner,condition-kevan_0_8,acquisition_date,year-2015,month-9,day-28,well-A4,z_depth-3,channel,value-PHASE_CONTRAST,is_mask-false,kind,value-ORIGINAL.png`
1. `lab-Finkbeiner,condition-kevan_0_8,acquisition_date,year-2015,month-9,day-28,well-A4,z_depth-4,channel,value-PHASE_CONTRAST,is_mask-false,kind,value-ORIGINAL.png`
1. `lab-Finkbeiner,condition-kevan_0_8,acquisition_date,year-2015,month-9,day-28,well-A4,z_depth-5,channel,value-PHASE_CONTRAST,is_mask-false,kind,value-ORIGINAL.png`
1. `lab-Finkbeiner,condition-kevan_0_8,acquisition_date,year-2015,month-9,day-28,well-A4,z_depth-6,channel,value-PHASE_CONTRAST,is_mask-false,kind,value-ORIGINAL.png`
1. `lab-Finkbeiner,condition-kevan_0_8,acquisition_date,year-2015,month-9,day-28,well-A4,z_depth-7,channel,value-PHASE_CONTRAST,is_mask-false,kind,value-ORIGINAL.png`
1. `lab-Finkbeiner,condition-kevan_0_8,acquisition_date,year-2015,month-9,day-28,well-A4,z_depth-8,channel,value-PHASE_CONTRAST,is_mask-false,kind,value-ORIGINAL.png`
1. `lab-Finkbeiner,condition-kevan_0_8,acquisition_date,year-2015,month-9,day-28,well-A4,z_depth-9,channel,value-PHASE_CONTRAST,is_mask-false,kind,value-ORIGINAL.png`

Thirteen of these images are the transmitted light _z_-stack: in this case the imaging modality was phase-contrast.
The remaining eight are true and predicted fluorescence images, for the `DAPI_CONFOCAL`, `MAP2_CONFOCAL`, `NFH_CONFOCAL`, and `NEURITE_CONFOCAL` channels.
The `NEURITE_CONFOCAL` channel is a synthetic channel equal to the mean of the `MAP2_CONFOCAL` and `NFH_CONFOCAL` channels.

For this dataset you can ignore the `is_mask` field, which should always be `false`.

## License

The data is licensed under the [Creative Commons Attribution 4.0 International license](https://creativecommons.org/licenses/by/4.0/).
If you use the data, please cite our paper:

TODO: Add reference.