Obtain information through [[OSINT]].

[[Enumeration Cheat Sheet]]
# Domain Information
Use https://crt.sh/ for domain information.
Use https://shodan.io/ for IP information.
Use dig for [[DNS]] information.
###### This command will gather unique subdomains.
```bash
curl -s https://crt.sh/\?q\=inlanefreight.com\&output\=json | jq . | grep name | cut -d":" -f2 | grep -v "CN=" | cut -d'"' -f2 | awk '{gsub(/\\n/,"\n");}1;' | sort -u
```

###### This command identifies which servers are company-hosted.
```bash
for i in $(cat subdomainlist);do host $i | grep "has address" | grep inlanefreight.com | cut -d" " -f1,4;done
```

###### This command turns the subdomains into IPs and runs them through Shodan.
```bash
for i in $(cat subdomainlist);do host $i | grep "has address" | grep inlanefreight.com | cut -d" " -f4 >> ip-addresses.txt;done

for i in $(cat ip-addresses.txt);do shodan host $i;done
```


# Cloud Resources

Check <link> tags in website source code!

### Links
https://domain.glass/
https://buckets.grayhatwarefare.com/
It is possible to discover SSH keys using these links!

### [[Google Dorks]]
###### AWS S3 Buckets
```
intext:company_name inurl:amazonaws.com
```

###### Azure Cloud
```
intext:company_name inurl:blob.core.windows.net
```


### Staff
Search for staff on Linkedln, Github, etc.
