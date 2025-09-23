## Class-5: Static Routing Setup

1. **Setup devices and connect using wires**
   - Connect routers and devices physically
   - Ensure proper cable connections

2. **Router WIC-2T and router restart**
   - Install WIC-2T module if needed
   - Restart router to recognize new hardware

3. **Give IP address**
   - Configure IP addresses on interfaces
   - Example: `interface GigabitEthernet0/0 ip address 192.168.1.1 255.255.255.0`

4. **Add static route**
   - Navigate to routing configuration
   - Add static route with next hop
   - Example: `ip route 192.168.2.0 255.255.255.0 192.168.1.2`
   
![class5](/assets/5.static_routing.png)
<!--  <img src="https://github.com/masterArnob/CN-Lab/blob/main/class%205.png" /> -->



## Class-6: RIP V1 Setup

1. **Setup devices and connect using wires**
   - Connect routers and devices physically
   - Ensure proper cable connections

2. **Router WIC-2T and router restart**
   - Install WIC-2T module if needed
   - Restart router to recognize new hardware

3. **Give IP address**
   - Configure IP addresses on interfaces
   - Example: `interface GigabitEthernet0/0 ip address 192.168.1.1 255.255.255.0`

4. **Add rip route**
   - Navigate to routing configuration

![class6](/assets/6.rip_1.png)
![class6](/assets/6.rip_2.png)
![class6](/assets/6.rip_3.png)
![class6](/assets/6.rip_4.png)




 ## Class-7: OSPF Setup

1. **Setup devices and connect using wires**
   - Connect routers and devices physically
   - Ensure proper cable connections

2. **Router WIC-2T and router restart**
   - Install WIC-2T module if needed
   - Restart router to recognize new hardware

3. **Give IP address**
   - Configure IP addresses on interfaces
   - Example: `interface GigabitEthernet0/0 ip address 192.168.1.1 255.255.255.0`

4. **Add ospf route**
   - Navigate to routing configuration
   - router config then
   ```
   en
   config t
   router ospf 1
   network 192.168.10.0 0.0.0.255 area 0
   network 10.0.0.0 0.255.255.255 area 0
   network 11.0.0.0 0.255.255.255 area 0
   
   ```

![class7](/assets/ospf.png)
![class7](/assets/ospf_1.png)
![class7](/assets/ospf_2.png)
![class7](/assets/ospf_3.png)
![class7](/assets/ospf_4.png)




 ## Class-8: Static Nat Setup

1. **Setup devices and connect using wires**
   - Connect routers and devices physically
   - Ensure proper cable connections

2. **Router WIC-2T and router restart**
   - Install WIC-2T module if needed
   - Restart router to recognize new hardware

3. **Give IP address**
   - Configure IP addresses on interfaces
   - Example: `interface GigabitEthernet0/0 ip address 192.168.1.1 255.255.255.0`

4. **Add ospf route**
   - Go to private network router
   ```
   en
   config t
   ip nat inside source static 192.168.20.2 10.0.0.2
   ip nat inside source static 192.168.20.3 10.0.0.2
   go to fatEthernet 0/0 and then cli
   ip nat inside
   go to serial 1/0
   ip nat outside
   go to static
   Network: 192.168.10.0
   Subnet Mask: 255.255.255.0
   Next Hop: 10.0.0.1
   ```
   5. Ping 
   ```
   ping 192.168.10.2
   ping 192.168.20.3
   ```

![class8](/static_nat.png)




