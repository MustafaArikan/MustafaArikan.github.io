# Some GPU shortcuts

Here's the table of contents:

1. TOC
{:toc}

## Check if GPU is being used in PyTorch

```
print(torch.cuda.is_available())
```

[See!](https://chrisalbon.com/code/deep_learning/pytorch/basics/check_if_pytorch_is_using_gpu/)


## Check which CuDNN version is used

```
print(torch.backends.cudnn.version())
```


[See!](https://discuss.pytorch.org/t/how-to-check-if-torch-uses-cudnn/21933)



