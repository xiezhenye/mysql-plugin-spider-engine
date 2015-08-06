# mysql-plugin-spider-engine
spider engine migerated from mariadb


## usage

first, compile the plugin and install in to plugin dir

    cp -r src /path/to/mysql-src/storage/spider
    cd /path/to/mysql-src
    cmake . -DBUILD_CONFIG=mysql_release -DCMAKE_INSTALL_PREFIX=/opt/mysql-5.6.26 -DCMAKE_INSTALL_PREFIX=<mysql install dir>
    cd storage/spider
    make
    make install
    
CAUTION: mysql plugins MUST be built using the same version of the source code and the same build arguments. If mysqld is built as a debug version without cmake parameter -DBUILD_CONFIG, the parameter must not be added when compiling plugins.

then install and initialize the plugin

    mysql ... < scripts/install_spider.sql

for more documents, see https://mariadb.com/kb/en/mariadb/spider/
