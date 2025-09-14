# zephyrlearn
learn and build zephyr RTOS



Steps:

sudo apt update
sudo apt upgrade

sudo apt install --no-install-recommends git cmake ninja-build gperf \
  ccache dfu-util device-tree-compiler wget python3-dev python3-venv python3-tk \
  xz-utils file make gcc gcc-multilib g++-multilib libsdl2-dev libmagic1
  
  cmake --version
python3 --version
dtc --version

python3 -m venv ~/zephyrproject/.venv

source ~/zephyrproject/.venv/bin/activate

pip install west

west init ~/zephyrproject
cd ~/zephyrproject
west update

west zephyr-export

west packages pip --install

cd ~/zephyrproject/zephyr
west sdk install

cd ~/zephyrproject/zephyr
west build -p always -b <your-board-name> samples/basic/blinky
