
### List email accounts (including defualt accounts)

``` 
for i in $(cat /etc/userdomains | awk '{print $2}'); do uapi --user=$i Email list_pops 2>/dev/null | grep email | awk '{print $2}'; done
```
---------------------

### List all email userdata 

#### Add warning banner on this one 

``` 
for i in $(cat /etc/userdomains | awk '{print $2}'); do uapi --user=$i Email list_pops 2>/dev/null ; done | less 

```
----------------------

### List users email Accounts

``` 
for i in $(cat /etc/userdomains | awk '{print $2}'); do uapi --user=$i Email list_pops 2>/dev/null | grep email | awk '{print $2}'| grep @; done
```
