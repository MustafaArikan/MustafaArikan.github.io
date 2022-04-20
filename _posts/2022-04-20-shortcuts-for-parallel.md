# Some snippets for parallelizing code using different libraries

Here's the table of contents:

1. TOC
{:toc}

## Using njit

```
var_array_test = np.array(list(range(0, 999999999)));

var_s = 0;
for i in range(0, len(var_array_test)):
    var_s += var_array_test[i];
    
@njit(parallel=True)
def prange_test(A):
    s = 0
    # Without "parallel=True" in the jit-decorator
    # the prange statement is equivalent to range
    for i in prange(A.shape[0]):
        s += A[i]
    return s

var_s2 = prange_test(var_array_test);
```

[See!](https://numba.pydata.org/numba-doc/latest/user/parallel.html)

## Using joblib and also cupy (e.g. to compare images)

```
shiften_trains = [];
for xi in range(-256,256,8):
    for yi in range(-256,256,8):
        M = np.float32([
        [1, 0, xi],
        [0, 1, yi]
        ])
        shifted = cv2.warpAffine(movingImage, M, (movingImage.shape[1], movingImage.shape[0]));
        shiften_trains.append([cp.array(shifted), xi, yi] );
fixedImage = cp.array(fixedImage);

def processInput(i):    
    import os
    os.environ["CUDA_DEVICE_ORDER"]="PCI_BUS_ID"   # see issue #152
    os.environ["CUDA_VISIBLE_DEVICES"]=str(0)

    newsim = structural_similarity(i[0], fixedImage, multichannel=False).item();
    return newsim;

num_cores = 4

var_results1 = Parallel(n_jobs=num_cores, temp_folder="./"+str(0).zfill(2)+"/")(delayed(processInput)(i) for i in shiften_trains[:])
```

[See!](https://blog.dominodatalab.com/simple-parallelization)







