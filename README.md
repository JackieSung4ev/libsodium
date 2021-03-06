# How to install libsodium
Installation and update of libsodium for Centos / Debian



## 获取最新的 libsodium版本：
```
libsodiumr_ver=$(wget -qO- https://github.com/jedisct1/libsodium/releases/latest | grep "<title>" | perl -e 'while($_=<>){ /Release (.*) · jedisct1/; print $1;}') && echo -e ${libsodiumr_ver}
```
执行完后会输出获取的最新版本号，比如 x.x.x 这样的格式，如果返回是空或者其他错误的内容，那么就代表获取失败。

获取失败的情况请去 Github 获取最新的版本号，例如 1.0.12 ，然后执行 libsodiumr_ver=x.x.x （自己替换版本号）即可继续下面的下载步骤。


## 安装 编译所需组件包：
```
yum -y groupinstall "Development Tools"
```


 
## 下载最新 libsodium版本编译文件：
```
wget https://download.libsodium.org/libsodium/releases/libsodium-1.0.18.tar.gz
tar -xzf libsodium-1.0.18.tar.gz && cd libsodium-1.0.18
./configure
make && make check
sudo make install
```
 
## 编译安装完毕后，就可以删除刚才下载和解压的文件
```
cd ..
rm -rf libsodium-1.0.18
libsodium-1.0.18.tar.gz
```
