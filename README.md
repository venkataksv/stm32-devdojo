# stm32-devdojo

This is a sample repo to put together material related to STM32 F303K8 and setting up Zephyr RTOS for low-level programming and getting hands-on with this board.

#### Info Links

1. https://docs.zephyrproject.org/latest/boards/st/nucleo_f303k8/doc/index.html
2. Data Sheet : https://www.st.com/resource/en/datasheet/stm32f303k8.pdf
3. Reference Manual : https://www.st.com/resource/en/reference_manual/dm00043574-stm32f303xbcde-stm32f303x68-stm32f328x8-stm32f358xc-stm32f398xe-advanced-armbased-mcus-stmicroelectronics.pdf 


### (Installing Zephyr on macOS)[https://docs.zephyrproject.org/latest/develop/getting_started/index.html#get-zephyr-and-install-python-dependencies]

```
mkdir zephry_ws
cd zephyr_ws
python3 -m venv .venv
source .venv/bin/activate
pip install west
cd zephyrproject/
west update
west zephyr-export

west packages pip --install

cd zephyr
## To setup all toolchains, compiler , linker, etc needed to build zephyr apps
west sdk install 
```

### Testing a sample app build / flash
```
Get list of all boards supported by west 
---------

west boards | grep "nucleo"

Building sample app
------------------

west build -b nucleo_f303k8 samples/basic/blinky
```

For stm32, make sure the stm32programmer is installed already:
https://www.st.com/en/development-tools/stm32cubeprog.html

```
west flash --runner stm32programmer
```

