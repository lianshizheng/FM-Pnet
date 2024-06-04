# [FM-Based Positioning via Deep Learning.](https://www.techrxiv.org/doi/full/10.36227/techrxiv.24580956.v1)

## About paper

**Title**: FM-Based Positioning via Deep Learning.

**Author**: Shilian Zheng, Jiacheng Hu, Luxin Zhang, Kunfeng Qiu, Jie Chen, Peihan Qi, Zhijin Zhao, and Xiaoniu Yang.

**Journal**: IEEE Journal on Selected Areas in Communications.

**Abstract**: Frequency modulation (FM) broadcast signals, regarded as opportunistic signals, hold significant potential for indoor and outdoor positioning applications. The existing FM-based positioning methods primarily rely on received signal strength (RSS) for positioning, the accuracy of which needs improvement. In this paper, we introduce FM-Pnet, an end-to-end FM-based positioning method that leverages deep learning. This method utilizes the time-frequency representation of FM signals as network input, enabling automatically learning of deep features for positioning. We also propose two strategies, noise injection and enriching training samples, to enhance the model's generalization performance over long time spans. We construct datasets for both indoor and outdoor scenarios and conduct extensive experiments to validate the performance of our proposed method. Experimental results demonstrate that FM-Pnet significantly outperforms traditional RSS-based positioning methods in terms of both positioning accuracy and stability.


## Datasets

Our dataset encompasses indoor and outdoor environments, with data collected over three days (Day1, 2, and 3) from the same locations. In both settings, Day1 data contains various FM signals, featuring multiple bandwidths. These signals, sampled at a center frequency of 97.5MHz, include two bandwidths: 320kHz (sampled at 400ksps) and 4MHz (sampled at 5Msps). Additionally, outdoor data samples with a bandwidth of 20MHz (sampled at 25Msps) were collected. For cross-day testing, Day2 and Day3 exclusively contain signals with a 4MHz bandwidth. Signals were continuously sampled for approximately 30 seconds at each collection point. The dataset comprises raw broadband signals within the FM frequency range, stored in (.std) file format.

The python code to read this data is as follows：

```
import torch
file_path = r'indoor_day1_4MHz_4096_test.pt'

data = torch.load(file_path)

print(data.shape)
```

Each day's data folder includes subfolders (25 indoor and 30 outdoor), representing specific collection points. Subfolder names correspond to the numbering of collection points (01-25 for indoor and 01-30 for outdoor), with corresponding coordinates provided.

```python
#Indoor:
class_coordinates = {
0: [0, 0], 1: [0, 2], 2: [0, 4], 3: [0, 6], 4: [0, 8],
5: [2,8],6: [2, 6], 7: [2, 4], 8: [2, 2], 9: [2, 0],
10: [4, 0], 11: [4, 2],12: [4, 4], 13: [4, 6], 14: [4, 8],
15: [6, 8], 16: [6, 6], 17: [6, 4],18: [6, 2], 19: [6, 0],
20: [8, 0], 21: [8, 2], 22: [8, 4], 23: [8,6],24: [8, 8]
}
```

```python
#Outdoor:
class_coordinates = {
0: [0, 0], 1: [0, 3], 2: [0, 6], 3: [0, 9], 4: [0, 12], 5: [0, 15],
6: [3, 0], 7: [3, 3], 8: [3, 6], 9: [3, 9], 10: [3, 12], 11: [3, 15],
12: [6, 0], 13: [6, 3], 14: [6, 6], 15: [6, 9], 16: [6, 12], 17: [6, 15],
18: [9, 0], 19: [9, 3], 20: [9, 6], 21: [9, 9], 22: [9, 12], 23: [9, 15],
24: [12, 0], 25: [12, 3], 26: [12, 6],27: [12, 9], 28: [12, 12], 29: [12, 15]
}
```

This dataset offers a rich resource for studying FM signals across diverse environmental conditions and can be valuable for various research and development endeavors.

## Access link of these two datasets

**indoor**

[The part 1 of dataset Indoor](https://figshare.com/articles/dataset/The_part_1_of_dataset_Indoor/25958365)

[The part 2 of dataset Indoor](https://figshare.com/articles/dataset/The_part_2_of_dataset_Indoor/25958293)

**outdoor**

[The part 1 of dataset Outdoor](https://figshare.com/articles/dataset/The_part_1_of_dataset_Outdoor/25962808)

[The part 2 of dataset Outdoor]()

[The part 3 of dataset Outdoor](https://figshare.com/articles/dataset/The_part_3_of_dataset_Outdoor/25963042)

## Citation

If you find this repository helpful, please consider citing:
```
Shilian Zheng, Jiachen Hu, Luxin Zhang, Kunfeng Qiu, Jie Chen, Peihan Qi, Zhijin Zhao, and Xiaoniu Yang. "FM-Based Positioning via Deep Learning." Authorea Preprints (2023). DOI: 10.36227/techrxiv.24580956.v1
```
or
```
@article{zheng2023fm,
  title={FM-Based Positioning via Deep Learning},
  author={Zheng, Shilian and Hu, Jiachen and Zhang, Luxin and Qiu, Kunfeng and Chen, Jie and Qi, Peihan and Zhao, Zhijin and Yang, Xiaoniu},
  journal={Authorea Preprints},
  year={2023},
  publisher={Authorea}
}
```
