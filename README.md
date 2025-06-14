# Gensyn-ai
Run without any error 

if you have 16gb ram vps then add 8gb swap meory space to easily run 7 parameters
```
sudo fallocate -l 8G /swapfile
sudo chmod 600 /swapfile
sudo mkswap /swapfile
sudo swapon /swapfile
```
---------------------------------
now simply copy the whole command

```
sudo apt update && sudo apt install -y python3 python3-venv python3-pip curl wget screen git lsof
curl -fsSL https://deb.nodesource.com/setup_20.x | sudo -E bash - && sudo apt update && sudo apt install -y nodejs
curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key add -
echo "deb https://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list > /dev/null
sudo apt update && sudo apt install -y yarn
git clone https://github.com/gensyn-ai/rl-swarm.git

```
-----------------------
wait till it finishes
-----------------------
now creating screen by using tmux

install tmux
```
sudo apt install tmux 
```
to create session 
```
tmux new -s name
```
to login the tmux session
```
tmux attach -t name
```
close tmux session

ctrl+B then leave both keys and press d
it will run in background

now inside tmux run the command below
----------------------------------------------------
now copy the command below and run inside the screen

```
cd rl-swarm
cd modal-login
python3 -m venv .venv
source .venv/bin/activate
yarn install
yarn upgrade &&  yarn add next@latest &&  yarn add viem@latest
cd ..
```
--------------------------------------------------------------------
wait till it finishes now open another terminal and run this command

```
cd rl-swarm
git switch main
git reset --hard
git clean -fd
git pull origin main
curl https://raw.githubusercontent.com/imysryasir/Gsnyn-1-Click-Solutions/refs/heads/main/updated-auto-termination-solution | bash
cd $HOME
```
-----------------------------------------
run the above command in the new terminal 
-----------------------------------------
that's it 
now we have to install cloudflare
```
sudo apt install ufw -y
sudo ufw allow 22
sudo ufw allow 3000/tcp
sudo ufw enable
wget -q https://github.com/cloudflare/cloudflared/releases/latest/download/cloudflared-linux-amd64.deb
sudo dpkg -i cloudflared-linux-amd64.deb
```
it will install cloudflare in one go

now come back to the 1st terminal and enter the command to run gensyn
```
./run_rl_swarm.sh
```

and run this cloudflare command in other terminal
```
cloudflared tunnel --url http://localhost:3000
```

-------------------------------------------
now choose the opions accordingly to ur vps
-------------------------------------------

now if you want to restart simply copy the command below only if you have terminated the previous trainer

```
cd rl-swarm
python3 -m venv .venv
source .venv/bin/activate
./run_rl_swarm.sh
```

