# UNet 结构

UNet 是一种编码器-解码器架构，最初用于医学图像分割。

## 原始 UNet

对称的 U 形结构：
- 左侧下采样提取特征
- 右侧上采样恢复分辨率
- 跳连(skip connection)把浅层细节传到深层

## DDPM 中的 UNet

相比原始 UNet 的几处改动：

- 普通卷积换成**带残差的卷积**，训练更稳定
- 更深的层加入 Cross Attention 注入条件信息
- 更密集的跳连：每个大层的下采样子模块都会输入到对称的上采样部分

## Stable Diffusion 中的 UNet

每一层都有 Cross Attention 加持，文本条件可以更细粒度地控制生成过程。
