---
title: Network Automation - How it all started
date: 2023-02-20
categories: [networkautomation, python, herald]
tags: [netdevops,python,netmiko,networkautomation]
author: herald
---
## lighter way of learning python network automation

### <ins> The tale </ins>

Like any major event or turning point in the world history. It started by a group of network engineers who felt jealous of developers who are able to pack the commands to accomplish specific tasks which is called programming. Some popular programming languages include C or python. In this article we focus more on python programming.

We as network engineers daily use commands to know or do some things on our network devices such as router or switch. Generally, these commands are in plain english conveying the intention or the task it accomplishes like `show version` which shows you version of the operating system or our favourite `show ip interface brief` which shows the status of all interfaces along with ip address. In the same way mostly all the commands in python are in plain english. So no need worry of learning any new language. I mean english is enough to understand most of the code but putting them together is the progamming skill.

If you don't have it already please install python in your local computer here - [link to install python](https://www.python.org/downloads/)

Once the python is installed, Open the command prompt and run command `python` you should see the python version and prompt like this `>>>` confirming successful python installation. 
please install jupyter lab as well by running the command `pip install jupyterlab` from command prompt

[Download the jupyter notebook here](https://drive.google.com/uc?export=download&id=1GBNnzaINTZIs_35zN8lPurU1NmAJs06w) to run the code and follow this guided article (Make sure to follow the sequence while running the blocks of code in the notebook, some blocks don't work with out running the previous block)

Real power of python comes from it's kind community, most of people in the community write the code and make it freely available to use and reap the benefits. In the same way a smart guy named __'Kirk Byers'__ went through the hard way and wrote a python module named __'netmiko'__ which is a collection of python scripts useful to handle network operations and configurations. 

### <ins> The path </ins>

How to get 'netmiko' to use it

> Install netmiko - from command prompt run `pip install netmiko` It brings or loads all the code of the netmiko module to our machine to import and run or use

Now take a leap of faith with me and lets use the 'netmiko' module to connect one of Always-On cisco devnet sandboxes using python. Even though things seem blurry now, they will clear with progression of the article. 
Usually, we need host, username, password to connect a network device. Also, We should know IOS on the device to run relavant commands. 

> Run the block of code below


```python
from netmiko import ConnectHandler
sandbox_connection = ConnectHandler(device_type = "cisco_ios", host = "sandbox-iosxe-latest-1.cisco.com", username = "developer", password = "C1sco12345")
print(sandbox_connection.find_prompt())
```
output :
```
csr1000v-1#
```
    

In the code above, We are importing a chunk of code called `ConnectHandler` from netmiko module, This is called class in programming. We use `ConnectHandler` with all the needed parameters packed in between braces `()` to establish connection. Here `sandbox_connection` is an object name which is a label of the
memory location that stores the related information which we can use in the latter parts of the code. This name might be anything, it is just a label to point a particular memory location. `find_prompt` is a function name that returns the prompt after connecting and we are just printing it out usint `print` function.

> In the same way we have a function named `send_command` to send IOS commnads to the device and get output. lets use it and get output of      `show ip int brief`


```python
from netmiko import ConnectHandler
sandbox_connection = ConnectHandler(device_type = "cisco_ios", host = "sandbox-iosxe-latest-1.cisco.com", username = "developer", password = "C1sco12345")
print(sandbox_connection.send_command("show ip int brief"))
```
output:
```
Interface              IP-Address      OK? Method Status                Protocol
GigabitEthernet1       10.10.20.48     YES NVRAM  up                    up      
GigabitEthernet2       unassigned      YES unset  administratively down down    
GigabitEthernet3       unassigned      YES NVRAM  administratively down down    
Loopback56             56.56.56.56     YES manual up                    up      
Loopback82             unassigned      YES unset  up                    up      
Loopback84             75.74.74.78     YES manual up                    up      
Loopback85             unassigned      YES unset  up                    up      
Loopback88             unassigned      YES unset  up                    up      
Loopback100            172.16.100.100  YES other  up                    up      
Loopback123            unassigned      YES unset  up                    up      
Loopback999            unassigned      YES unset  up                    up      
Loopback1000           1.1.1.1         YES manual up                    up 
```     
    

It is getting interesting right? 
> Now lets lets run `show interface GigabitEthernet1` and analyze the output to learn one important concept of python called __'data types'__


```python
from netmiko import ConnectHandler
sandbox_connection = ConnectHandler(device_type = "cisco_ios", host = "sandbox-iosxe-latest-1.cisco.com", username = "developer", password = "C1sco12345")
print(sandbox_connection.send_command("show interface GigabitEthernet1"))
```
output:
```
GigabitEthernet1 is up, line protocol is up 
Hardware is CSR vNIC, address is 0050.56bf.78ac (bia 0050.56bf.78ac)
Description: MANAGEMENT INTERFACE - DON'T TOUCH ME
Internet address is 10.10.20.48/24
MTU 1500 bytes, BW 1000000 Kbit/sec, DLY 10 usec, 
    reliability 255/255, txload 1/255, rxload 1/255
Encapsulation ARPA, loopback not set
Keepalive set (10 sec)
Full Duplex, 1000Mbps, link type is auto, media type is Virtual
output flow-control is unsupported, input flow-control is unsupported
ARP type: ARPA, ARP Timeout 04:00:00
Last input 00:00:00, output 00:00:00, output hang never
Last clearing of "show interface" counters never
Input queue: 0/375/0/0 (size/max/drops/flushes); Total output drops: 2746
Queueing strategy: fifo
Output queue: 0/40 (size/max)
5 minute input rate 3000 bits/sec, 2 packets/sec
5 minute output rate 2000 bits/sec, 2 packets/sec
    44902 packets input, 6516293 bytes, 0 no buffer
    Received 0 broadcasts (0 IP multicasts)
    0 runts, 0 giants, 0 throttles 
    0 input errors, 0 CRC, 0 frame, 0 overrun, 0 ignored
    0 watchdog, 0 multicast, 0 pause input
    41188 packets output, 17832827 bytes, 0 underruns
    Output 0 broadcasts (0 IP multicasts)
    0 output errors, 0 collisions, 0 interface resets
    0 unknown protocol drops
    0 babbles, 0 late collision, 0 deferred
    0 lost carrier, 0 no carrier, 0 pause output
    0 output buffer failures, 0 output buffers swapped out
```
![GigabitEthernet1_output](/assets/img/favicons/output_ge1.jpg)

Analyze the output above to understand different types of data in python. `Description` of the interface is __MANAGEMENT INTERFACE - DON'T TOUCH ME__ which is a __String__ data type, sequence of characters which forms a word or sentence, simply text is string enclosed between `''` or `""`  Now check the speed above in Mbps, It says __1000__, this __Integer__ data type, they are simply numerics or numbers. We can also have __True__ or __False__ as values which are called __Boolean__ data type.  We have __Float__ data type for decimal point numbers like T1 circuit speed in Mbps __1.544__

Run the code blocks below to understand. `type()` function can be used to know the data type of the data in the object.

```python
description = "MANAGEMENT INTERFACE - DON'T TOUCH ME"
print(type(website))
```
output:
```
<class 'str'>
```

Here `description` is the label of the memory location, called __Object__ which stores the assigned value in python object oriented programming. We are printing out type of the data in the `description` object. Object names can be any word except some reserved words in python so description object type is 'String'

lets explore other types too in the same way.

```python
speed = 1000
print(type(speed))
```
output:
```
<class 'int'>
```

```python
is_status_up = True
print(type(is_status_up))
```
output:
```
<class 'bool'>
```
```python
t1_speed = 1.544
print(type(t1_speed))
```
output:
```
<class 'float'>
``` 
Mostly, In network automation we deal with string data type. So lets learn some string manupulations and use them to get our job done.

Indexing of the string starts from __0__ to __n-1__ where __n__ is the length of the given string. lets manipulte string 'tales of technology'

```python
website_name = 'tales of technology'
print(len(website_name))
```
output:
```
19
```
`len()` function outputs the length of the string

So as observed indexing ends at **18** because it started from **0**

Now lets print out only 'tales' from the string

![website_indices.jpg](/assets/img/favicons/website_indices.jpg)


```python
print(website_name[0:5])
```
output:
```
tales
```    

To split the string by white space run `website_name.split(" ")`
![string_chunks.jpg](/assets/img/favicons/string_chunks.jpg)

```python
print(website_name.split(" "))
```
output:
```
['tales', 'of', 'technology']
```    

Wow! It did created a __list__ of splitted strings, `list` is a collection of data enclosed between `[]` and seperated by `,`. Even list follows the same indexing which starts from __0__ and ends by __length-1__. 

Run the below code to understand


```python
spiltted_website_name = website_name.split(" ")
print(spiltted_website_name)
print(type(spiltted_website_name))

# now using index lets get the first word only

spiltted_website_name[0]
```
output:
```
['tales', 'of', 'technology']
<class 'list'>
'tales'
```

Good! now lets store the output of the `show interface GigabitEthernet1` in an object and manipulate the string to get only the __description__ of the interface

```python
from netmiko import ConnectHandler
sandbox_connection = ConnectHandler(device_type = "cisco_ios", host = "sandbox-iosxe-latest-1.cisco.com", username = "developer", password = "C1sco12345")
output_string = sandbox_connection.send_command("show interface GigabitEthernet1")
print(output_string)
```
output:
```
GigabitEthernet1 is up, line protocol is up 
    Hardware is CSR vNIC, address is 0050.56bf.78ac (bia 0050.56bf.78ac)
    Description: MANAGEMENT INTERFACE - DON'T TOUCH ME
    Internet address is 10.10.20.48/24
    MTU 1500 bytes, BW 1000000 Kbit/sec, DLY 10 usec, 
        reliability 255/255, txload 1/255, rxload 1/255
    Encapsulation ARPA, loopback not set
    Keepalive set (10 sec)
    Full Duplex, 1000Mbps, link type is auto, media type is Virtual
    output flow-control is unsupported, input flow-control is unsupported
    ARP type: ARPA, ARP Timeout 04:00:00
    Last input 00:00:00, output 00:00:00, output hang never
    Last clearing of "show interface" counters never
    Input queue: 0/375/0/0 (size/max/drops/flushes); Total output drops: 22290
    Queueing strategy: fifo
    Output queue: 0/40 (size/max)
    5 minute input rate 46000 bits/sec, 7 packets/sec
    5 minute output rate 108000 bits/sec, 7 packets/sec
        146129 packets input, 35964839 bytes, 0 no buffer
        Received 0 broadcasts (0 IP multicasts)
        0 runts, 0 giants, 0 throttles 
        0 input errors, 0 CRC, 0 frame, 0 overrun, 0 ignored
        0 watchdog, 0 multicast, 0 pause input
        130933 packets output, 90170802 bytes, 0 underruns
        Output 0 broadcasts (0 IP multicasts)
        0 output errors, 0 collisions, 0 interface resets
        0 unknown protocol drops
        0 babbles, 0 late collision, 0 deferred
        0 lost carrier, 0 no carrier, 0 pause output
        0 output buffer failures, 0 output buffers swapped out
```

```python
print(type(output_string))
```
output:
```
<class 'str'>
```
To split the string by line we use `\n` which is the new line character present as a character in multiline strings

```python
splitted_output = output_string.split("\n")
print(splitted_output)
```
output:
```
['GigabitEthernet1 is up, line protocol is up ', '  Hardware is CSR vNIC, address is 0050.56bf.78ac (bia 0050.56bf.78ac)', "  Description: MANAGEMENT INTERFACE - DON'T TOUCH ME", '  Internet address is 10.10.20.48/24', '  MTU 1500 bytes, BW 1000000 Kbit/sec, DLY 10 usec, ', '     reliability 255/255, txload 1/255, rxload 1/255', '  Encapsulation ARPA, loopback not set', '  Keepalive set (10 sec)', '  Full Duplex, 1000Mbps, link type is auto, media type is Virtual', '  output flow-control is unsupported, input flow-control is unsupported', '  ARP type: ARPA, ARP Timeout 04:00:00', '  Last input 00:00:00, output 00:00:00, output hang never', '  Last clearing of "show interface" counters never', '  Input queue: 0/375/0/0 (size/max/drops/flushes); Total output drops: 22290', '  Queueing strategy: fifo', '  Output queue: 0/40 (size/max)', '  5 minute input rate 46000 bits/sec, 7 packets/sec', '  5 minute output rate 108000 bits/sec, 7 packets/sec', '     146129 packets input, 35964839 bytes, 0 no buffer', '     Received 0 broadcasts (0 IP multicasts)', '     0 runts, 0 giants, 0 throttles ', '     0 input errors, 0 CRC, 0 frame, 0 overrun, 0 ignored', '     0 watchdog, 0 multicast, 0 pause input', '     130933 packets output, 90170802 bytes, 0 underruns', '     Output 0 broadcasts (0 IP multicasts)', '     0 output errors, 0 collisions, 0 interface resets', '     0 unknown protocol drops', '     0 babbles, 0 late collision, 0 deferred', '     0 lost carrier, 0 no carrier, 0 pause output', '     0 output buffer failures, 0 output buffers swapped out']
```
Now description is present in the third line so its index is 2 as per the python indices concept. lets filter out only the description line 
![list_of_ge1_output.png](/assets/img/favicons/list_of_ge1_output.png)

```python
desc_line = splitted_output[2]
print(desc_line)
print(type(desc_line))
```
output:
```
Description: MANAGEMENT INTERFACE - DON'T TOUCH ME
<class 'str'>
```
Finally, We are able to retrive only the description of an interface by filtering out all the other output
In this path, We learnt the following

- Connecting the device using netmiko
- Running the commands using send_command
- Objects
- Different data types
- String manipulations

Hope you enjoyed reading the article, My main goal is involve you while reading rather just reading stuff.

To learn more about python and netmiko, please visit their official websites

- python - https://docs.python.org/3/tutorial/index.html
- netmiko - https://pyneng.readthedocs.io/en/latest/book/18_ssh_telnet/netmiko.html

Thank you for reading. Don't forget to complete the challenge below and let me know in the comments below.

### <ins> The challenge </ins>

Using previous learned concepts and the below hints. Do the following

1. Connect to the sandbox using ConnectHandler
2. Get the whole running configuration as by sending the suitable cisco IOS command
3. Create a file named 'run_config.txt' in the current directory
4. Write the configuration from router to this created file

##### <ins> hints </ins>
- To create a new file or to open an existing file in python we use open function Example:- `file_object = open(file_name.txt,'rw')`
- Here `file_object` is an object reference to use in handling the latter operations on the file, `rw` represents that we can do both read and write operations on the file
- `write()` is the function to be used for witing as the name suggests

For your reference, you can read on file handling in the python website [python file handling](https://docs.python.org/3/tutorial/inputoutput.html#reading-and-writing-files)

Thank you for reading. This is part 1 of Network Automation using python.More articles on same topic. Coming soon!

Follow us on [tales of technology](https://talesoftechnology.github.io) for more such articles.

our twitter profile - [toftechnology](https://twitter.com/toftechnology)

My Linkedin profile to follow - [Herald's linkedin](https://linkedin.com/in/herald126/)

please comment below for any queries or feedback