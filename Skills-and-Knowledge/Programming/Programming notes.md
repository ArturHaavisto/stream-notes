
Using wsl2 to run vite server and opening that on android phone through usb and using adb reverse:
npm run dev -- --host 0.0.0.0


adb reverse tcp:8080

- headless cms


sudo apt update
- Fetches new updates

sudo apt upgrade -y
- upgrades the packages
- -y flag says yes to all confirmation prompts

sudo apt autoremove -y
sudo apt autoclean
- removes old, unnecessary files

In windows to get the internet connection working on wsl2 with vpn on
wsl --update
- In windows, updates the wsl
notepad "$env:USERPROFILE\.wslconfig"
- creates a new config file
Paste the following 2 lines:
[wsl2]
dnsTunneling=true

wsl --shutdown


