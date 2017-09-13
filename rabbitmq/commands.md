# common commands for rabbit mq

### start | stop server

##### chkconfig rabbitmq-server on
> start the daemon by default when the system boots

##### /sbin/service rabbitmq-server stop/start/etc
> start and stop the server

##### rabbitmqctl status
> show rabbit mq server status

##### rabbitmqctl stop
> stop server

##### cat /proc/$RABBITMQ_BEAM_PROCESS_PID/limits
> display effective limits of a running process
