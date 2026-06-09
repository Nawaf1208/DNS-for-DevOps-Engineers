# DNS-for-DevOps-Engineers

![](DNS.png)

<details>
<summary><b><i>1.What is DNS? What is it used for?</i></b></summary>

$\color{green}{\text{Answer}}$

DNS (Domain Name Systems) is a protocol used for converting domain names into IP addresses.

Computer networking (at layer 3 of the OSP model) is done with IP addresses but for as humans it's hard to remember IP addresses, it's much easier to remember names. This why we need something such as DNS to convert any domain name we type into an IP address. You can think on DNS as a huge phonebook or database where each corresponding name has an IP.

</details>

<details>
<summary><b><i>2.What is DNS resolution?</i></b></summary>

$\color{green}{\text{Answer}}$

The process of translating IP addresses to domain names.

</details>

<details>
<summary><b><i>3.What is a name server?</i></b></summary>

$\color{green}{\text{Answer}}$

A server which is responsible for resolving DNS queries.

</details>

<details>
<summary><b><i>4.What is the resolution sequence of: `www.site.com`</i></b></summary>

$\color{green}{\text{Answer}}$

It's resolved in this order:

1. .

2. .com

3. site.com

4. www.site.com

</details>

<details>
<summary><b><i>5.What is a domain name registrar?</i></b></summary>

$\color{green}{\text{Answer}}$

Cloudflare: "A domain name registrar provides domain name registrations to the general public. A common misconception is that registrars sell domain names; these domain names are actually owned by registries and can only be leased by users."


</details>

<details>
<summary><b><i>6.Given the following fqdn, `www.blipblop.com`, what is the root?</i></b></summary>

$\color{green}{\text{Answer}}$

`.` is the root

</details>

<details>
<summary><b><i>7.Given the following fqdn, `www.blipblop.com`, what is the top level domain?</i></b></summary>

$\color{green}{\text{Answer}}$

`.com.` is the top level domain

</details>

<details>
<summary><b><i>8.Given the following fqdn, `www.blipblop.com`, what is the second level domain?</i></b></summary>

$\color{green}{\text{Answer}}$

`blipblop.com.` is the second level domain

</details>

<details>
<summary><b><i>9.Given the following fqdn, `www.blipblop.com`, what is the domain?</i></b></summary>

$\color{green}{\text{Answer}}$

`www.blipblop.com.` is the domain

</details>

<details>
<summary><b><i>10.Describe DNS resolution workflow in high-level</i></b></summary>

$\color{green}{\text{Answer}}$

In general the process is as follows:

The user types an address in the web browser (some_site.com)

The operating system gets a request from the browser to translate the address the user entered

A query created to check if a local entry of the address exists in the system. In case it doesn't, the request is forwarded to the DNS resolver

The Resolver is a server, usually configured by your ISP when you connect to the internet, that responsible for resolving your query by contacting other DNS servers

The Resolver contacts the root nameserver (aka as .)

The root nameserver either responds with the address you are looking for or it responds with the address of the relevant Top Level Domain DNS server (if your address ends with org then the org TLD)

The Resolver then contacts the TLD DNS. TLD DNS might respond with the address you are looking for. If it doesn't has the information, it will provide the address of SLD DNS server

SLD DNS server will reply with the address to the resolver

The Resolver passes this information to the browser while your OS also stores this information in the cache

The user cab browse the website with happiness and joy

</details>

## DNS - Records

<details>
<summary><b><i>11.What is a DNS record?</i></b></summary>

$\color{green}{\text{Answer}}$

A mapping between domain name and an IP address.

</details>

<details>
<summary><b><i>12.What types of DNS records are there?</i></b></summary>

$\color{green}{\text{Answer}}$

A

CNAME

PTR

MX

AAAA ...

</details>

<details>
<summary><b><i>13.What is a A record?</i></b></summary>

$\color{green}{\text{Answer}}$

A (Address): Maps a host name to an IPv4 address.

When a computer has multiple adapter cards and IP addresses, it should have multiple address records.

</details>

<details>
<summary><b><i>14.What is a AAAA record?</i></b></summary>

$\color{green}{\text{Answer}}$

An AAAA Record performs the same function as an A Record, but for an IPv6 Address.

</details>

<details>
<summary><b><i>15.What is a CNAME record?</i></b></summary>

$\color{green}{\text{Answer}}$

CNAME: maps a hostname to another hostname.

The target should be a domain name which must have an A or AAAA record. Think of it as an alias record.

</details>

<details>
<summary><b><i>16.What is a PTR record?</i></b></summary>

$\color{green}{\text{Answer}}$

While an A record points a domain name to an IP address, a PTR record does the opposite and resolves the IP address to a domain name.

</details>

<details>
<summary><b><i>17.What is a MX record?</i></b></summary>

$\color{green}{\text{Answer}}$

MX (Mail Exchange) Specifies a mail exchange server for the domain, which allows mail to be delivered to the correct mail servers in the domain.

</details>

<details>
<summary><b><i>18.What is a NS record?</i></b></summary>

$\color{green}{\text{Answer}}$

NS: name servers that can respond to DNS queries

</details>

## DNS - TTL

<details>
<summary><b><i>19.xplain DNS Records TTL</i></b></summary>

$\color{green}{\text{Answer}}$

DNS TTL (time to live) is a setting that tells the DNS resolver how long to cache a query before requesting a new one. The information gathered is then stored in the cache of the recursive or local resolver for the TTL before it reaches back out to collect new, updated details.

</details>

## DNS - Misc

<details>
<summary><b><i>20.Is DNS using TCP or UDP?</i></b></summary>

$\color{green}{\text{Answer}}$

DNS uses UDP port 53 for resolving queries either regular or reverse. DNS uses TCP for zone transfer.

</details>

<details>
<summary><b><i>21.True or False? DNS can be used for load balancing</i></b></summary>

$\color{green}{\text{Answer}}$

True.

</details>

<details>
<summary><b><i>22.Which techniques a DNS can use for load balancing?</i></b></summary>

$\color{green}{\text{Answer}}$

There are several techniques that a DNS can use for load balancing, including:
  - Round-robin DNS
  - Weighted round-robin DNS
  - Least connections
  - GeoDNS

</details>

<details>
<summary><b><i>23.What is a DNS zone?</i></b></summary>

$\color{green}{\text{Answer}}$

A DNS zone is a logical container that holds all the DNS resource records for a specific domain name.

</details>

<details>
<summary><b><i>24.What types of zones are there?</i></b></summary>

$\color{green}{\text{Answer}}$

There are several types, including:

Primary zone: A primary zone is a read/write zone that is stored in a master DNS server.

Secondary zone: A secondary zone is a read-only copy of a primary zone that is stored in a slave DNS server.

Stub zone: A stub zone is a type of zone that contains only the essential information about a domain name. It is used to reduce the amount of DNS traffic and improve the efficiency of the DNS resolution process.

</details>
