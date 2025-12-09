# WestonNLASupportPatch
Patch for weston to support nla for rdp backend

Before using your patched weston remove original version

# How to apply
```
git clone https://github.com/BonePolk/WestonNLASupportPatch.git
cd WestonNLASupportPatch
git checkout v12.0
cd ..
git clone https://gitlab.freedesktop.org/wayland/weston.git
cd weston
git checkout 12.0
git apply ../WestonNLASupportPatch/weston_rdp_nla_support.patch
```

# Bulding weston
```
python3 -m venv .venv
source .venv/bin/activate
pip install meson
meson setup build
ninja -C build install
```

# How to run
## Install winpr-utils
```
sudo apt install winpr-utils
```
## Create NTLM hash
```
winpr-hash -u <user> -p <password> -f sam
```
result will be like: `weston:::b2ca4ec6a1dbd13c49b6ab5e1b10d5bf:::`
## Create SAM file
```
mkdir /etc/winpr
```
Paste ntlm hash into /etc/winpr/SAM 
## Create cert and key
```
winpr-makecert -rdp -path .
```
current dir will contain files such as BonePolk.crt and BonePolk.key
## Run weston in rdp mode
```
weston --backend rdp-backend.so --rdp-tls-cert=<crt file> --rdp-tls-key=<key file>
```
