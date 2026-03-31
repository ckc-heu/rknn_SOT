在线免费测试网站https://frp-bus.com:49189/login访问密码请发邮件ckc8686@163.com
![1](https://github.com/user-attachments/assets/0b912e25-dec3-46d1-8075-8b68daa7e26d)


# 📊 NanoTrack 在 Rockchip RK3588 / RK3576 上的评估结果

**系统环境**：Ubuntu 22.04  
**RKNN 运行时**：librknnrt v2.3.2  
**RKNN 驱动版本**：v0.9.8  
**模型格式**：RKNN v6（由 rknn-toolkit2 v2.3.0 导出）

> 🔹 所有测试均在 **默认频率（默频）** 下运行。  
> 🔹 **量化（`backbone255q`）仅作用于搜索分支的主干网络**；模板分支（127×127）虽也量化，但只在初始化时调用一次，对跟踪速度影响可忽略，因此未单独量化。  
> 🔹 量化模型 **未进行校准（no calibration）**，为直接转换。 <br>
> 🔹 OSTrack有些算子rknn不支持，对部分逻辑进行了处理。

---

## 🥇 VOT2018 评估结果

| 模型名称       | 平台   | 主干是否量化 | Accuracy | Robustness | Lost Number | EAO   | FPS   |
|----------------|--------|--------------|----------|------------|-------------|-------|-------|
| `nanotrack_v3` | RK3588 | 否           | 0.569    | 0.187      | 40.0        | 0.431 | 112   |
| `nanotrack_v3` | RK3588 | 是           | 0.566    | 0.234      | 50.0        | 0.378 | 121   |
| `nanotrack_v2` | RK3588 | 否           | 0.555    | 0.304      | 65.0        | 0.332 | 135   |
| `nanotrack_v2` | RK3588 | 是           | 0.552    | 0.314      | 67.0        | 0.327 | 142   |
| `nanotrack_v3` | RK3576 | 否           | 0.568    | 0.215      | 46.0        | 0.399 | x     |
| `nanotrack_v3` | RK3576 | 是           | 0.560    | 0.187      | 40.0        | 0.405 | x1    |
| `nanotrack_v2` | RK3576 | 否           | 0.572    | 0.318      | 68.0        | 0.337 | x     |
| `nanotrack_v2` | RK3576 | 是           | 0.556    | 0.337      | 72.0        | 0.312 | x     |
| `OSTrack` | RK3588 | 否           | 0.591    | 0.300      | 64.0        | 0.306 | 3.1     |

---

## 🥈 OTB100 评估结果

| 模型名称       | 平台   | 主干是否量化 | Success | Precision | FPS   |
|----------------|--------|--------------|---------|-----------|-------|
| `nanotrack_v3` | RK3588 | 否           | 0.671   | 0.886     | 112   |
| `nanotrack_v3` | RK3588 | 是           | 0.666   | 0.878     | 121   |
| `nanotrack_v2` | RK3588 | 否           | 0.642   | 0.845     | 135   |
| `nanotrack_v2` | RK3588 | 是           | 0.637   | 0.836     | 142   |
| `nanotrack_v3` | RK3576 | 否           | 0.666   | 0.880     | x     |
| `nanotrack_v3` | RK3576 | 是           | 0.666   | 0.875     | x     |
| `nanotrack_v2` | RK3576 | 否           | 0.645   | 0.846     | x     |
| `nanotrack_v2` | RK3576 | 是           | 0.636   | 0.833     | x     |
| `OSTrack` | RK3588 | 否           | 0.695   | 0.903     | 3     |
| `new` | RK3588 | 否           | 0.690   | 0.891     | 18     |
---



> 🔜 更多测试数据、部署代码及训练细节将在整理后开源。

---

## 参考项目

- [rknn-toolkit2](https://github.com/rockchip-linux/rknn-toolkit2)  
- [SiamTrackers](https://github.com/HonglinChu/SiamTrackers)  
- [NanoTrack_RK3588_python](https://github.com/Try2ChangeX/NanoTrack_RK3588_python)
