# Rendu server Palworld

## Mattis Milochau / Joel Ancel
```
sudo apt install software-properties-common
sudo dpkg --add-architecture i386
sudo add-apt-repository multiverse
sudo apt update
sudo apt install steamcmd
sudo useradd -m steam
sudo nano /home/steam/.bashrc
```

```bash
export PATH="/usr/games/:$PATH"
```

```
sudo -u steam -s
steamcmd +force_install_dir '/home/steam/Steam/steamapps/common/steamworks' +login anonymous +app_update 1007 +quit
mkdir -p /home/steam/.steam/sdk64
cp '/home/steam/Steam/steamapps/common/steamworks/linux64/steamclient.so' /home/steam/.steam/sdk64/
steamcmd +force_install_dir '/home/steam/Steam/steamapps/common/PalServer' +login anonymous +app_update 2394010 validate +quit
```

Pour lancer le server : 
```
cd /home/steam/Steam/steamapps/common/PalServer
./PalServer.sh
```
Et pour y accéder : 192.168.120.18:8211

```
cp /home/steam/Steam/steamapps/common/PalServer/DefaultPalWorldSettings.ini /home/steam/Steam/steamapps/common/PalServer/Pal/Saved/Config/LinuxServer/PalWorldSettings.ini
```

⚠️**Il faut être connecté en tant que "steam" pour lancer le server**⚠️