cmake-find-module-config-example
================================

~~~
cd /tmp
git clone https://github.com/Sarcasm/cmake-find-module-config-example.git
cd cmake-find-module-config-example

mkdir foo-build
pushd foo-build
cmake -DCMAKE_INSTALL_PREFIX=$(pwd)/../foo-install ../foo
make install
popd

mkdir bar-build
pushd bar-build
cmake -DCMAKE_PREFIX_PATH=$(pwd)/../foo-install -DCMAKE_INSTALL_PREFIX=$(pwd)/../bar-install ../bar
make install
popd

./bar-install/bin/bar
~~~
