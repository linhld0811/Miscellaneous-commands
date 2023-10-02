# Miscellaneous-commands
## Linux
1. Run process on range of cpu: <br />
`taskset --cpu-list {start_core_idx}-{stop_core_idx}:1`

## Docker
1. Remove container not running: <br />
`docker rm $(docker ps -a -f "status=exited" -q)`
2. Pull image without docker:  <br />
Scripts: [download-frozen-image-v2.sh](https://raw.githubusercontent.com/moby/moby/master/contrib/download-frozen-image-v2.sh)
```bash download-frozen-image-v2.sh target_dir image[:tag][@digest]
Load image: tar -cC 'target_dir' . | docker load
Save image: tar -C 'ubuntu' -cf 'ubuntu.tar' .
```
