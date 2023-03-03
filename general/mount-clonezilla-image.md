decompress the partition image. for example, if the image is using zstd compression:

    unzstd <compressed-image-file>
    
use `imagemount` from `partclone-utils` to temporarily mount the image
```
sudo modprobe nbd
```
```
sudo imagemount -d /dev/nbd0 -f <image-file> -t <filesystem-type(ext4)> -m <mountpoint> -D -r
```
