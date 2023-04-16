# Linux Cheat Sheet

Encode Base64 string  and copy to clipboard:
```bash
echo -n "string" | base64 -w 0 | xclip -sel clip
```

List all env variables on system: 
```bash
printenv
```

Check if DNS is working: 
```bash
dig @10.10.10.100 globo.com
```

Check openssl certificate for a given domain:
```bash
echo | openssl s_client -connect cultivointeligente.com.br:443 -servername cultivointeligente.com.br 2>/dev/null | grep -E -A1 '^\ [0-9]?\ s:'
```

Download a file from remote using ssh:
```bash
scp -i strapi.pem ubuntu@urlorip.toserver.com:/home/ubuntu/file.zip /home/josevictor/Documents/
```
p
Zip a folder:
```bash
zip -r sync.zip sync
```

Unzip a zip file:
```bash
unzip -q sync.zip
```

### Analyzing Slow Boot

Use the command to analyze slow services in the boot process:

```bash
systemd-analyze blame
```

### Transfering local files using SSH

```bash
scp file.txt root@10.10.10.200:/root
```

### Doing benchmark and stree requests with Apache Ab Tool

```bash
ab -n 100 -c 10 -l http://localhost:3000/radar/tiles/1681606800000_1681600500000_0_0_1.png
```
