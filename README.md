# DOMI_dataset
DOMI_dataset is the dataset for the paper "Detecting Outlier Machine Instances through One Dimensional CNN Gaussian Mixture Variational AutoEncoder"

## Data

### Dataset Information

| Dataset name|time length of <br> each instance </br>  |metric number of <br> each instance </br>| matrix shape of <br> each instance </br>  |
|:------:|:----:|:--------:|:-----:|
| DOMI_dataset | 288 | 19 | 19 * 288 |
| **Training set size** | **Outlier Ratio in <br>Training set (%)</br>** |**Testing set size**|**Outlier Ratio in <br>Testing set (%)</br>**| 
|  54630 | 18.62 | 27315 | 22.26 |


### DOMI_dataset

DOMI_dataset is a server machine dataset collected from a top global Internet company. 
This dataset contains 1821 machines last for one and a half months, with 5-minute equal-spaced timestamps. 
Every instance named M-X@D-Y (means machine X at day Y) is a T * M matrix, where M and T are the number of metrics and time points in one day, respectively. 
In our dataset, each machine is constituted of 19 metrics (i.e., M=19), and each day has 288 time points (i.e., T=288).

We divide the overall dataset into two parts, the first month for training and the second half month for testing. 
For the testing dataset, we provide labels for outlier machine instances, and interpretation labels for outlier instances.

Thus DOMI_dataset is made up by the following parts:

* `train_data/`: Training set. 
* `test_data/`: Testing set.
* `test_label/`: The labels of the testing set, which indicate whether an instance is an outlier. 
* `interpretation_label.txt`: The ground truth lists of metrics that contribute to outlier judgment.

Detailedly, in `train_data/`, `test_data/`, `test_label/`, each file contains the monitoring data or ground truth of one machine, thus we have 1821 files (i.e., 1821 machines) in each dir. Moreover, for files in `train_data/`, `test_data/`, each line in the file is the 19 monitored metrics at one timestamp. There are 8640 (=288 * 30) and 4320 (=288 * 15) lines in `train_data/` and `test_data/`, respectively. For files in `test_label/`, each line is the ground truth (1:outlier, 0:normal) of 1-day data (i.e., 288 lines) of the corresponding file in `test_data/`. In `interpretation_label.txt`, each line is formatted as "X+Y,index1 of metric1,index2 of metric2,...", and it means the index list of metrics for machine-X at Day-Y.
