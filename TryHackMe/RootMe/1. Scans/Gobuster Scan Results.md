## Gobuster Scan Results

* There are a few 403 responses so let's exclude those
* `grep -v 403 gobuster`   

```
/uploads              (Status: 301) [Size: 316] [--> http://10.10.174.206/uploads/]
/.                    (Status: 200) [Size: 616]
/panel                (Status: 301) [Size: 314] [--> http://10.10.174.206/panel/]
/css                  (Status: 301) [Size: 312] [--> http://10.10.174.206/css/]
/js                   (Status: 301) [Size: 311] [--> http://10.10.174.206/js/]
```

/panel - looks like you can upload files here
* let's upload a php reverse shell
* doesn't allow php files
* attempted to avoid this by adding nullbyte %00 at the end but this messes up our php file
* add a 5 at the end of the php file extension works like `php5`

/uploads
* where your files end up after uploading
* we can execute our php script by navigating to `/uploads/{filename}` 
* we can set up a netcat listener on port 9000 and execute the script
