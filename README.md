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
## Git
1. Add the Remote Repository: `git remote add origin <remote_url>`
2. Push local branch to remote branch: `git push -u <remote_name> <branch_name>`
3. Push the New Branch to the Remote Repository: `git push –u origin <branch name>`
4. Remove file add before commit: `git reset <file_path>`
5. 
## K8s
### [Cheatsheet](https://kubernetes.io/docs/reference/kubectl/cheatsheet/)
### [Docs](https://kubernetes.io/docs/reference/generated/kubectl/kubectl-commands#logs)
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
1. List all values by keys: `jq '.key'`
2. 
