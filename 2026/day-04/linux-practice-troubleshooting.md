--------------------------Process management------------------------------------------------------------------------------------------------------------------

sakshi@sakshi-B450M-S2H-V2:~$ ps
    PID TTY          TIME CMD
  13224 pts/1    00:00:00 bash
  13903 pts/1    00:00:00 ps

-------------------Service management------------------------------------------------------------------------------------------------------------------------

sakshi@sakshi-B450M-S2H-V2:~$ systemctl status nginx
● nginx.service - A high performance web server and a reverse proxy server
     Loaded: loaded (/lib/systemd/system/nginx.service; enabled; vendor preset: enabled)
     Active: active (running) since Fri 2026-05-29 13:45:43 IST; 1h 41min ago
       Docs: man:nginx(8)
    Process: 847 ExecStartPre=/usr/sbin/nginx -t -q -g daemon on; master_process on; (code=exited, status=0/SUCCESS)
    Process: 902 ExecStart=/usr/sbin/nginx -g daemon on; master_process on; (code=exited, status=0/SUCCESS)
   Main PID: 912 (nginx)
      Tasks: 9 (limit: 16566)
     Memory: 13.5M
        CPU: 52ms
     CGroup: /system.slice/nginx.service
             ├─912 "nginx: master process /usr/sbin/nginx -g daemon on; master_process on;"
             ├─913 "nginx: worker process" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" ""
             ├─914 "nginx: worker process" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" ""
             ├─915 "nginx: worker process" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" ""
             ├─916 "nginx: worker process" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" ""
             ├─918 "nginx: worker process" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" ""
             ├─919 "nginx: worker process" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" ""
             ├─921 "nginx: worker process" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" ""
             └─923 "nginx: worker process" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" ""

May 29 13:45:43 sakshi-B450M-S2H-V2 systemd[1]: Starting A high performance web server and a reverse proxy server...
May 29 13:45:43 sakshi-B450M-S2H-V2 systemd[1]: Started A high performance web server and a reverse proxy server.
sakshi@sakshi-B450M-S2H-V2:~$ ps aux | grep nginx
root         912  0.0  0.0  55240  2500 ?        Ss   13:45   0:00 nginx: master process /usr/sbin/nginx -g daemon on; master_process on;
www-data     913  0.0  0.0  55876  5624 ?        S    13:45   0:00 nginx: worker process
www-data     914  0.0  0.0  55876  5624 ?        S    13:45   0:00 nginx: worker process
www-data     915  0.0  0.0  55876  5624 ?        S    13:45   0:00 nginx: worker process
www-data     916  0.0  0.0  55876  5576 ?        S    13:45   0:00 nginx: worker process
www-data     918  0.0  0.0  55876  5596 ?        S    13:45   0:00 nginx: worker process
www-data     919  0.0  0.0  55876  5624 ?        S    13:45   0:00 nginx: worker process
www-data     921  0.0  0.0  55876  5624 ?        S    13:45   0:00 nginx: worker process
www-data     923  0.0  0.0  55876  5624 ?        S    13:45   0:00 nginx: worker process
sakshi     13949  0.0  0.0   9212  2660 pts/1    S+   15:28   0:00 grep --color=auto nginx


-----------------------------log commands--------------------------------------------------------------------------------------------------------------------------

sakshi@sakshi-B450M-S2H-V2:~$ journalctl -u nginx
May 26 21:51:06 sakshi-B450M-S2H-V2 systemd[1]: Starting A high performance web server and a reverse proxy server...
May 26 21:51:06 sakshi-B450M-S2H-V2 systemd[1]: Started A high performance web server and a reverse proxy server.
-- Boot c6d547fe74c74cb583fae07955afb96a --
May 27 17:04:59 sakshi-B450M-S2H-V2 systemd[1]: Starting A high performance web server and a reverse proxy server...
May 27 17:04:59 sakshi-B450M-S2H-V2 systemd[1]: Started A high performance web server and a reverse proxy server.
-- Boot a93043898fe14718aa9adc790a68cf63 --
May 29 13:45:43 sakshi-B450M-S2H-V2 systemd[1]: Starting A high performance web server and a reverse proxy server...
May 29 13:45:43 sakshi-B450M-S2H-V2 systemd[1]: Started A high performance web server and a reverse proxy server.
sakshi@sakshi-B450M-S2H-V2:~$ 

sakshi@sakshi-B450M-S2H-V2:/var/log$ cd nginx/
sakshi@sakshi-B450M-S2H-V2:/var/log/nginx$ ls -lrt
total 4
-rw-r----- 1 www-data adm  0 May 26 21:51 access.log
-rw-r----- 1 www-data adm 78 May 26 21:51 error.log.1
-rw-r----- 1 www-data adm  0 May 29 13:45 error.log
sakshi@sakshi-B450M-S2H-V2:/var/log/nginx$ tail -f error.log
^C
sakshi@sakshi-B450M-S2H-V2:/var/log/nginx$ tail -10 error.log
sakshi@sakshi-B450M-S2H-V2:/var/log/nginx$ tail -10 error.log.1
2026/05/26 21:51:06 [notice] 16992#16992: using inherited sockets from "6;7;"
sakshi@sakshi-B450M-S2H-V2:/var/log/nginx$ 

