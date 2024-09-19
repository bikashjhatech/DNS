# DNS

I have completed the DNS course on TryHackMe . I learned about the importance of various aspects of DNS details, which will be very helpful during investigations. I am documenting my learning.


DNS (Domain Name System) is like the phone book of the internet. When you type a website address into your browser, like “tryhackme[.]com,” DNS translates that name into an IP address 104.26.10.229, which is like the “tryhackme[.]com” website’s phone number.


## Domain Hierarchy

**TLD (Top-Level Domain)**:A Top-Level Domain (TLD) is the part of a domain name that comes after the last dot. For example, in the domain name “tryhackme[.]com,” the TLD is “.com.” TLDs are the highest level in the domain name system hierarchy, and they help categorize and identify the purpose or origin of a website.

There are several types of TLDs:

**Generic TLDs (gTLDs)**: .com, .org, .edu, .gov

**Country Code TLDs (ccTLDs)**: These represent specific countries such as .ca for Canada

**Second-Level Domain**: A Second-Level Domain (SLD) is the part of a domain name that comes immediately before the Top-Level Domain (TLD). For example, in the domain name “tryhackme[.]com,” “tryhackme” is the second-level domain.

**Subdomain**: A subdomain is a domain that is part of a larger domain. It comes before the second-level domain and the top-level domain in a web address. For example “shop[.]amazon[.]com” shop part is the subdomain. Subdomains are used to organize different sections of a website.

## DNS Record Types

DNS records are like different types of information stored in the Domain Name System.

**A Record** : Maps a domain name to an IPv4 address like 104.26.10.229

**AAAA Record**: Maps a domain name to an IPv6 address like 2001:4860:4860::8888

**CNAME**: Canonical Name- Alias for another domain name. For example store[.]tryhackme[.]com returns a CNAME record shops[.]shopify[.]com.

**MX Record**: MX (Mail Exchange) record is a type of DNS record used to specify the mail servers responsible for receiving and handling email for a domain.

**TXT Record**: TXT((Text) record is a type of DNS record used to store text data associated with a domain.They are particularly valuable for domain verification and enhancing email security.

## How a DNS request operates behind the scenes

**Local Cache Check**: Your computer first checks if it has the domain address cached locally.

**Recursive DNS Server Query**: An ISP typically supplies a Recursive DNS Server. This server maintains a local cache of recently queried domain names, so if it has the information stored, it can send the result directly to your computer.

**Root DNS Server**: If not cached, the Recursive DNS Server queries the root DNS servers to find the Top-Level Domain (TLD) server.

**TLD Server**: The root server directs the request to the TLD server for the domain’s extension (e.g., .com).

**Authoritative DNS Server**: The TLD server directs the request to the authoritative DNS server for the domain.

**DNS Record Response**: The authoritative server provides the DNS record (e.g., IP address) and sends it back through the Recursive DNS Server to your computer.

**Caching**: The DNS record is cached locally on your computer and on the Recursive DNS Server for future requests, with a TTL (Time To Live) value determining how long it is stored.



