# Cross Attention

Cross Attention（交叉注意力）是 Stable Diffusion 中把文本条件注入图像生成过程的关键机制。

## 作用

UNet 在去噪的每一步都需要知道"要生成什么"。Cross Attention 让网络可以"看"到文本提示的词向量，并决定当前特征图哪些区域应该受哪个词的影响。

## 在 UNet 中的位置

- DDPM 阶段：只在比较深的层加入 Cross Attention
- Stable Diffusion：**每一层**都有 Cross Attention，控制更精细

文本编码器（如 CLIP）把 prompt 变成一系列向量，这些向量作为 Key 和 Value，UNet 的特征作为 Query，做注意力计算后输出条件化的特征。

## 效果

没有 Cross Attention 的模型只能做无条件生成。加入之后才能实现：
- 文生图
- 特定物体、风格、构图的控制
