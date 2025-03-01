# v3.0.3 Apr 30 2024
## Breaking Change

For users using SMTP with older versions, you might need to update the settings by moving the domains (the part after @ in the username and domain setup field) into the username field.

+ Updated SMTP UI for non email login username [#129](https://github.com/tobychui/zoraxy/issues/129)
+ Fixed ACME cert store reload after cert request [#126](https://github.com/tobychui/zoraxy/issues/126)
+ Fixed default rule not applying to default site when default site is set to proxy target [#130](https://github.com/tobychui/zoraxy/issues/130)
+ Fixed blacklist-ip not working with CIDR bug
+ Fixed minor vdir bug in tailing slash detection and redirect logic
+ Added custom mdns name support (-mdnsname flag)
+ Added LAN tag in statistic [#131](https://github.com/tobychui/zoraxy/issues/131)


# v3.0.2 Apr 24 2024

+ Added alias for HTTP proxy host names [#76](https://github.com/tobychui/zoraxy/issues/76)
+ Added separator support for create new proxy rules (use "," to add alias when creating new proxy rule)
+ Added HTTP proxy host based access rules [#69](https://github.com/tobychui/zoraxy/issues/69)
+ Added EAD Configuration for ACME (by [yeungalan](https://github.com/yeungalan)) [#45](https://github.com/tobychui/zoraxy/issues/45)
+ Fixed bug for bypassGlobalTLS endpoint do not support basic-auth
+ Fixed panic due to empty domain field in json config [#120](https://github.com/tobychui/zoraxy/issues/120)
+ Removed dependencies on management panel css for online font files

# v3.0.1 Apr 04 2024

## Bugfixupdate for big release of V3, read update notes from V3 if you are still on V2

+ Added regex support for redirect (slow, don't use it unless you really needs it) [#42](https://github.com/tobychui/zoraxy/issues/42)
+ Added new dpcore implementations for faster proxy speed
+ Added support for CF-Connecting-IP to X-Real-IP auto rewrite [#114](https://github.com/tobychui/zoraxy/issues/114)
+ Added enable / disable of HTTP proxy rules in runtime via slider [#108](https://github.com/tobychui/zoraxy/issues/108)
+ Added better 404 page
+ Added option to bypass websocket origin check [#107](https://github.com/tobychui/zoraxy/issues/107)
+ Updated project homepage design
+ Fixed recursive port detection logic
+ Fixed UserAgent in resp bug
+ Updated minimum required Go version to v1.22 (Notes: Windows 7 support is dropped) [#112](https://github.com/tobychui/zoraxy/issues/112)


# v3.0.0 Feb 18 2024

## IMPORTANT: V3 is a big rewrite and it is incompatible with V2! There is NO migration, if you want to stay on V2, please use V2 branch!

+ Added comments for whitelist [#97](https://github.com/tobychui/zoraxy/issues/97)
+ Added force-renew for certificates [#92](https://github.com/tobychui/zoraxy/issues/92)
+ Added automatic cert pick for multi-host certs (SNI)
+ Renamed .crt to .pem for cert store
+ Added best-fit selection for wildcard matching rules
+ Added x-proxy-by header / Added X-real-Ip header [#93](https://github.com/tobychui/zoraxy/issues/93)
+ Added Development Mode (Cache-Control: no-store)
+ Updated utm timeout to 10 seconds instead of 90
+ Added "Add controller as member" feature to Global Area Network editor
+ Added custom header
+ Deprecated aroz subservice support
+ Updated visuals, improving logical structure, less depressing colors [#95](https://github.com/tobychui/zoraxy/issues/95)
+ Added virtual directory into host routing object (each host now got its own sets of virtual directories)
+ Added support for wildcard host names (e.g. *.example.com)
+ Added best-fit selection for wildcard matching rules (e.g. *.a.example.com > *.example.com in routing)
+ Generalized root and hosts routing struct (no more conversion between runtime & save record object
+ Added "Default Site" to replace "Proxy Root" interface
+ Added Redirect & 404 page for "Default Site"


# v2.6.8 Nov 25 2023

+ Added opt-out for subdomains for global TLS settings: See [release notes](https://github.com/tobychui/zoraxy/releases/tag/2.6.8)
+ Optimized subdomain / vdir editing interface
+ Added system-wide logger (Work in progress)
+ Fixed issue for uptime monitor bug [#77](https://github.com/tobychui/zoraxy/issues/77)
+ Changed default static web port to 5487 (prevent already in use)
+ Added automatic HTTP/2 to TLS mode
+ Bug fix for webserver autostart [67](https://github.com/tobychui/zoraxy/issues/67)

# v2.6.7 Sep 26 2023

+ Added Static Web Server function [#56](https://github.com/tobychui/zoraxy/issues/56)
+ Web Directory Manager (see static webserver tab)
+ Added static web server and black / whitelist template [#38](https://github.com/tobychui/zoraxy/issues/38)
+ Added default / preferred CA features for ACME [#47](https://github.com/tobychui/zoraxy/issues/47)
+ Optimized TLS/SSL page and added dedicated section for ACME related features
+ Bugfixes [#61](https://github.com/tobychui/zoraxy/issues/61) [#58](https://github.com/tobychui/zoraxy/issues/58)

# v2.6.6 Aug 30 2023

+ Added basic auth editor custom exception rules 
+ Fixed redirection bug under another reverse proxy and Apache location headers [#39](https://github.com/tobychui/zoraxy/issues/39)
+ Optimized memory usage (from 1.2GB to 61MB for low speed geoip lookup) [#52](https://github.com/tobychui/zoraxy/issues/52)
+ Added unset subdomain custom redirection feature [#46](https://github.com/tobychui/zoraxy/issues/46)
+ Fixed potential security issue in satori/go.uuid [#55](https://github.com/tobychui/zoraxy/issues/55)
+ Added custom ACME feature in backend, thx [@daluntw](https://github.com/daluntw)
+ Added bypass TLS check for custom acme server, thx [@daluntw](https://github.com/daluntw)
+ Introduce new start parameter `-fastgeoip=true`: see [release notes](https://github.com/tobychui/zoraxy/releases/tag/2.6.6)

# v2.6.5.1 Jul 26 2023

+ Patch on memory leaking for Windows netstat module (do not effect any of the previous non Windows builds)
+ Fixed potential memory leak in ACME handler logic
+ Added "Do you want to get a TLS certificate for this subdomain?" dialogue when a new subdomain proxy rule is created

# v2.6.5 Jul 19 2023

+ Added Import / Export-Feature 
+ Moved configuration files to a separate folder [#26](https://github.com/tobychui/zoraxy/issues/26)
+ Added auto-renew with ACME [#6](https://github.com/tobychui/zoraxy/issues/6)
+ Fixed Whitelistbug [#18](https://github.com/tobychui/zoraxy/issues/18)
+ Added Whois

# v2.6.4 Jun 15 2023

+ Added force TLS v1.2 above toggle
+ Added trace route
+ Added ICMP ping
+ Added special routing rules module for up-coming ACME integration
+ Fixed IPv6 check bug in black/whitelist
+ Optimized UI for TCP Proxy

# v2.6.3 Jun 8 2023

+ Added X-Forwarded-Proto for automatic proxy detector
+ Split blacklist and whitelist from geodb script file
+ Optimized compile binary size
+ Added access control to TCP proxy
+ Added "invalid config detect" in up time monitor for issue [#7](https://github.com/tobychui/zoraxy/issues/7)
+ Fixed minor bugs in advance stats panel
+ Reduced file size of embedded materials

# v2.6.2 Jun 4 2023

+ Added advance stats operation tab
+ Added statistic reset [#13](https://github.com/tobychui/zoraxy/issues/13)
+ Added statistic export to csv and json (please use json)
+ Make subdomain clickable (not vdir) [#12](https://github.com/tobychui/zoraxy/issues/12)
+ Added TCP Proxy
+ Updates SMTP setup UI to make it more straight forward to setup

# v2.6.1 May 31 2023

+ Added reverse proxy TLS skip verification
+ Added basic auth
+ Edit proxy settings
+ Whitelist
+ TCP Proxy (experimental)
+ Info (Utilities page)

# v2.6 May 27 2023

+ Basic auth
+ Support TLS verification skip (for self signed certs)
+ Added trend analysis
+ Added referrer and file type analysis
+ Added cert expire day display
+ Moved subdomain proxy logic to dpcore
