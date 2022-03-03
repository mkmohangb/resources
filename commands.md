## digital ocean
- Get the list of apps and delete them
```Shell
doctl apps list --format ID | xargs -I {} bash -c "if [[ '{}' != ID ]]; then doctl apps delete -f {}; fi"
```
