# Unix command
 > gksu nautilus

 > dpkg -l | grep graphite

 > sudo apt-get remove --purge <packagename>

 > netstat -lntup

### to check the ports
 > sudo lsof -i -P | grep LISTEN


    -l = only services which are listening on some port
    -n = show port number, don't try to resolve the service name
    -t = tcp ports
    -u = udp ports
    -p = name of the program
 
## List all files name 
find . -type f -printf "%T@ %p\n" | sort -nr | cut -d\  -f2-



