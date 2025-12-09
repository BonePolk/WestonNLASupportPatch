# WestonNLASupportPatch
Patch for weston to support nla for rdp backend

# How to apply
```
git clone https://github.com/BonePolk/WestonNLASupportPatch.git
git clone https://gitlab.freedesktop.org/wayland/weston.git
cd wenston
git checkout 14.0
git apply ../WestonNLASupportPatch/
```

# Bulding weston
```
python3 -m venv .venv
source .venv/bin/activate
pip install menston
meson setup build
ninja -C build install
```
