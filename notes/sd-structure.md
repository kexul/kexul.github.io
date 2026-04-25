# Stable diffusion结构

## [整体架构](https://zhuanlan.zhihu.com/p/613337342)

![v2-60b029fe6065252a1441ecc5a3f6bb1a_r](assets/v2-60b029fe6065252a1441ecc5a3f6bb1a_r-20240425163115-yc774lt.jpg)

### 使用UNet做DDPM

- 原始UNet结构

对称的 U 形结构：
  - 左侧下采样提取特征
  - 右侧上采样恢复分辨率
  - 跳连(skip connection)把浅层细节传到深层

![image](assets/image-20240425160939-nkrjj6l.png)

- DDPM中的UNet结构

相比原始 UNet 的改动：
  - 普通卷积换成带[残差](residual-conv.md)的卷积，训练更稳定
  - 更深的层加入[cross attention](cross-attention.md)注入条件信息
  - 更密集的跳连：每个大层的下采样子模块都会输入到对称的上采样部分

![image](assets/image-20240425161106-ik3p00p.png)

- Stable diffusion中的UNet结构，每一层都有[cross attention](cross-attention.md)加持

![image](assets/image-20240425161511-ur0qy3d.png)
