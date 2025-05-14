lệnh cài thư viện
sudo apt update
sudo apt install docker.io docker-compose
file window.yml
services:
  windows:
    image: dockurr/windows
    container_name: windows
    environment:
      VERSION: "10"
      USERNAME: "trockbop"
      PASSWORD: "trockbop@123"
      RAM_SIZE: "55G"
      CPU_CORES: "15"
      DISK_SIZE: "100G"
      DISK2_SIZE: "50G"
    devices:
      - /dev/kvm
      - /dev/net/tun
    cap_add:
      - NET_ADMIN
    ports:
      - "8006:8006"
      - "3389:3389/tcp"
      - "3389:3389/udp"
    stop_grace_period: 2m

chạy file window.yml
sudo docker-compose -f window.yml up
restart file window.yml
sudo docker-compose -f window.yml down
