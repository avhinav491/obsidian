**Day 12**: https://youtube.com/live/HtT6DHSnAAE

check [linux capstone] 

read [handbook] if any difficulty occur in solving capstone 

use ova file if u dont have try hack me premium 
set bridge adapter 


assignment details mentioned 
- [ctf]
- bandit 25
- linux notes
- network notes
- [linux capstone]



networking start 
# intro in networking 
internet named arpnet used for militry in starting days
data flow  is very fast these days due to internet
network require set of rules to make networking possible
wired and wireless are its type 

key points
- sending email
- browsing 
- acessing remote server

[lifi] 

why matter ?
 to understand nodes communication to compromise device
core of cyber attack 

[pentester] :ethical hacker or tester
[ip address] :unique address for device communication
[mac address] :unique identifier assigned to device

mac details identifier

mac look up


[port] :virtual port & physical port 
 entry point to transfer data. define protocol to use from ip to connect
 
 
[protocol] : rules to define how data must be transfer
bodyguard 
scp is port 
[dns] : domin name map with ip adress so u dont have to know ip address

[firewall] :bodyguard that scan traffic . it analyse traffic and decide wheather to pass data or not

[router ] : dallal , it send your traffic to internet

[subnet] : to manage network , we use subnet to divide bandwith and manage network seperately
it manage ip shortage 


race condition vulnerability 
networking model

[osi model] 
it is conceptual framework which discribe how data must follow

it help to know your network related issue more clearly

understanding vulnerability better

layers and their functions 
- img here


check bowser raw data by inspecting and going to network tab
see ssl cert and its public key.it encrypt data

transport layer is where which protocol to use is decided

network layer 
it find shortest path and cheapest and efficient 


ospf in routing

data link handle data connection

about layer 
layer 7

human interaction happen here. eazy interface 
browsing is done in application layer
email smtp, 
ftp is noe dissapearing 


layer 6 
[encryption] and comress in format 
data compress vulnebrality
serialize format
rendering engine
v8 engine make execution happen for application

encrypt tls /ssl
encode ascii and data compression zip ,mp3

layer 5 
handle session and manage /start/end
so lesser need to have secure connection at each time somthing is shared like group of packets
it also endure u dont need to login each time
it make sure data is from same sesssion
cookies sharing 

layer 4
it ensure data ia in proper order and has two main protocol
they are tcp and udp

tcp [three way handshake] image here

tcp 
aligned order and no faulty data is assured using flags

it make sure server is there

do they do it for each data?
tcp has flags 
it resend part which might be tampered

udp dont care 
client send multiple req and server response
live stream work in udp
wired decrease delay
udp is used for heavy data that needed to be transfered fast 

layer 3
it find best way to the desired server . it also calculate cost due to long cables
network map the path. it  use routing table for this by algorithim like ospf

ospf in bachelor
there are more efficient algorithim,google map or pathao use a*
algorithim are great 
its also in w3 dsa
a* is among best


layer 2
it handle the directly connected device in lan 
mac has sub layer ,llc and mac
it deald with frame ,mac and error detection

osi model pdu img added
raw data which is actual data is from session layer
burpsuite show session layer data
http has header block diagram
tcp header diagram 
checksum handles error

padding is mentioned

explore wireshark for frames

layer 1
data is made 01010 and it is transfered through eletricity or ligh tor signals 
actual raw data is transported here

tcpip

its practical and error are check though this model
as it wasn't planned to have internet while development of osi model, the tcp has different names of layers and is practically used

**Day 13**: https://youtube.com/live/9fO4OGDNYBU

Ip Address : 
ipv4
32bits 
its oldest 
its most used 
about 4.3billions 
eg 
192.168.1.1
each device need one ip address

ipv4 address have 4 octate seperated by .
each octet is 0-255



Subnetting 

ipv6
it has 128 bits
ipv6 is made due to sortage of ipv4
it not implemented comp;etely due to company problem to shifts to ipv6
it will take years to change it

it might come within 15 years 

pentester deals woth both

mac address

it is assigned to each hardware for internet 
assigned by manifacture
its a serial number

its layer 2 thing

address resolution protocol arp

it resolve ip and mac


in a netwoek 
arp 

arp is used to send a  boardcast msg to find who as desired ip adress and ask for its mac address for the requester



arp spoofing 

public vs private ip and nat

ip divided by class, version and type

it solve the problem with limited ipv4 
its jugard

public ip adresss is all ip adress that can be pinged by using internet

its like phone no

private adress is only for devices 
we need to buy the public ip adress

 we arent assigned public ip adress by isp and we cant run site on our private ip

onion router is different

private ip can be different inside different public ip


private ip cannot be reached by the internet


nat
private ip ask router to send its request  then router send it to find shortest path 
nat table is used in router to distintify what each devicd need to access 

router gets the ipdatagram

router gets ip datagram and sends the frame to required ip addresss

in receiving 

youtube sends reply to the router public address

router use the source and destination and nat table to find which device needs the specific info 

buying ip adress make it easy but its not easy process in nepal 


vps has its own ip adress and it can be used for direct communication 

vps need to be boought

using nat and private ip address we get to use more devices in internet

nat uses port to know where to send its data in router

ngxrok service also has similar concept in how its work

tunneling mentioned

ngxrok is freee but need credit card

router also has cache

 we are mitigating to ipv6 

subnetting 

it allow to manage multiple types of devces



cidr notation mentioned

subnetting divide the ip adress into a range so we can use certain range for seperate purposes



curl ipinfo.io 

doing curl is asking send me the info router ask
 curl also has a gui website to see it
 



curl cimmand used

router has both private and public ip

router mostly has the default ip address

ipcalc is used to do  the subnetting
 subnetmask tell which part is network part and board cast  part is host part by bitwise anding and oring
network and boardcast adress isnt usable part





















































