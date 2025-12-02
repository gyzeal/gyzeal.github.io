# 标题：初识大语言模型训练中 GPU 显存分配（初学者）

## 1. 前向传播：

### 1.1 权重加载到 GPU 显存 

首先将权重（`.pth`、`.safetensors`）加载进GPU显存 （VRAM）中。
模型权重的数据类型（`fp32`、`bf16`、`fp16`、`int8` 等）决定了占用多少显存。

- **显存估算公式**:
对于一个具有 \(n\) Billion 参数的模型，其权重占用显存约为：  
  $$
  \text{Param Memory} \approx n \times 10^9 \times \text{Bytes(fp32/bf16/fp16/int8...)}
  $$

- **是否有策略可以缓解显存占用？**  
```text
1. 参数量化策略
```

### 1.2 激活值（Activation）显存占用

其次开始处理数据 \((B, L, H)\)。 
每一层 Layer 的输出（\(X\)）都需要存下来，因为反向传播算梯度时要用到它,链式法则:
$$
\frac{dL}{dW} = \frac{dL}{dY} \cdot X
$$

此时，激活值所占用的显存可通过如下公式粗略计算：  
$$
\text{Activation Memory} \approx 
\text{Layers} \times \text{Batch Size} \times \text{Seq Len} \times \text{Hidden Size} \times \text{Bytes}
$$

- **那么是否有策略可以缓解激活值带来的高昂显存占用？例如：**

```
1. 梯度检查点
2. Flash Attention 2
3. 激活值卸载
4. 序列并行:将序列 L 切分成 N 份（N=GPU数量），每张卡只存 L/N 的激活值
``` 