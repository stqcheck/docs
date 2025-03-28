# [torch 参数更多]torch.nn.CrossEntropyLoss
### [torch.nn.CrossEntropyLoss](https://pytorch.org/docs/stable/generated/torch.nn.CrossEntropyLoss.html?highlight=crossentropyloss#torch.nn.CrossEntropyLoss)

```python
torch.nn.CrossEntropyLoss(weight=None,
                          size_average=None,
                          ignore_index=- 100,
                          reduce=None,
                          reduction='mean',
                          label_smoothing=0.0)
```

### [paddle.nn.CrossEntropyLoss](https://www.paddlepaddle.org.cn/documentation/docs/zh/api/paddle/nn/CrossEntropyLoss_cn.html#crossentropyloss)

```python
paddle.nn.CrossEntropyLoss(weight=None,
                           ignore_index=-100,
                           reduction='mean',
                           soft_label=False,
                           axis=-1,
                           name=None)
```

两者功能一致但参数不一致，具体如下：
### 参数映射
| PyTorch       | PaddlePaddle | 备注                                                   |
| ------------- | ------------ | ------------------------------------------------------ |
| weight  | weight           | 表示每个类别的权重。  |
| <font color='red'> size_average </font> | -            | PyTorch 已弃用， Paddle 无此参数，需要转写。  |
| ignore_index  | ignore_index            | 表示忽略的一个标签值。  |
| <font color='red'> reduce </font>       | -            | PyTorch 已弃用， Paddle 无此参数，需要转写。  |
| reduction  | reduction            | 表示应用于输出结果的计算方式。  |
| <font color='red'> label_smoothing </font> | -            | 指定计算损失时的平滑量，Paddle 无此功能，暂无转写方式。  |
| -             | <font color='red'> soft_label </font>  | 指明 label 是否为软标签，Pytorch 无此参数，Paddle 保持默认即可。  |
| -             | <font color='red'> axis </font>       | 进行 softmax 计算的维度索引，Pytorch 无此参数，Paddle 保持默认即可。   |

### 转写示例
#### size_average
```python
# Pytorch 的 size_average、reduce 参数转为 Paddle 的 reduction 参数
if size_average is None:
    size_average = True
if reduce is None:
    reduce = True

if size_average and reduce:
    reduction = 'mean'
elif reduce:
    reduction = 'sum'
else:
    reduction = 'none'
```
