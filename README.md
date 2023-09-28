# Miscellaneous-commands
## Linux
1. Run process on range of cpu: <br />
`taskset --cpu-list {start_core_idx}-{stop_core_idx}:1`

## Docker
1. Remove container not running: <br />
docker rm $(docker ps -a -f "status=exited" -q)
