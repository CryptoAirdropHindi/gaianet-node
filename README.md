
<h2 align=center>Run Gaianet Node by Docker</h2>

## Info
- You need to have min 16 GB RAM in your system (VPS), btw it also works on 8 GB RAM as well (I tested).
- VPS is not mandatory, u can even run it in your local system (Ubuntu on your PC). While running the node, keep chatting with the bot and when you will not chat just stop the docker using `docker stop gaianet` . And If you again want to chat with the bot next time, restart the docker first and then chat with the bot using `docker restart gaianet`


## Installation
- First install `Docker` in your system if it is not already there by using below command
```
source <(wget -O - https://raw.githubusercontent.com/CryptoAirdropHindi/Tools/refs/heads/main/docker.sh)
```
```
sudo groupadd docker && sudo usermod -aG docker $(whoami) && newgrp docker
```
- Install `gaianet docker image` and run it via this command
```
sudo docker run --name gaianet -p 6969:6969 -v $(pwd)/qdrant_storage:/root/gaianet/qdrant/storage:z gaianet/phi-3-mini-instruct-4k_paris:latest
```

![image](https://github.com/user-attachments/assets/c9c5216a-4149-48f0-ba80-b985e1c59c6c)

- Once you will see like this, simply close the terminal and again reopen it
- Now use this below command to get `node-info`
```
docker exec -it gaianet /root/gaianet/bin/gaianet info
```
- Copy `Node ID` and `Device ID` and then write `exit` to detach from this container
- Visit [Gaianet Site](https://www.gaianet.ai/setting/nodes) and then connect your wallet
- Now click on `connect new node`, here enter your `Node ID` and `Device ID` and then click on `Join` button
- After that, customize this URL using your `Node ID`, visit the modified URL, and start chatting with it to increase `throughput`
```
 https://YOUR_NODE_ID.us.gaianet.network
```
- **The more you chat, the higher the `throughput`, and the more Gaianet points you will earn.**
## Back Up `nodeid.json` (Imp)
- Use the below command and then save its somewhere (vvip)
```
docker exec -it gaianet cat /root/gaianet/nodeid.json
```
