# Basic_MicroProcessor
## 하버드 구조와 폰 노이만 구조도 
![image](https://user-images.githubusercontent.com/76835313/127178190-74c7d6da-ee66-4704-bb7c-d7e3476cd32c.png)
## RISC and CISC Architecture  
![image](https://user-images.githubusercontent.com/76835313/127179214-fd8f3d36-a4af-4608-b9be-1ea7a419a718.png)
## Superscalar architecture 
![image](https://user-images.githubusercontent.com/76835313/127180155-1bdc11d5-a4a6-433e-85e4-f7466d97b3ca.png)
## Little-endian byte ordering
[출처](https://uynguyen.github.io/2018/04/30/Big-Endian-vs-Little-Endian/)  
![image](https://user-images.githubusercontent.com/76835313/127180543-3e8e12ed-f980-4ee0-bcca-aca5c5712c55.png)
In computer science, a bit is the smallest piece of information. It represents a digit of the binary numeral system. A string of 8 bits called a byte. There are two ways to store a string of data in computers: Big Endian and Little Endian. If your tasks are working with data in a piece of bytes, you ought to know how to deal with bytes in these two formats. In this post, I will explain how data is stored in computers, what are the main differences between these two, then provide some useful code to work with bytes in Swift and Objective-C.  

* Basic concepts  
To understand Big Endian and Little Endian, you need to know what the Least Significant Byte (LSB) and the Most Significant Byte (MSB) are. The LSB is the right-most bit in a string, it is called that because it has the least effect on the value of the binary number. In contrast, the left-most byte is the MSB that carries the greatest numerical value.  
After understanding these two, it is easy to distinguish between Big Endian and Little Endian:

* In Big Endian, the MSB of the data is placed at the byte with the lowest address.
* In Little Endian, the LSB of the data is placed at the byte with the lowest address.  
![image](https://user-images.githubusercontent.com/76835313/127180646-1c32bd7e-a675-4661-9ab4-d275de4076fe.png)

* The advantages of Little Endian are:

1. It’s easy to read the value in a variety of type sizes. For example, the variable A = 0x13 in 64-bit value in memory at the address B will be 1300 0000 0000 0000. A will always be read as 19 regardless of using 8, 16, 32, 64-bit reads. By contrast, in Big Endian we have to know in which size we have written the value to read it correctly.
2. It’s easy to cast the value to a smaller type like from int16_t to int8_t since int8_t is the byte at the beginning of int16_t.
3. Easily to do mathematical computations “because of the 1:1 relationship between address offset and byte number (offset 0 is byte 0), multiple precision math routines are correspondingly easy to write.”
