<h1 align="center">Vatican .va (Holy See)<br>ccTLD Zone Data<br><br>
<img src="https://raw.githubusercontent.com/indianajson/indianajson/main/vatican.gif"></h1>
    <h3 align="center">Last updated May 26, 2021.<br>This zone file contains 1,426+ records for 935 FQDNs.<br>
    Download <a target="_blank" href="va-zone.csv">CSV</a> or <a target="_blank" href="va-zone.txt">TXT</a> format.</h3>

## Summary

Vatican City is the smallest, independent nation state in the world. As a nation it was given the .va ccTLD. This country code top-level domain is restricted for usage by Vatican City (also known as the Holy See) and represents the religion of Catholicism at large. One would suspect that there would be a relatively small network behind such a small nation, but the reality is quite surprising. The Vatican .va (Holy See) ccTLD operates around two hundred apex domains, encompassing over seven hundred subdomains, which connect the various aspects of Vatican City's internal operations and publicly facing websites. As it stands there is no offical way to request the zone file from Vatican City. Furthermore, it has been over a decade since the [2007 VA ccTLD zone file](https://web.archive.org/web/20080119124048/http://www.robert.net/ccTLD/VA) was published (originally by Robert Baskerville). This lead us to develop our own zone file as part of a research initiative, which we are making available for interested researchers. 

## Downloads

The <a target="_blank" href="va-zone.txt">`va-zone.txt`</a> file is tab delimited and contains a running list of each record identified, whereas the <a target="_blank" href="va-zone.csv">`va-zone.csv`</a> file contains seperate columns for record name, record type, and record value for easy sorting and filtering. 

## Interesting Notes

#### 1. Apex domains can be bound with a CNAME record.

>Unlike many nameservers, apex domains in the VA zone may forward traffic directly with a CNAME, as opposed to using an A record. For example, `www.va` only has a CNAME pointing to `www.vatican.va`.

#### 2. Apex domains do not usually redirect to their `www` counterpart.

> Typically when navigating to a domain, if the website resides at `www.example.com` then navigating to `example.com` will redirect you to the former. This is not the case within the VA zone. For example, `vatican.va` contains no A or CNAME records and will never resolve to a website directly, whereas `www.vatican.va` contains a CNAME record and will resolve to the main Vatican City website. 

#### 3. Most websites within the zone can be accessed via both `http` and `https`.

>While most of the internet now redirects all `http` traffic to `https`, this is not the case with most domains within the VA zone. For example, you can access either `https://www.vartican.va` or `http://www.vatican.va` without being redirected. 

#### 4. Many domains are only used for email.

>Quite a few domains registered in the zone appear to be used exclusively for email addresses (neither the apex domain nor the `www` equivalent contained A or CNAME records) and no subdomain records appear to exist. 

## Methodology & Special Thanks

Research began with the Vatican City's two autonomous systems ([AS8978](https://bgp.he.net/AS8978) and [AS202865](https://bgp.he.net/AS202865)). Almost all Vatican City networks and servers operate within these two IP address blocks (with very few exceptions). With research on the scope of the ccTLD over the past twenty years obtained from <a href="https://github.com/internetarchive/" target="_blank"the Internet Archive</a> we were able to construct a fairly robust map of the primary domains in the zone. This project would have been impossible without <a href="https://github.com/caffix"> target="_blank">Caffix</a>'s <a href="https://github.com/OWASP/Amass" target="_blank">amass</a> project, which allowed us to perform subdomain enumeration on each valid apex domain automating what would have taking dozens of hours to complete by hand. Finally, DNS records for each valid domain and subdomain were collected into the final zone data presented above. 

## Disclaimer

This zone file was not obtained via a zone transfer, but instead created by compiling data collected through various methods, consequently this zone data does not necessary contain every record that exists within the real .va ccTLD Zone File operated by Vatican City. Additionally, most of the domains' use the same nameservers as the SOA for `va`. We did not include additional NS records unless they differed from the SOA. 
