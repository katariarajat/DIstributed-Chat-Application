#  Distributed System Project - Distributed Chat Schema

This is terminal based distributed chat application which uses concept of distributed system such as leader selection, Heartbeat mechanism.

We have used socket library in python and developed chat rooms using multicasting. 

The chat system is fault tolerant, replicated data, is available (CAP Theorem).

### FOLLOW BELOW COMMANDS TO RUN -
    - python3 server.js
    - (run server.js only once in a single machine or use virtual machine)
    - python3 client.js

#### What happens when we run server.js?
##### Ans -
    - server creates a socket
    - Sends receive request to every member of multicast group(To check if there exist another server in the system)
    - If receives an request
        - perform heartbeat mechanism
    - else 
        - make yourself leader
        - listen from clients 
        - listen from multicast receiver 
    - If a server replica crashes and server A detect it
        - if server A is a leader
            - Then it registers server replica crashed and change of network 
        - If server A detects an leader crash
            - It makes itself as leader and send messages to others.

#### What happens when we run client.js?
##### Ans. 
    - It sends JOIN request to multicast group
        - If response received from leader, joins the group and wait for any message or sends message.
        - Else ends the session. 





