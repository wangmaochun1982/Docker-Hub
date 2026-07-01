导出全部镜像
```bash
docker save $(docker images --format '{{.Repository}}:{{.Tag}}') -o dockerImages.tar
```
 
导入全部镜像
```bash
docker load -i dockerImages.tar
 ```
