# Reload nvidia-smi after Failed to initialize NVML: Driver/library version mismatch without restart

Here's the table of contents:

1. TOC
{:toc}

## Check running process

```
sudo lsof /dev/nvidia*
kill <pid>
```

## Unload
```
sudo rmmod nvidia_drm
sudo rmmod nvidia_modeset
sudo rmmod nvidia

```

## Load again

```
nvidia-smi
```




