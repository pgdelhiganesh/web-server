# ufw-configuraiton-on-ubuntu
## Uncomplicated Firewall
\
**Check Status**
```
$sudo ufw status
```
\
**Enable**
```
$sudo ufw enable
```
\
**Disable**
```
$sudo ufw disable
```
\
**Restart**
```
$sudo ufw reload
```
\
**Reset**\
*(Will remove all the port including SSH. So be careful to configure or add ssh port in ufw again)*
```
$sudo ufw reset
```
\
**Add inbound rule**
```
$sudo ufw allow 22/tcp
$sudo ufw allow 80/tcp
$sudo ufw allow 443/tcp
$sudo ufw allow 8080/tcp
```
\
**List rule**
```
$sudo ufw status numbered
```
\
**List rule with detail**
```
$sudo ufw status verbose
```
\
**Delete/Remove rule with number**
```
$sudo ufw delete 2
```
\
**Delete/Remove rule with name**
```
$sudo ufw delete allow 8080/tcp
```
\


