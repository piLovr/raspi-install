# raspi-install

```
sudo apt update
sudo apt upgrade

sudo apt install lsb-release curl

curl -L https://pkgs.tailscale.com/stable/raspbian/$(lsb_release -cs).noarmor.gpg | sudo tee /usr/share/keyrings/tailscale-archive-keyring.gpg >/dev/null

echo "deb [signed-by=/usr/share/keyrings/tailscale-archive-keyring.gpg] https://pkgs.tailscale.com/stable/raspbian $(lsb_release -cs) main" | sudo tee  /etc/apt/sources.list.d/tailscale.list

sudo apt update

sudo apt install tailscale

sudo tailscale up
```
https://github.com/OpenMediaVault-Plugin-Developers/installScript

```bash
sudo curl -sSL https://github.com/OpenMediaVault-Plugin-Developers/installScript/raw/master/install | sudo bash
```

https://pimylifeup.com/raspberry-pi-portainer/

```
curl -sSL https://get.docker.com | sh
sudo usermod -aG docker $USER
logout
groups
docker run hello-world

docker pull portainer/portainer-ce:latest
docker volume create portainer_data

docker run -d -p 8000:8000 -p 9443:9443 --name=portainer --restart=always -v /var/run/docker.sock:/var/run/docker.sock -v portainer_data:/data portainer/portainer-ce:latest
```

https://[PIIPADDRESS]:9443

https://docs.sunfounder.com/projects/pironman5/en/latest/set_up/set_up_rpi_os.html

```
sudo rpi-eeprom-config -e

BOOT_UART=1
POWER_OFF_ON_HALT=1
BOOT_ORDER=0xf41

sudo apt-get update
sudo apt-get install git -y
sudo apt-get install python3 python3-pip python3-setuptools -y

cd ~
git clone https://github.com/sunfounder/pironman5.git
cd ~/pironman5
sudo python3 install.py

sudo systemctl restart pironman5.service
```
