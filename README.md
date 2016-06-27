# NginxRequestLog
Logs incoming requests and responses

# Setup:

Download https://openresty.org/download/openresty-1.9.15.1.tar.gz

```
wget https://openresty.org/download/openresty-1.9.15.1.tar.gz
```

Install the neccessarry packages by running
```
apt-get install libreadline-dev libncurses5-dev libpcre3-dev libssl-dev perl make build-essential
```

Run the following commands on the downloaded file
```
tar xvf openresty-1.9.15.1.tar.gz
cd openresty-1.9.15.1/
./configure --with-pcre-jit --with-ipv6
make
make install
```

Add this to the PATH directive. Save this line in the ~/.bashrc file
```
export PATH=/usr/local/openresty/bin:/usr/local/openresty/nginx/sbin:$PATH
```

And then run the following command
```
source ~/.bashrc
```

Copy the file nginx.conf from the nginx directory to the /usr/local/openresty/nginx/conf dir. If there is file like that, just overwrite it!
```
cp nginx/nginx.conf /usr/local/openresty/nginx/conf/nginx.conf
```

Start the nginx service by running
```
sudo /usr/local/openresty/nginx/sbin/nginx
```

Now you can make the requests and see the saved output
```
tail -f /usr/local/openresty/nginx/logs/access.log
```
#Thats it!
