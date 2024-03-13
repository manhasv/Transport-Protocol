1. High-level approach:
    Sender will send packet to Receiver and Receiver will send acknowledgement back to Sender the two will
    exchange packets.
    Sender will have a sequence number attach to each packet that it sends to Receiver for order and packet control.
    The packet will contain the checksum message for corruption detection, time for timeout and num for sequence number.
    Based on those field, the Receiver will check for sequence number, check if it is out of order or fix an order and send acks accordingly. 
    If a packet is missing, send duplicate acks to notify Sender to resend the missing packet.
    Sender will based on acks received to modify related field like window size, RTT and adjust to the network.
    
2. Challenges:
    It took me a while to find a way to detect corruptions. Eventually I came accross the piazza post mentioning hashlib 
    so I did a quick research and got it done.
    I also had troubles working on a sliding window at first but I got it eventually.

3. A list of properties/features of your design
    Sequence number 
    Corruption detection
    Sliding window
    Adjust window size
    Detect out of order and has window to store packets

4. Testing:
    I ran the configs tests from the starter code along with the autograder from the gradescope website.