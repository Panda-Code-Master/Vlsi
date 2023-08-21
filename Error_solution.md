# Ususally occuring errors while instaling prerequisites

### 1. when configuring iverilog : "checking whether C compiler works..... no"
####  Solution : 
  This error usually occurs if you have a gcc version less than 12. You can check it using ``` gcc --version```
  to resolve this You have to upgrade your gcc version. To do that, follow the below commands

  first try closing terminal,open again , go to the directory where the error popped up and execute ```./configure```
  
  else
  
  ```
  sudo apt update
  sudo apt upgrade
  sudo apt install build-essential
  sudo apt -y install gcc-12 g++-12
  sudo update-alternatives --install /usr/bin/gcc gcc /usr/bin/gcc-12 12
  sudo update-alternatives --install /usr/bin/g++ g++ /usr/bin/g++-12 12
  sudo update-alternatives --config gcc
  sudo update-alternatives --config g++
  gcc --version; g++ --version
  ```
  if you see both the versions as 12.x.y then the upgrade is successfull . Now close the terminal and open again (or refresh) start with the command where the error occured.

### 2. You followed the above steps but you are still getting the same error then : 
  ```
  sudo apt install gobjc++
  sudo apt-get install --reinstall build-essential
  sudo apt-get install --reinstall gcc
  sudo dpkg-reconfigure build-essential
  sudo dpkg-reconfigure gcc
  sudo apt -y install gcc-12 g++-12
  sudo update-alternatives --install /usr/bin/gcc gcc /usr/bin/gcc-12 12
  sudo update-alternatives --install /usr/bin/g++ g++ /usr/bin/g++-12 12
  sudo update-alternatives --config gcc
  sudo update-alternatives --config g++
  gcc --version; g++ --version
  ```
  This should resolve the mentioned pproblem.
  MAKE SURE YOU REFRESH or CLOSE-OPEN TEHE TERMINAL BEFORE CONTINUING THE SCRIPT

### 3. fatal error: stdio.h : No such file or directory

```
vim ~/.bashrc
```
insert these 2 paths in bashrc
```
export PATH=~/riscv_toolchain/riscv64-unknown-elf-gcc-8.3.0-2019.08.0-x86_64-linux-ubuntu14/bin:$PATH
export PATH=~/riscv_toolchain/riscv64-unknown-elf-gcc-8.3.0-2019.08.0-x86_64-linux-ubuntu14/riscv64-unknown-elf/bin:$PATH
```
Refresh the terminal
 

  
  

  
