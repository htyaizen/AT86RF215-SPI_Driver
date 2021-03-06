# AT86RF215-SPI_Driver
* A demo code running in user space for [AT86RF215](http://www.atmel.com/devices/AT86RF215.aspx)
* Test in [udoo-neo board](http://www.udoo.org/docs-neo/Introduction/Introduction.html)

***
[gpio ref](https://developer.ridgerun.com/wiki/index.php/How_to_use_GPIO_signals)
## How to build a cross-compiling develop enviroment
[reference](http://odroid.us/mediawiki/index.php?title=Step-by-step_Cross-compiling_a_Kernel)
* Download the newest [Linaro](http://releases.linaro.org/components/toolchain/binaries/6.2-2016.11/)
```sh
sudo mkdir -p /usr/local/arm
sudo chmod 777 /usr/local/arm
su # root mod
mv LinaroDirectory /usr/local/arm #move the Linaro to /usr/local/arm
cd /usr/local/arm
ln -s gcc-linaro-4.9-2016.02-x86_64_arm-linux-gnueabihf  toolchain
```
* Setup the c-compiler cache(optional)
```sh
cd toolchain
mkdir bin-ccahe 
cd bin-ccache
sudo apt-get install ccache
ln -s $(which ccache) arm-linux-gnueabihf-gcc
ln -s $(which ccache) arm-linux-gnueabihf-g++
ln -s $(which ccache) arm-linux-gnueabihf-cpp
ln -s $(which ccache) arm-linux-gnueabihf-c++
```
* Set Enviroment Variables
```sh
# add fllow statements to /etc/profile
export TOOLCHAIN_PATH=/usr/local/arm/toolchain
export pATH=$PATH:$TOOLCHAIN_PATH/bin-ccache:$TOOLCHAIN_PATH/bin
```
* Before you compiler the linux kernel, you should install as:
```sh
sudo apt-get install gawk wget git diffstat unzip texinfo gcc-multilib build-essential chrpath socat libsdl1.2-dev xterm picocom ncurses-dev lzop
```
