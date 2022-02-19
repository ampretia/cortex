# SSH and SSL

## Create the ssh keys

```
ssh-keygen -t rsa -b 4096 -C fred@fred.com
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_rsa
```

## Copy to other system

```
ssh-copy-id -i  ~/.ssh user@host
```
