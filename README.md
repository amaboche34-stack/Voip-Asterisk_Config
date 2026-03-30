# Voip-Asterisk_Config
In this Directory we will be using the resent sip configurations called the PJSIP and not the CHAN_SIP, unlike the legacy chan_sip which used a single configuration block per peer, PJSIP uses a modular design with multiple object types that work together. This can seem complex at first, but it provides much more flexibility and clarity.
Why PJSIP: chan_sip is deprecated and no longer actively developed. PJSIP supports multiple transports per endpoint, better NAT handling, WebRTC, and improved performance. And as from asterisk 20, the chan_sip is no longer supported unless installed manually. But it's higly recommended to use the pjsip.
PJSIP uses six main components, which includes:
Transport; Which defines the network protocols and the port for SIP communication. You need at least one. Most systems defines udp and rarely tls
Endpoints; Endpoints are the central PJSIP object. Every SIP phone, softphone, or trunk is an endpoint. They reference other objects (AOR, auth) and define media settings
AORs (Address of Record); AORs define where a device can be reached and how many simultaneous registrations are allowed  
Authentication; Auth objects store credentials for inbound authentication (phones registering to Asterisk) and outbound authentication (Asterisk registering to a trunk provider)     
Identify: Identify objects match inbound SIP traffic to an endpoint based on the source IP address. This is essential for trunks using IP authentication where there is no REGISTER to identify the source         
Registration: Registration objects tell Asterisk to register with an external SIP server. This is needed when your trunk provider uses digest authentication

Note: This information was gotten from  https://www.ipcomms.net/blog/asterisk-pjsip-configuration/#overview
If You need more information Just visit the website above
