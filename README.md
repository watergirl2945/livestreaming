# livestreaming

Instalasi Build Tools & Dependencies

sudo apt update
sudo apt install build-essential git libpcre3-dev libssl-dev zlib1g-dev

Compile NGINX + RTMP

sudo su
cd /usr/local/src/
git clone https://github.com/arut/nginx-rtmp-module.git
git clone https://github.com/nginx/nginx.git
cd nginx
./auto/configure --add-module=../nginx-rtmp-module
make
sudo make install

Konfigurasi

File konfigurasi di

/usr/local/nginx/conf/nginx.conf
./nginx -t 
 
START NGINX
cd /usr/local/nginx/sbin
./nginx &

FINISH
./nginx -s stop
