# Explore-JSON-Objects-and-Scripts-in-Python-IOS-XE

```
enable
guestshell enable
```
The guestshell enable command uses the management virtual routing and forwarding (VRF) instance for networking.
```
Rtr-1# guestshell run python 
Python 2.7.5 (default, Apr 17 2016, 14:00:29) 
[GCC 4.8.2 20160413] (Red Hat 4.8.2-16) on linux2 
Type "help", "copyright", "credits" or "license" for more information. 
>>>
```
Create the following dictionary. You will see how a dictionary object with key-value pairs natively maps to JSON objects of name-value pairs. They are essentially the same thing.
```
>>> neighbor = {'hostname': 'Rtr-1', 'os': 'ios-xe', 'model': 'CSR1000v'}  
>>>
```
```
>>> type(neighbor) 
<type 'dict'> 
>>>
```
```
>>> import json 
>>> 
>>> print json.dumps(neighbor, indent=4) 
{ 
    "model": "CSR1000v",    
    "hostname": "Rtr-1",    
    "os": "ios-xe"        
} 
>>>
```
```
>>> data = json.dumps(neighbor, indent=4) 
>>> 
 
First print it as a string literal. 
 
>>> data =
'{\n    "model": "CSR1000v", \n    "hostname": "Rtr-1", \n    "os": "ios-xe"\n}' 
>>> 
 
Now use the print statement. 
 
>>> print data 
{ 
    "model": "CSR1000v",    
    "hostname": "Rtr-1",    
    "os": "ios-xe"   
}
```
```
>>> data_dict = json.loads(data) 
>>> data_dict['os'] 
u’ios-xe 
>>> 
If you tried access os from data, you would see this error: 
>>> data['os'] 
Traceback (most recent call last): 
  File "<stdin>", line 1, in <module>   
TypeError: string indices must be integers, not str 
>>>
```
```
>>> json.dumps(neighbor)    
'{"model": "CSR1000v", "hostname": "Rtr-1", "os": "ios-xe"}'
>>>
```
