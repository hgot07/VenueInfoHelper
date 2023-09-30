# VenueInfoHandler (beta)
API/CGI for Venue Information notification on Public Wi-Fi to help users reach out to the web portal at the venue.

This helper is specialized for Venue Information display rather than Captive Portal that blocks the network usage. There is no access control at all. Our intention is to improve user engagement while allowing people to use the network continuously and seamlessly.

## Supported platforms
### Modern Capport (RFC 8908/8910)
- Android 12+
- iOS/iPadOS 17+
- macOS 13 (Ventura)+

### Vendor-specific Captive Portal
- iOS/iPadOS 16 and some older ones
- macOS 12 (Montrerey) and some older ones


## Specifications
- Capport API (RFC 8908/8910) is the primary.
- Support (partly) Apple's legacy Captive Portal mechanism (CNA, Captive Network Assistant).
- Usable with Open, PSK, 802.1X, and Passpoint networks.

## Requirements
- Redis
- Perl
- (Local) HTTP server with a server certificate issued by a popular CA
- Local DNS server
- DHCP server

## Limitations
- (Disturbing) Captive Portal is enforced on Apple devices since they haven't got a nice notification mechanism.
- No support for Android 11 and older.
- No support for Windows 10/11 so far.
- Not working well over NAPT. To overcome this, we will need a DHCP server that can attach some paramters like MAC address in order for the API to uniquely identify the user device behind a NAPT box.

## Website layout
- https://\<portal.example.com\>/ -- Portal site of the venue. (SSL is required)
- https://\<example.net\>/cp/ -- Capport API (SSL is required)
- http://\<local IP address\>/ -- Diverted destination for Apple's legacy captive portal mechanism. (No-SSL)

## Deployment
- (to be added)
