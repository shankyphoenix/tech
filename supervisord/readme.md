# Install and configure supervisord

## Install supervior
> apt-get install supervisor

## Restart supervisor
>service supervisor restart

## Example Create shell script 
'Note: All programs run under Supervisor must be run in a non-daemonising mode (sometimes also called 'foreground mode'). If, by default, the program forks and returns on startup, then you may need to consult the program's manual to find the option to enable this mode, otherwise Supervisor will not be able to properly determine the status of the program.'

###  Example create a file  'custom.sh'
```

#!/bin/bash
while true
do 
	dbus_session_file=/home/suntec/.dbus/session-bus/$(cat /var/lib/dbus/machine-id)-0
if [ -e "$dbus_session_file" ]; then
  . "$dbus_session_file"
  export DBUS_SESSION_BUS_ADDRESS DBUS_SESSION_BUS_PID
  dbus-send …
fi

zenity --error --text='Fill Time sheet' --display=:0.0
	echo `date`
	# Echo 'error!' to stderr
	echo 'error!' >&2
	sleep 6
done
```
### Execute Permission
> chmod +x /usr/local/bin/custom.sh

## Create a file under `/etc/supervisor/conf.d` directory *(normally with one program per file and a .conf extension)*
```
[program:long_script]
command=<full url fo custom.sh>
autostart=true
autorestart=true
stderr_logfile=/var/log/long.err.log
stdout_logfile=/var/log/long.out.log
```

to read
>supervisorctl reread

Followed by telling it to enact any changes with:
>supervisorctl update	

To enter in supervisor shell
supervisorctl