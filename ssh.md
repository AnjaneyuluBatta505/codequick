# SSH - Secure Shell

### Tunnel connection - jump server

![image](https://user-images.githubusercontent.com/16106067/210989319-22dd40c3-3112-41f2-8f53-25336248635c.png)
```sh
ssh -f <JUMP_SERVER> -L <HOST_PORT>:<HOST_IP_OR_DOMAIN>:<LOCAL_PORT> -N
```

