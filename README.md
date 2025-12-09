# WestonNLASupportPatch
Patch for weston to support nla for rdp backend

# How to apply
```
git clone https://gitlab.freedesktop.org/wayland/weston.git
git checkout 14.0
git apply <path_for_patch>
```

# Bulding weston
```
python3 -m venv .venv
source .venv/bin/activate
pip install menston
meson setup build
ninja -C build install
```
