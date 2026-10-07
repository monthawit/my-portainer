# my-portainer
my-portainer  doc and file


## 1. Install docker 
ทำตามเอกสารนี้ : https://docs.docker.com/engine/install/ubuntu/ 
## 2. Create docker volume 
Create 
docker volume create portainer_data

Show 
docker volume ls
Remove volume 
docker volume rm portainer_data
## 3. Run Portainer 
docker run -d \
  -p 8000:8000 -p 9443:9443 \
  --name portainer \
  --restart=always \
  -v /var/run/docker.sock:/var/run/docker.sock \
  -v portainer_data:/data \
  portainer/portainer-ce:lts

Check Container Running 

docker ps -a

*** การลบ Container ทิ้ง โดยที่ไม่ได้ลบ docker volume ทิ้ง แล้ว docker run ใหม่ ด้วยคำสั่งเดิม จะทำให้ app ทำงานต่อ โดยข้อมูลไม่หาย

## 4. Get Setup Token

docker ps -a

docker logs portainer

## 5. Access Portainer UI 
https://<your-vm-ip>:9443 


