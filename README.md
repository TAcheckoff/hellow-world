# hellow-world
final project
By Abiy Abebe and Habtamu Bonso
client side

import GPi.GPIO as GPIO            #import GPIO LIBRARY
import time                         #import time library
GPIO.setmode(GPIO.BCM)              #set GPIO pin numbering

import socket                       #import socket module

HOST, PORT ='xxx.xxx.xxx.xxx', xxxx  #Put the ip address and port number
Data_Tobe_Send = "station number"      #Data that you want to transmit\
data = ""
data += str(Data_Tobe_Send)
TRIG = 18                         #pin number on the GPIO,which connect to Sonar TRIG PIN
ECHO = 24                        #pin number on the GPIO,which connect to Sonar ECHO PIN
sock = socket.socket(socket.AF_INET,socket.SOCK_STREAM)
	
GPIO.setup(TRIG,GPIO_OUT)       #SET pin as GPIO OUT
GPIO.setup(ECHO,GPIO_IN)       #SET pin as GPIO IN

def distance()
   GPIO.output(TRIG,True)
   time.sleep(0.00001)

   GPIO.output(TRIG,False)
   pulse_start = time.time()
   pulse_end = time.time()

   while GPIO.input(ECHO)==0:      #check whether the echo low
    pulse_start = time.time()      #save the last time of low pulse

   while GPIO.input(ECHO)==1:     #check whether the echo is at high pulse
    pulse_end = time.time()       #save the las time high pulse captured

   pulse_duration = pulse_end-pulse_start      #Get pulse duration to a variable 
   dist = (pulse_duration*34300)/2    #Multiply pulse duration by 17150 to get distance
   return distance

if __name__ =='main__':
   try:
     while True
       dist = distance()
       print("Mesasured distance = %0.f cm" %dist)
       time.sleep(1)

       if dist>2 and dist<10:
           while 1:
             sock.connect((HOST,PORT))
             sock.sendall(bytes(data+"\n")) 
             data = sock,recv(1024)
             print(data)
             sock.close()
   except KeyboardInterrupt:

       print("measure stoped")
       GPIO cleanup    
