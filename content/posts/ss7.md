---
title: "SS7 or when scp it is not OpenSSH secure file copy"
date: 2023-10-21
description: ''
featured_image: "/images/photo1677896889_1.jpeg"
tags: ["#network", " #text", "#scetch", "#telephone"]
draft: false
---

# SS7 or when scp it is not OpenSSH secure file copy

**SS7** - **Signaling System 7** is a set of international telecommunication signaling protocols that are used to set up most of the world’s public switched telephone network (PSTN) telephone calls. SS7 primarily sets up and tears down telephone calls, but other uses include number translation, prepaid billing mechanisms, local number portability, short message service (SMS), and a variety of mass-market services.

The signaling transport (SIGTRAN) protocols provide interoperability of SS7 signaling to operate over (IP)-based networks. This enables PSTN service to operate over legacy, analog plain old telephone service systems and modern IP networking equipment. 
SIGTRAN uses its own Stream Control Transmission Protocol, as opposed to Transmission Control Protocol or User Datagram Protocol.

To remove the issues of in-band signaling, SS7 uses out-of-band signaling, called common channel signaling (CCS). In CCS, a dedicated channel separate from the voice channel is used to carry the SS7 control signals. This channel is only accessible to the underlying infrastructure and not the end callers, increasing security.

Services offered by SS7 include the following:

* Basic call setup, management, and teardown
* call forwarding
* automated voicemail
* call waiting
* conference calling
* threeway calling
* caller ID
* subscriber authentication and extended billing
* Wireless services such as personal communications services (PCS), wireless roaming, and mobile subscriber authentication
* Local number portability (LNP)
* toll-free (800 and 888) and toll (900) calls
* SMS (Short Message Service)
* Efficient worldwide telecommunications
* mobile phone roaming and tracking

![](/images/networking-typical_signaling_system_7_architecture-f.png)

> SS7 is a longstanding telecommunications protocol and standard for both landline and mobile phone service.

SS7 network has three main types of nodes. Each node has specific functionalities:

* **Signaling Switching Points (SSP)** This node terminates the wireless side (BSC/BTS) and connects to the rest of the network over SS7. An SSP may be connected to another SSP directly, or it may be connected via a signaling gateway. MSC, or mobile switching center, is an example of SSP. MSC provides roaming, messaging, billing, and call control functionalities.

* **Signaling Transfer Point (STP)** This node is working as a  router in the SS7 network. The primary important role is to do Global Title Translation and select the next node for the message. The next node may be SSP or another STP.

* **Signaling Control Point (SCP)** This node has a database and maintains a centralized service. For a service, these nodes are contacted. Many SSPs can contact a single SCP. HLR or Home Location Register is an example of SCP in the GSM network. When a mobile phone is switched on, it tries to attach first to MSC (SSP), and then MSC sends a location update to the HLR. The MSC may change, but the HLR remains the same. A mobile operator can map location information with time.


SSPs originate or terminate a call and are the initial point on the SS7 network. The control signals are routed through various STPs, which operate as interconnected switches on the SS7 network. The SCPs determine how to route a call or set up and manage some special feature.

SCPs and STPs usually exist as a collection of discrete nodes so that service can continue if one network point fails. The SCPs may also communicate with a Service Data Point, which stores the user database and directory. The signaling links between nodes generally operate at full-duplex 56 or 64 kilobits per second (Kbps) bandwidth, with large facilities using a full T1 line at 1.536 megabits per second (Mbps) for signaling links.

SS7 allows for several modes of operation for both voice and data service, including the following:

* Message Transfer Part carries SS7 signals between nodes.
* Telephone User Part carries voice calls between users.
* Data User Part carries digital data between users.

Integrated Services Digital Network (ISDN) could also be used, enabling digital voice or data service at a relatively high speed, for the time, of up to 128 Kbps or 1.5 Mbps for a full T1 line. ISDN did not see wide adoption in the consumer market because, by the time it was widely available, 56.6 Kbps modems were becoming available as well. Asymmetric Digital Subscriber Line service widely superseded ISDN data service.

## What are the layers in an SS7 Protocol stack?

![](/images/SS7-Protocol-Stack.jpg)

### Message Transfer Part 1 (MTP1) – Physical Layer

Transfers bits over a physical channel in the form of electrical signals. Have physical ports to connect the cables. A card may have its CPU and RAM. When someone buys an SS7 card, it also comes with MTP2. An SS7 card may have multiple ports with multiple channels (32 – E1, 24 -T1).   

### Message Transfer Part 2( MTP2) – Data Link Layer

Transfers the error-free frames between two directly connected nodes. It maintains the receiver and sender windows. It uses sliding window protocol and retransmissions for flow and error control. 

#### functions of the MTP2 layer
* Error Control- checks the error in a received frame based on 16 bits CRC. Re-transmits lost message or error message.
* Message Sequencing–  maintains the sequencing of messages between directly connected nodes. Forward and backward sequencing numbers are maintained for sequence and retransmissions.
* Link Alignment–  provides link alignment procedures when requested from its user(MTP3).
* Flow control– if the receiver is slow, sending mtp2 gives an indication to its user for congestion.
* Link Status–  link status is given to the user. The status may be, in service(UP), out of service(DOWN), or congestion(CONGESTED).

### Message Transfer Part 3(MTP3) – Network Layer

This is the network layer that implements the mtp3 protocol. This does end-to-end routing of SS7 messages. This is the network layer in the ss7 protocol stack. For routing mtp3 routing, the level is defined. The routing level is defined in the MTP3 header, which contains OPC, DPC, and SLS. Mtp3 specification is given in Q.704. DPC is the point code of the destination ss7 node, OPC is the originating point code, and SLS is used for the load distribution of MTP3 user messages over links.

When a message is passed from MTP2 to MTP3, the routing level, SIO, and MTP3 user data are passed in the message. MTP3 has two primary functions, discrimination, and distribution. The discrimination function decides if the message is for the self node or some distance node. The discrimination function uses DPC. If a message is for a self-node, it is passed to the distribution function. 

The distribution function checks SI, which is part of SIO. The value of SI identifies the user of  MTP3. For Eg, if SI is 5, the message is delivered to the ISUP layer over MTP3. If the value of SI is 3, then the message is delivered to the user (SCCP/ISUP).

#### functions of MTP3

* Remote Point code status management, mtp3 maintains the configuration of remote point code and its status. The status may be available or unavailable. The user of mtp3 gets PAUSE or RESUME indications for a configured remote point code. During the routing of a message, the status of the remote point code is checked.
* Link Alignment: Once a link is configured at MTP2 and MTP3 levels, the MTP3 layer starts the link alignment by issuing an alignment primitive to the MTP2 layer. This starts link alignment at the mtp3 level. Once a link comes up on the mtp2 level. MTP3 receives an in-service indication from the MTP2 layer. MTP3 sends an SLTM message to the remote end. If SLTA is received in response to SLTM, the link is marked up at the mtp3 level. If the link is the first link in a link set, then it’s an emergency link alignment procedure, else it’s a normal link alignment procedure.
* Transfer Prohibited (TFP): This is the MTP3 procedure by which a signaling point code can mark a route unavailable for a destination point code. This updates the routing table for a destination point code when a signaling transfer point (STP) detects an unreachable point code. 

* **Load Sharing** does the load sharing over Linkset and links based on SLS received from the user.
* **Change Over**, when a link fails, the failed link’s traffic is distributed to the available links. 
* **Change Back**, when a failed link comes back, the traffic is rerouted to the association. 




## SS7 vulnerabilities and security implications

The telecommunications (telecom) industry developed Signaling System 7 before digital encryption and authentication were widely adopted. This means that SS7 messages and service can be relatively easily listened in on and forged.

Unfortunately, the primary security on the SS7 network is that it is a closed system; only telecom operators have access to it. End users and most hackers cannot access the system as a whole. 
Telecom providers operating as bad actors or governmental agencies with legal access have relatively unrestricted access to all the information available in the SS7 network. Telecom providers can also monitor the SS7 network for threats or intrude and identify them, but this does not prevent passive exploitation.

Given the rich feature set and nonexistent security of SS7, this gives these threat actors unprecedented access to user information. It also gives governments the ability to track mobile users' location anywhere in the world, even without the use of the Global Positioning System.

While Global System for Mobile communication (GSM) calls are encrypted over the air, the decryption key can be requested from the SS7 network for later decryption. SMS messages are sent unencrypted over the SS7 network and can be easily read. This type of snooping is called a SS7 probe or international mobile subscriber identity catcher. Attackers have used call forwarding to redirect calls or SMS multifactor authentication codes to ones controlled by an attacker to steal from bank accounts.

![](/images/mobile_computing-gsm.png)


With the underlying vulnerability of the SS7 network, the only way not to be at risk is to not use telephone service. This would entail disabling telephone and mobile data service on a cellphone to prevent tracking. Voice and text messages should be sent using encrypted IP-based services, such as iMessage, WhatsApp, Telegram or Signal.

*** 

# Signaling Connection Control Part (SCCP) – Transport Layer

It works as a transport layer and uses the service of MTP3. Do the segmentation/reassembly of large messages if required. A user application is identified by an SSN (an integer value). An SSN is a standard numeric value identifying an application/node in the GSM network.

HLR – SSN 6
VLR-SSN 7
MSC – SSN 8
SGSN – SSN 149
In the telecom network, an SCCP layer is identified by a Global title. A global title is a sequence of digits that is unique globally. Your phone number with country code is an example of a global title. The SCCP layer does SSN management, global title translation, and other functions.

SSN management:
SSN configured on the SCCP layer can be local or remote. Before sending a message to a peer SSN, SCCP layers check the status of the remote SSN. If it is down, the message is dropped. To check the status of an SSN,  a peer transmits the SST and waits for SSA. This procedure is optional. A remote SSN can be marked as available when a peer point code comes up after successful link alignment.

Global Title Translation:
An SCCP address has called party and calling party address in the SCCP header. Both addresses are global titles. Upon receiving, SCCP checks if GT matches the current node. If yes, then the Called Party GT is translated to the point code of the current node. The message is delivered to the local user identified by the called party SSN in the incoming messages.

If a message is not of local use, the GT can be translated into another GT or PC. Or it can be forwarded to the next hope. If the current nodes know the point code serving the called party address, the gt is translated on point code. Else forward to the next hop.

SCCP message classes:
Class 0, connection less non sequenced message. 
Class 1, connection less sequenced delivery of messages.
Class 2, connection oriented without flow control.
Class 3, connection oriented with flow control. 
User Primitives of SCCP Layer:
A user primitive is the interface a layer provides to access its services. SCCP Provides request primitives to request a service from the layer, and Indication primitives, to inform events received from the network.

***

# PSTN

PSTN Public Switched Telephone Network - is a collection of interconnected public telephone networks that rely on physical infrastructure to connect phone calls. 
PSTN refers to the traditional telephone system used for voice-oriented communications. It consists of multiple interconnected carriers to reliably connect people through standard phone numbers.

This telephone network is known as analog, landlines, Plain Old Telephone Service (POTS), or fixed lines. This system has been in general use since the late 1800s.

Using underground copper wires and circuit-switching, this legacy service has provided businesses and households with a reliable means to communicate with anyone worldwide for generations.

When you place a call on the PSTN, the call hits multiple touchpoints, or offices, before your call reaches the phone on the other end of the line. The call travels through physical wires to each relevant office—which varies depending on its final destination—and each office is equipped with physical infrastructure designed to send the call to the next office until it reaches its intended receiver. It’s not complicated, but the amount of infrastructure and touchpoints involved means it’s challenging to match the instant data transmission offered by modern telephony solutions like VoIP.


## PSTN routing and call flow

When you pick up the phone and dial, several things take place that enable your call to connect. 

![](/images/How-POTS-Works.jpg)

Here’s how it works:

* The caller picks up a phone, hears a dial tone and dials a phone number.
* Once the call is received, the phone works to convert sound waves (your voice) into electrical signals that can be transmitted to a terminal via cables.
* The electrical signals are then sent by the terminal to the central office or local exchange.
* Once the central office receives the electrical signals, they are routed to the correct destination through cables in the form of light or electrical pulses, depending on the type of cable used. When the call reaches its destination, it is converted back to electrical signals and routed to the correct terminal.
* Finally, the terminal routes the call to the correct phone number. Once the phone receives the electrical signals, it converts those signals back into sound waves, which allows for nearly instantaneous communication between callers.

Because of the way calls are routed, it’s possible to physically trace the origin of any call. This makes the PSTN ideal for use cases like emergency services—even if a caller is not able to identify or communicate their location, the 911 dispatcher can trace the call and send help to the correct place.

Key terms:

**The local exchange**

A local exchange – consisting of one or more exchanges – connects subscribers to a PSTN line. Also known as a central office or a switching exchange, a telephone exchange can have up to 10,000 lines. All phones are connected to the local exchange in a specific area. The exchange identifies the number dialed to route the call to the correct destination.

**Central office (CO)**

A central office, also known as the local exchange, is usually made up of one or more offices that connect subscribers to a PSTN line. The central office a subscriber is connected to usually depends on their geographical location. The exchange then identifies the number being dialed, and routes it to the desired destination.

**Tandem office**

A tandem office, also known as a junction network, is a step up from the local exchange. It serves a larger geographical area, and is made up of multiple local exchanges. The tandem office has the capability of routing calls between local exchanges.

**Toll office**

Every national long-distance switching takes place here. A toll office is connected to all tandem offices. For instance, if you dial a branch of your office in another city, your call will go through a toll office.

**International gateway**

International gateways manage international call switching, routing domestic calls to the appropriate countries.


## The PSTN alternative:

### PSTN vs. VoIP

**VoIP** stands for **Voice Over Internet Protocol**. It means voice communication is transmitted over the internet or private wide area network (WAN). VoIP is also known as IP telephony, internet telephony, or broadband telephony.

VoIP eliminates the need for circuit-switched networks for phone calls as it sends your voice communications over the internet rather than through cables. This means you’ll need a reliable internet connection. It’s a cloud-based solution that’s simple to set up, inexpensive, and easy to use.

VoIP has advantages over PSTN, including lower network costs, faster connectivity, scalability, and advanced features, such as unified communications and app integrations.

While PSTN calls aren’t as susceptible to security issues like cyber attacks, VoIP calls today have also become more safe and secure.

### PSTN vs. SIP

**SIP** means **Session Initiation Protocol**. It is a signaling protocol for communications ranging from voice and video calls to data transfers. SIP trunking is the direct connection and data routing from one phone to another between a business and an **Internet Service Provider** (**ISP**).

VoIP systems don’t use dedicated lines. Instead, the data packets use routers and the internet. Each data packet travels through the least congested and shortest path that PSTNs aren’t smart enough to do.


VoIP has many advantages over the PSTN: 
* you can create calling systems as simple or complex as your needs require, fitted with automations;
* conferencing capabilities;
* advanced privacy and security configurations;
* call recording, translation, transcription, and storage;
* integrations with other communications channels such as messaging or video;
* and much more—all on a network that is built to scale.

With SIP, complexity is also reduced. You can start using it right away after set up as it doesn’t require hardware.

### PSTN vs. Hosted PBX

A **hosted PBX** or **hosted phone system** is a **cloud-based solution that connects your phone system to the cloud**, giving you all the benefits of a VoIP system while still offering you the use of traditional phone systems and hardware. With this alternative, you no longer worry about set-up, installation, and maintenance fees.

### PSTN vs. ISDN

Both PSTN and **Integrated Services Digital Network** (**ISDN**) carry voice over traditional copper-based telephone lines or fiber optic cables but with some inherent differences.

|PSTN|ISDN|
|--|--|
|Traditional analog phone system|Digital telecommunications system|
|Supports basic voice calls and limited data services such as faxing and dial-up internet connections|Offers high-quality, faster, and reliable voice, data, and video transmission compared to PSTN|
|Cheaper but fewer features offered|Offers high-quality, faster, and more reliable voice, data, and video transmission compared to PSTN|

ISDNs aren’t used these days. It was one of the first forms of higher-speed internet in the days of dial-up.

https://www.techtarget.com/

https://www.patton.com/whitepapers/intro-to-ss7-tutorial/ or https://www.patton.com/whitepapers/intro_to_ss7_tutorial.pdf or [pdf](/documents/intro_to_ss7_tutorial.pdf)

https://www.cspsprotocol.com/ss7-protocol-ss7-protocol-tutorial/

https://en.wikipedia.org/wiki/Signalling_System_No._7

https://www.techtarget.com/searchsecurity/answer/What-is-the-SS7-protocol-and-what-are-its-security-implications

https://ss7.info/ss7-map/