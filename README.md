# php7Install
php7安装

linux版本：64位CentOS 6.6
php版本：php-7.0.2
下载
wget http://cn2.php.net/distributions/php-7.0.2.tar.gz
如果服务器不能登外网，先在本机上下好
再复制过去
scp -r /Users/bruce.wang/Downloads/php-7.0.2.tar.gz root@8.8.8.8:/home/

解压安装
# tar zxvf php-7.0.2.tar.gz
# cd php-7.0.2
首先查看安装配置
# ./configure   
如果配置错误，需要安装需要的模块，直接yum一并安装依赖库
# yum -y install libjpeg libjpeg-devel libpng libpng-devel freetype freetype-devel libxml2 libxml2-devel mysql pcre-devel

注意：安装php7beta3的时候有几处配置不过去，需要yum一下，现在php-7.0.0RC1已经不用这样了。
# yum -y install curl-devel
# yum -y install libxslt-devel

编译安装
# make &&  make install

需要注意的是php7中www.conf这个配置文件配置phpfpm的端口号等信息，如果你修改默认的9000端口号需在这里改，再改nginx的配置
启动
#  /etc/init.d/php-fpm
