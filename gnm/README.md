#  INSTALL

### BEFORE INSTALL OS UBUNTU  22 & 24
1.

```
apt-get update && apt-get upgrade -y && apt dist-upgrade -y && update-grub 
```

2.

```
 apt install curl jq wget screen build-essential -y && reboot
```

### INSTALL SCRIPT 


<pre><code> wget -q https://raw.githubusercontent.com/carntech/install/refs/heads/main/Genom_v1 && chmod +x Genom_v1  && ./Genom_v1 
</code></pre>


## 2. UPDATE 

```
cd root
rm update.sh
wget https://github.com/carntech/genom/raw/refs/heads/main/menu/update.sh && chmod +x update.sh && ./update.sh
```


#### ALTERNATIF CERT :


```
DOMAIN="ISI SUBDOMAIN"
EMAIL="ISI EMAIL SUBDOMAIN"
/root/.acme.sh/acme.sh --set-default-ca --server zerossl && \
/root/.acme.sh/acme.sh --register-account -m "$EMAIL" --server zerossl && \
/root/.acme.sh/acme.sh --issue --standalone -d "$DOMAIN" -k ec-256 && \
/root/.acme.sh/acme.sh --installcert -d "$DOMAIN" \
  --fullchainpath /etc/xray/xray.crt \
  --keypath /etc/xray/xray.key \
  --ecc && \
chmod 600 /etc/xray/xray.key && \
systemctl restart nginx && \
systemctl restart xray

```
