# Stable diffusion结构

## [整体架构](https://zhuanlan.zhihu.com/p/613337342)

![整体架构](assets/v2-60b029fe6065252a1441ecc5a3f6bb1a_r-20240425163115-yc774lt.jpg)

### [UNet 结构](unet-structure.md)

从原始 UNet 到 DDPM UNet 再到 Stable Diffusion UNet 的演进：下采样提取特征、上采样恢复分辨率、跳连传递细节。

### [Cross Attention](cross-attention.md)

文本条件注入图像生成的关键机制。DDPM 中只在深层加入，Stable Diffusion 中每一层都有，控制更精细。

### [残差卷积](residual-conv.md)

普通卷积替换为带残差连接的卷积块，训练更稳定、网络可以更深，时间步嵌入也由此注入。
