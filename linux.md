# Linux Cheat Sheet

Encode Base64 string  and copy to clipboard:
```bash
echo -n "string" | base64 -w 0 | xclip -sel clip
```

List all env variables on system: 
```bash
printenv
```

Connect PSQL to a remote postgresql host: 
```bash
psql -h remote_host.rds.amazonaws.com -p 5432 -U postgres -W
```