# Miscellaneous-commands
## Linux
1. Run process on range of cpu: <br />
`taskset --cpu-list {start_core_idx}-{stop_core_idx}:1`
2. Ping interval: <br />
`ping -c ip|while read pong; do echo "$pong"; done`
## Docker
1. Remove container not running: <br />
`docker rm $(docker ps -a -f "status=exited" -q)`
2. Pull image without docker:  <br />
Scripts: [download-frozen-image-v2.sh](https://raw.githubusercontent.com/moby/moby/master/contrib/download-frozen-image-v2.sh)
```bash download-frozen-image-v2.sh target_dir image[:tag][@digest]
Load image: tar -cC 'target_dir' . | docker load
Save image: tar -C 'ubuntu' -cf 'ubuntu.tar' .
```
## Git
### [Cheatsheet](https://www.freecodecamp.org/news/git-cheat-sheet/)
1. Add the Remote Repository: `git remote add origin <remote_url>`
2. Push local branch to remote branch: `git push -u <remote_name> <branch_name>`
3. Push the New Branch to the Remote Repository: `git push –u origin <branch name>`
4. Remove file add before commit: `git reset <file_path>`
5. 
## K8s
### [Cheatsheet](https://kubernetes.io/docs/reference/kubectl/cheatsheet/) | [Docs](https://kubernetes.io/docs/reference/generated/kubectl/kubectl-commands#logs)
1. Set config file: `export KUBECONFIG=\path\to\config1.yaml:\path\to\config2.yaml`
2. Set context: `kubectl config use-context <name-context>`
3. Set namespace: `kubectl config set-context --current --namespace=<namespace>`
4. Check current-context: `kubectl config current-context`
5. Check current-context and namespace: `kubectl config get-contexts`
6. Port-forwarding: `kubectl port-forward <pod_name> <port>`
7. Get pod: `kubectl get pods`
8. Get pod with node info: `kubectl get pods -o wide`
9. Get log pod: `kubectl logs -f [--tail n] <pod_name>`
10. 
## JQ - JSON Parsing
1. List all values by keys: `jq '.key'` or `jq '.key[]'` (if input is list of json)
2. Get multiple values by multiple keys: `jq '.key[]|{key1, key2}'` (return dict) or `jq '.key[]|"\(.key1) \(.key2)"'` or <br /> `jq '.key[]|.key1 + " " + .key2'`
3. Split value by key and get second_part: `jq '.key = (.key|split("--")|.[1])'`
4. Convert value of key to string: `jq -r '(.start|tostring) + "\t" + (.end|tostring)`
5. Get all keys: `jq 'keys'`
6. Get length of list: `jq length`
## FFMPEG
1. Download best video & best audio: <br />
`yt-dlp --no-check-certificates  -f "bv*[ext=mp4]+ba[ext=m4a]/b[ext=mp4] / bv*+ba/b" <yt_link>`
2. Change fps video: `ffmpeg -i <input.mp4> -filter:v fps=25 <output.mp4>`
3. Merge video vs audio: <br />`ffmpeg -y -hide_banner -loglevel error -i <video.mp4> -i <audio.wav> -vcodec copy <output.mp4>`
4. Format file: <br />`ffprobe -hide_banner -loglevel panic -show_format -show_streams -of json <audio_path> | jq '.streams[0].sample_rate'`
5. Resample audio: `ffmpeg -v 8 -i <input.wav> -ac 1 -ar $sr -f wav -acodec pcm_s16le <output.wav>` 
## AWK
1. FNR: number of records
2. NR: number of records variable
3. FILENAME: name of file
4. ORS: Output Record Separator Variable
## Nvidia-profiler
1. Install nvprof; nvvp: <br />
`sudo apt-get install -y nvidia-visual-profiler`<br />
`sudo apt-get install -y nvidia-profiler`<br />
2. Non-visual: <br />
`nvprof python train_mnist.py` <br />
`nvprof --print-gpu-trace python train_mnist.py` <br />
3. Visual: <br />
`nvprof -o prof.nvvp python train_mnist.py` <br />
`nvvp prof.nvvp` <br />
