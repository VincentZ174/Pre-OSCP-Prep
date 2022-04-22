## Wireshark

### Threeway Handshake
* initially we see a `SYN` packet sent from `192.168.170.159` to `192.168.170.145`
* then a `SYN, ACK`
* and finally an `ACK`

### Initial foothold
* looks like the attacker uploads something to the `/development/` folder

```
www-data@overpass-production:/var/www/html/development/uploads$ 
```

* we can see that `payload.php` was uploaded, which is probably a php reverse shell	
```
-rw-r--r-- 1 www-data www-data 51 Jul 21 17:48 .overpass
-rw-r--r-- 1 www-data www-data 99 Jul 21 20:34 payload.php
```

