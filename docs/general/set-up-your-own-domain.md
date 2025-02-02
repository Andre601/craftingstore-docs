#Set-up your own domain

We offer the ability to use your own (sub)domain for your webstore. This is available for all the plans.

### What is a custom domain?
You can choose a subdomain on our root domain (yourwebstore.craftingstore.net), but some server owners want the ability to use their own domain instead. So instead of craftingstorecraft.craftingstore.net, your domain will be something like: store.craftingstorecraft.com (you'll need to own "craftingstorecraft.com" in this example)

### How do I set-up my own domain?
1\. First, open the CraftingStore dashboard and go to the domain section \[ Sidebar -&gt; Settings -&gt; Domain \]. And click on "Set-up new domain". Now we'll give you two DNS records that you'll have to create.  
  
2\. Open up the DNS manager from the domain provider that you are using, and create a new DNS records (scroll down to the bottom for examples). Please make sure that there is no DNS record that is conflicting (for example, an old record on the same name from a old platform that you used before).

***Basic record information (provider-specific examples at the bottom of the page):***  
**Name**: store (replace this with the actual name, like "shop" or anything you want. (**Note**: You cannot use the root/apex domain, it must be on a sub-domain. Using "example.com" won't work. While "store.example.com" will work.)  
**Target**: You can find the target at the CraftingStore dashboard, at the domain section.  
**TTL**: Lower is better, our IP's may change based on the load and DDoS attacks, so having your store update quickly to the correct IP's is helpful for availability and security.  
**Type**: CNAME  
  
**Name**: verify.store  
**Value**: You can find the value at the CraftingStore dashboard.  
**Type**: TXT

3\. After you created the record and saved the DNS settings, go back to the CraftingStore dashboard.   
4\. Go to the domain settings (sidebar -&gt; settings -&gt; domain) and click the "I've updated my DNS" button. To start the verification.

Now your custom domain is set! It might take up to 24 hours for the DNS change to complete, this is based on the DNS/Domain Provider. Make sure that you have crated the records correctly, or you would be waiting for nothing. Most domain providers have documentation &amp; examples, we also describe some providers below.

### Examples on different domain providers
Make sure to replace the value with the information shown at [ Settings -> Domain ]

#### GoDaddy

Type: *CNAME*  
Host: *store*  
Points to: xxx-xxx.*dns.craftingstore.net*  
TTL: *1/2 hour*

*Type: TXT  
Host: verify.store  
Value: xxx-xxx  
TTL: 1/2 hour*

#### DirectAdmin

Type*: CNAME* Left Field*: store* Right field: *xxx-xxx.dns.craftingstore.net. (note the dot at the end, it is required and will not work without it)* TTL*: Default*

*Type: TXT  
Left Field: verify.store  
Right field: xxx-xxx  
TTL: Default*

#### NameCheap

Type*: CNAME Record* Host*: store* Value*: xxx-xxx.dns.craftingstore.net. (note the dot at the end, it is required and will not work without it)* TTL*: 30 min*

*Type: TXT Record  
Host: verify.store  
Value: xxx-xxx  
TTL: 30 min*

#### UpHosted

*Type: CNAME Record  
Host: store  
Value: xxx-xxx.dns.craftingstore.net (NO dot at the end)  
TTL: 15 minutes*

*Type: TXT Record  
Host: verify.store  
Value: xxx-xxx  
TTL: 15 minutes*

#### CloudFlare

Type*: CNAME* Name*: store* Domain name*: xxx-xxx.cfdns.craftingstore.net Automatic TTL* Orange Cloud: *Make sure that this one is on, the requests must go through Cloudflare, or they will fail. For cloudflare we use servers that only work inside of their network. You can use SSL/TLS mode: Full or Flexible, not full strict.*

*Type: TXT  
Name: verify.store  
Content: xxx-xxx  
Automatic TTL*

#### OVH

Pointer Records: *CNAME* Sub-domain*: store* TTL*: By Default* Target*: xxx-xxx.dns.craftingstore.net. (note the dot at the end, it is required and will not work without it)*

*Pointer Records: TXT  
Sub-domain: verify.store  
TTL: By Default  
Target: xxx-xxx*
