## [torch 参数更多 ]torch.arcsin

### [torch.arcsin](https://pytorch.org/docs/stable/generated/torch.arcsin.html?highlight=arcsin#torch.arcsin)

```python
torch.arcsin(input,
             *,
             out=None)
```

### [paddle.asin](https://www.paddlepaddle.org.cn/documentation/docs/zh/api/paddle/asin_cn.html#asin)

```python
paddle.asin(x,
            name=None)
```

其中 Pytorch 相比 Paddle 支持更多其他参数，具体如下：

### 参数映射
| PyTorch       | PaddlePaddle | 备注                                                   |
| ------------- | ------------ | ------------------------------------------------------ |
| <font color='red'>input</font>         | <font color='red'>x</font>            | 输入的 Tensor ，仅参数名不同。                                      |
| <font color='red'>out</font>           | -            | 表示输出的 Tensor ，PaddlePaddle 无此参数，需要转写 。               |


### 转写示例
#### out：指定输出
```python
# Pytorch 写法
torch.arcsin([-0.5962,  1.4985, -0.4396,  1.4525], out=y)

# Paddle 写法
y = paddle.asin([-0.5962,  1.4985, -0.4396,  1.4525])
```
