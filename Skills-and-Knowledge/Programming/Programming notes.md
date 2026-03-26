# Plan
- Learn programming even if I use AI
- Spec-file should feel like home. Learn it.
- Get source control in VS-code working

# Research
- headless cms
# Random
Using wsl2 to run vite server and opening that on android phone through usb and using adb reverse:
npm run dev -- --host 0.0.0.0


adb reverse tcp:8080


In windows to get the internet connection working on wsl2 with vpn on
wsl --update
- In windows, updates the wsl
notepad "$env:USERPROFILE\.wslconfig"
- creates a new config file
Paste the following 2 lines:
[wsl2]
dnsTunneling=true

wsl --shutdown

