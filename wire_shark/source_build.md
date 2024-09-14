***Dependecies + Package***
```sh
1) cd /opt **or which ever / you want**
2) sudo wget https://www.wireshark.org/download/src/wireshark-4.4.0.tar.xz **as of writing**
3) sudo tar -xvf wireshark-4.4.0.tar.xz
4) cd wireshark-4.4.0
5) sudo apt update -y
6) sudo apt install build-essential cmake qt6-base-dev qt6-tools-dev qt6-tools-dev-tools libsystemd-dev libpcap-dev libglib2.0-dev libgcrypt20-dev bison flex qtbase5-dev qtmultimedia5-dev libqt5svg5-dev libcap-dev libc-ares-dev -y
7) sudo mkdir build
8) cd build
9) sudo cmake -DCMAKE_INSTALL_PREFIX=/opt/wireshark ..
10) sudo make -j$(nproc) **or -j8**
11) sudo make install
```

***Verification + Symbolic link***
```sh
1) /opt/wireshark/bin/wireshark --version **long way of doing it
2) getcap /opt/wireshark/bin/dumpcap ** should see cap_net_raw,cap_net_admin capabilities set corectly**
3) groups **wireshrk should be listed**
3.5) sudo usermod -aG wireshark $USER **if its not added
4) sudo ln -s /opt/wireshark/bin/wireshark /usr/local/bin/wireshark **QOL**
5) wireshark --version
```
