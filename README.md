# Handy-Stuufs
1)Add correct host key in known_hosts" / multiple ssh host keys per hostname?

2)How to use REMOTE DESTOP CONNECTION in place of VNC viewer:
https://github.com/amiteshkr63/Handy-Stuufs/blob/main/README.md#how-to-use-remote-destop-connection-in-place-of-vnc-viewer

3)Interfacing LCD with RaspberryPi:

4)How to convert Dynamic IP of RaspberryPi3 to Static ip:

## Add correct host key in known_hosts" / multiple ssh host keys per hostname?
https://serverfault.com/questions/321167/add-correct-host-key-in-known-hosts-multiple-ssh-host-keys-per-hostname

![Screenshot (1875)](https://user-images.githubusercontent.com/88953654/137610042-8ebbc775-d9eb-42de-a46e-5c45d8ce2596.png)

> get the rsa key of your server, where server_ip is your server's IP address, such as 192.168.2.1:
> 
`ssh-keyscan -t rsa server_ip`
> 
> Sample response:
> 
> # server_ip SSH-2.0-OpenSSH_4.3
> server_ip ssh-rsa AAAAB3NzaC1yc2EAAAABIwAAAQEAwH5EXZG.......................
> and on the client, copy the entire response line server_ip ssh-rsa AAAAB3NzaC1yc2EAAAABIwAAAQEAwH5EXZG..., and add this key to the bottom of your ~/.ssh/known_hosts file:
> 
> server_ip ssh-rsa AAAAB3NzaC1yc2EAAAABIwAAAQEAqx9m529...(the offending key, and/or the very bottom of the `known_hosts` file)
> server_ip ssh-rsa AAAAB3NzaC1yc2EAAAABIwAAAQEAwH5EXZG... (line you're adding, copied an

## How to use REMOTE DESTOP CONNECTION in place of VNC viewer

ssh to raspberry:

then install these:

`sudo apt-get install xrdp `

`sudo apt-get install tightvncserver`

![Screenshot (1757)](https://user-images.githubusercontent.com/88953654/136336086-f2246adc-06e8-4515-a799-f324ea41ad39.png)

![Screenshot (1758)](https://user-images.githubusercontent.com/88953654/136336166-722fcf37-b2ab-4a70-beea-c0340fb6701d.png)

### Choose "YES" here in upper screenshot

![Screenshot (1760)](https://user-images.githubusercontent.com/88953654/136336204-6bd08d55-fb30-46a8-8e00-2894c2033c2d.png)

![Screenshot (1761)](https://user-images.githubusercontent.com/88953654/136336222-1bfece82-febd-432e-ae85-aa750cf231a6.png)

## Using Ethernet cable and Laptop(via Remote Desktop):
  Just type "raspberrypi" or "<ip_address_of_raspberrypi>" in "Remote Desktop Connection"
  
### Interfacing LCD with RaspberryPi:
  
  https://github.com/amiteshkr63/Handy-Stuufs-about-Raspberrypi/blob/3759c14dcabc358111c9ff16512a738c631d2fa5/LCD%20Installation%20on%20RaspberryPi.docx
  
  
  Reference:
  
  https://trickiknow.com/raspberry-pi-3-complete-tutorial-2018-lets-get-started/
 ![robu-10-1](https://user-images.githubusercontent.com/88953654/147870937-edfcb7a6-716c-438d-889e-13de4ff21482.jpg)

## How to convert Dynamic IP of RaspberryPi to Static ip:

`
vi /etc/netplan
`

> paste below lines in vi /etc/netplan

 network:
   ethernets:
     eno1:
       dhcp4: no
       addresses: [172.16.100.129/24]
       gateway4: 172.16.101.254
       nameservers:
               addresses: [8.8.8.8,8.8.4.4]
     enp4s0:
       dhcp4: true
   version: 2
   
> See the netplan.txt for Format
   
                OR
      
sudo /etc/netplan

sudo apt-get install netplan
        
        
