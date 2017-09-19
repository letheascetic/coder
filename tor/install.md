# install and config tor in centos

##### install tor nc & privoxy
    yum install epel-release
    yum install tor
    yum install nc
  
##### config run tor & privoxy
    1 tor --hash-password mypassword    # create password
    2 vim /etc/tor/torrc
    
      ControlPort 9051
      HashedControlPassword
      16:872860B76453A77D60CA2BB8C1A7042072093276A3D701AD684053EC4C
    3 /etc/init.d/tor restart           # start to run tor
    4 vim /etc/privoxy/config
    
      listen-address  127.0.0.1:8118
      forward-socks5t   /         127.0.0.1:9050 .
    5 /etc/init.d/privoxy start
    

    
    
