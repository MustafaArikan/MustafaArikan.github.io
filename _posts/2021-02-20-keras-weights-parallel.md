# Get weights from a parallel model and save as a single GPU model in Keras

Here's the table of contents:

1. TOC
{:toc}

## Load into a multi-gpu model and save the weights for a single-gpu model

```
    import numpy as np
    weights = np.load("./parallel_model.npy", allow_pickle=True)
    parallel_model.set_weights(weights)
    print (parallel_model.layers[-2])
    single_gpu_model = parallel_model.layers[-2]
    np.save("./single_model", single_gpu_model.get_weights())
```

[See!](https://github.com/keras-team/keras/issues/11253#issuecomment-482467792)
