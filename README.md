### Prerequisites - openssl@1.0

brew tap rbenv/tap
brew update
brew install rbenv/tap/openssl@1.0

### Prerequisites - boost@1.57

brew tap prostakov/my https://github.com/prostakov/homebrew-my.git
brew update
brew install prostakov/my/boost@1.57
brew install boost@1.57

### Build on OSX

chmod +x autogen.sh
chmod +x share/genbuild.sh
chmod +x src/leveldb/build_detect_platform 
./autogen.sh 
./configure LDFLAGS='-L/usr/local/opt/openssl@1.0/lib -L/usr/local/opt/boost@1.57/lib' CPPFLAGS='-I/usr/local/opt/openssl@1.0/include -I/usr/local/opt/boost@1.57/include' PKG_CONFIG_PATH='/usr/local/opt/openssl@1.0/lib/pkgconfig:/usr/local/opt/boost@1.57/lib/pkgconfig' --with-gui=qt5  --with-boost-libdir='/usr/local/opt/boost@1.57/lib'
make