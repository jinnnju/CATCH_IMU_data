# [ICLR 2025] CATCH: Channel-Aware Multivariate Time Series Anomaly Detection via Frequency Patching

**CATCH_IMU_data** applies **CATCH** to real-world **IMU sensor** data.  
This repo provides minimal preprocessing and a runnable script to detect anomalies on multivariate IMU signals using the CATCH pipeline.

> **Note**: The official PyTorch implementation of **CATCH** is provided by the original authors.  
> This repository focuses on applying CATCH to IMU data (data placement + one-command run).

---

## Quick Start

### 1) Install requirements
```bash
pip install -r requirements.txt
```

### 2) Prepare data
Place your **preprocessed** IMU CSV file here:
```
./dataset/anomaly_detect/data/IMU.csv
```
- The CSV should contain your IMU multivariate time series after preprocessing.
- Large raw datasets should **not** be committed to GitHub (100 MB/file limit). Consider Git LFS or external storage.

### 3) Run CATCH on IMU
```bash
sh ./scripts/multivariate_detection/detect_label/IMU_script/CATCH.sh
```
This script executes the CATCH pipeline configured for the IMU dataset and saves outputs to the default paths defined in the script.

---

## Repository Purpose
- Provide a minimal, reproducible setup to **apply CATCH** to IMU multivariate time series.
- Offer a reference **data placement** and **one-command script** for quick evaluation.
- Serve as a starting point for adapting CATCH to other sensor modalities.

---

## Acknowledgments
This repository builds on the CATCH paper and its official implementation. All credit for the method goes to the original authors.

---

## Citation

If you find this repo useful, please cite the original papers:

```bibtex
@inproceedings{wu2024catch,
  title     = {{CATCH}: Channel-Aware multivariate Time Series Anomaly Detection via Frequency Patching},
  author    = {Wu, Xingjian and Qiu, Xiangfei and Li, Zhengyu and Wang, Yihang and Hu, Jilin and Guo, Chenjuan and Xiong, Hui and Yang, Bin},
  booktitle = {ICLR},
  year      = {2025}
}

@inproceedings{qiu2025tab,
  title      = {{TAB}: Unified Benchmarking of Time Series Anomaly Detection Methods},
  author     = {Xiangfei Qiu and Zhe Li and Wanghui Qiu and Shiyan Hu and Lekui Zhou and Xingjian Wu and Zhengyu Li and Chenjuan Guo and Aoying Zhou and Zhenli Sheng and Jilin Hu and Christian S. Jensen and Bin Yang},
  booktitle  = {Proc. {VLDB} Endow.},
  year       = {2025}
}
```
