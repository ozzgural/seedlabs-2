# SEEDlabs: Exam2 - BGP Exploration and Attack Lab

#### Ozgur Ural
#### Student ID: 2564455

### 2 The Lab Setup and the SEED Internet Emulator

First of all, I downloaded the emulator files. Then run the docker with the following commands.
```sh
$ docker-compose build
$ docker-compose up
```

### 3 Task 1: Stub Autonomous System
#### 3.1 Task 1.a: Understanding AS-155’s BGP Configuration

Task 1.a.1:  Find the peer autonomous system of AS-155, find the BGP route of 10.155.0.254/24, and use cat /etc/bird/bird.conf to query its configuration information.

![image](https://user-images.githubusercontent.com/4716254/200149098-ba95c405-c104-4bd7-a22c-dd4a2d569ab3.png)

It is known from the routing configuration that AS-150 is interconnected with 3 autonomous systems, of which p_as156 has a peer relationship with it:

![image](https://user-images.githubusercontent.com/4716254/200149125-4ae9cde5-716b-4730-9d89-98c65d072d89.png)


Task 1.a.2: AS-155 is interconnected with multiple ASs at the same time, one of which will not affect the AS-155's access to the Internet.

Here we choose to ping the host 10.156.0.72 from 10.155.0.72, and disconnect the links of the BGP routes one by one. If and only when all the links are disconnected, the ping command shows that it is unreachable.

![image](https://user-images.githubusercontent.com/4716254/200149151-9eee0fc3-2220-47fa-af75-121328c21040.png)


#### 3.2 Task 1.b: Observing BGP UPDATE Messages
#### 3.3 Task 1.c: Experimenting with Large Communities
#### 3.4 Task 1.d: Configuring AS-180

### 4 Task 2: Transit Autonomous System
#### 4.1 Task 2.a: Experimenting with IBGP
#### 4.2 Task 2.b: Experimenting with IGP
#### 4.3 Task 2.c: Configuring AS-5
### 5 Task 3: Path Selection
### 6 Task 4: IP Anycast
### 7 Task 5: BGP Prefix Attack
#### 7.1 Task 5.a. Launching the Prefix Hijacking Attack from AS-161
#### 7.2 Task 5.b. Fighting Back from AS-154
#### 7.3 Task 5.c. Fixing the Problem at AS-3