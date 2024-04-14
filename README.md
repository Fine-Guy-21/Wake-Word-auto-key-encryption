# Wake-Word-auto-key-encryption


Word Auto Key Encryption algorithm is a stream cipher algorithm that has been used commercially [6]. This algorithm invented by David Wheeler in 1993. Word Auto Key Encryption algorithm uses 128-bit key length and SBOX table 256 x 32 bits [6]. Word Auto Key Encryption Algorithm uses XOR, AND, OR and Right Shift. The main process of the algorithm consists of [6]:
1. The process of formation of the S-Box table (Substitution Box).
2. The process of formation of the key.
3. The process of encryption and decryption.
The essence of the Word Auto Key Encryption algorithm lies in the formation of S-Box tables and key establishment process. Table S-Box of Word Auto Key Encryption Algorithm is flexible and different for each round [6].

The process of formation of the S-Box table is as follows:
1.  Initialize the value of TT [0] ... TT [7] (in hexadecimal):
TT [0]: 726a8f3b 
TT [1]: e69a3b5c 
TT [2]: d3c71fe5 
TT [3]: ab3c73d2 
TT [4]: 4d3a8eb3 
TT [5]: 0396d6e8 
TT [6]: 3d4c2f7a 
TT [7]: 9ee27cf3 
2.  Initialize the initial value of 
T [0] ... T [3]:
T [0] = K [0]      T [1] = K [1]
T[2] = K[2]      T[3] = K[3]
K [0], K [1], K [2], K [3] resulting from the lock were broken up into 4 parts of equal length.
3.  To T [4] to T [255], do the following:
X = T [n-4] + T [n-1]
T [n] = X >> 3 XOR TT (X AND 7)
4.  To T [0] to T [22], do the following:
T [n] = T [n] + T [n + 89]
5.  Set the value to multiple variables below:
X = T [33]
Z = T [59] OR (01000001h)
Z = Z AND (FF7FFFFFh)
X = (X AND FF7FFFFFh) + Z
6.  To T [0] ... T [255], do the following:
X = (X AND FF7FFFFFh) + Z
T [n] = T [n] AND 00FFFFFFh XOR X
7.  Initialization values for some of the following variables:
T [256] = T [0]
X = X AND 255
8.  To T [0] ... T [255], do the following:
Temp = (T [n XOR X] XOR X) AND 255
T [n] = T [Temp]
T [X] = T [n + 1]

The process of formation Key Word Auto Key Encryption algorithms can determine for n rounds. The more rounds of the process of forming the key, then the data security will be guaranteed. Function used in the process of forming the key is M (X, Y) = (X + Y) >> 8 XOR T [(X + Y) AND 255]. First of all, the key input will be split into four parts and set as the initial value of the variable A0, B0, C0, and D0 [6]. The value of this variable will process through the following steps:
Ai + 1 = M (Ai, Di)
Bi + 1 = M (Bi, Ai + 1)
Ci + 1 = M (Ci, Bi + 1)
At + 1 = M (Di, Ci + 1)
The value of Di is the value of the key Ki.