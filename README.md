# 📊 NanoTrack on Rockchip RK3588 / RK3576 — Evaluation Results

配置信息 ubuntu22.04
rknn-toolkit-lite2 version: 2.3.2

I RKNN: [11:20:23.045] RKNN Runtime Information, librknnrt version: 2.3.2 
I RKNN: [11:20:23.045] RKNN Driver Information, version: 0.9.8
I RKNN: [11:20:23.045] RKNN Model Information, version: 6, toolkit version: 2.3.0

---

## 🥇 VOT2018 Results

| Tracker Name                          | Platform | Accuracy | Robustness | Lost Number | EAO   | FPS   |
|--------------------------------------|----------|----------|------------|-------------|-------|-------|
| `nanotrack_v3`                       | RK3588   | 0.569    | 0.187      | 40.0        | 0.431 |   112 |  
| `nanotrack_v3_backbone255q`          | RK3588   | 0.566    | 0.234      | 50.0        | 0.378 |   121 |  
| `nanotrack_v3_backbone255q`         | RK3576   | 0.560    | 0.187      | 40.0        | 0.405 |   x1 |  
| `nanotrack_v3`                      | RK3576   | 0.568    | 0.215      | 46.0        | 0.399 |   x |  
| `nanotrack_v2`                   | RK3576   | 0.572    | 0.318      | 68.0        | 0.337 |   x |  
| `nanotrack_v2_backbone255q`       | RK3576   | 0.556    | 0.337      | 72.0        | 0.312 |   x |  

 
> 🔹 都是默频跑，量化后未校准, backbone255q为量化搜索分支主干，backbone127只会在初始化阶段调用一次，对跟踪速度影响可忽略不计，量化意义不大。

---

## 🥈 OTB100 Results

| Tracker Name                     | Platform | Success | Precision | FPS   |
|----------------------------------|----------|---------|-----------|-------|
| `nanotrack_v3`                   | RK3588   | 0.671 | 0.886 | 112 |
| `nanotrack_v3_backbone255q`          | RK3588   | 0.666   | 0.878     | 121 |
| `nanotrack_v3`              | RK3576   | 0.666   | 0.880     | x |
| `nanotrack_v3_backbone255q`          | RK3576   | 0.666   | 0.875     | x |
| `nanotrack_v2`              | RK3576   | 0.645   | 0.846     | x |
| `nanotrack_v2_backbone255q`  | RK3576   | 0.636   | 0.833     | x |



**更多测试正在整理**
---


## reference

[rknn-toolkit2](https://github.com/rockchip-linux/rknn-toolkit2)  
[SiamTracker](https://github.com/HonglinChu/SiamTrackers)
[NanoTrack_RK3588_python](https://github.com/Try2ChangeX/NanoTrack_RK3588_python)
