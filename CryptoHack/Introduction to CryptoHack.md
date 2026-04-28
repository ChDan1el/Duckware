## 1)Finding Flags - FLAG: crypto{y0ur_f1rst_fl4g}

## 2)Great Snakes - FLAG: crypto{z3n_0f_pyth0n}

## 3)ASCII - 
```python
numeros = [99, 114, 121, 112, 116, 111, 123, 65, 83, 67, 73, 73, 95, 112, 114, 49, 110, 116, 52, 98, 108, 51, 125]

for x in numeros:
    print(chr(x),end="")
```
## FLAG: crypto{ASCII_pr1nt4bl3}

## 4) Hex
```python
string = "63727970746f7b596f755f77696c6c5f62655f776f726b696e675f776974685f6865785f737472696e67735f615f6c6f747d"

print(bytes.fromhex(string))
```
## FLAG: crypto{You_will_be_working_with_hex_strings_a_lot}

## 5)  Base64
```python
import base64

string = "72bca9b68fc16ac7beeb8f849dca1d8a783e8acf9679bf9269f7bf"

print(base64.b64encode(bytes.fromhex(string)))
```
## FLAG: crypto/Base+64+Encoding+is+Web+Safe/

## 6) Bytes and Big Integers
```python
from Crypto.Util.number import *

string = 11515195063862318899931685488813747395775516287289682636499965282714637259206269

print(long_to_bytes(string))
```
## FLAG: crypto{3nc0d1n6_4ll_7h3_w4y_d0wn}

## 7) XOR Starter
```python
from Crypto.Util.number import *

string = "label"
key = 13

resultado = ""

for letra in string:
    resultado+= chr(ord(letra)^key)

print("crypto{"+resultado+"}")
```
## FLAG: crypto{aloha}


## 8) XOR Properties
```python
from Crypto.Util.number import *

hex2and3 = "c1545756687e7573db23aa1c3452a098b71a7fbf0fddddde5fc1"
hex1 = "a6c8b6733c9b22de7bc0253266a3867df55acde8635e19c73313"
hexflag = "04ee9855208a2cd59091d04767ae47963170d1660df7f56f5faf"

h2and3byte = bytes.fromhex(hex2and3)
h1byte = bytes.fromhex(hex1)
hflagbyte = bytes.fromhex(hexflag)

numh23 = bytes_to_long(h2and3byte)
numh1 = bytes_to_long(h1byte)
numflag = bytes_to_long(hflagbyte)

longflag = numh23 ^ numh1 ^ numflag

byteflag = long_to_bytes(longflag)

print(byteflag)
```
## FLAG: crypto{x0r_i5_ass0c1at1v3}

## 9)Favourite byte
```python
string = "73626960647f6b206821204f21254f7d694f7624662065622127234f726927756d"

bytestring = bytes.fromhex(string)

for key in range(256):
    flag = ""

    for byte in bytestring:
        flag += chr(byte ^ key)

    if "crypto" in flag: 
        print(flag)
        print("key:",key)
        break
```

## FLAG: crypto{0x10_15_my_f4v0ur173_by7e}

## 10)You either know, XOR you don't

```python
from itertools import cycle

cipher_hex = "0e0b213f26041e480b26217f27342e175d0e070a3c5b103e2526217f27342e175d0e077e263451150104"

cipher = bytes.fromhex(cipher_hex)

known = b"crypto{"

key_start = bytes([c ^ p for c, p in zip(cipher, known)])

print(key_start)
```

```python
from itertools import cycle

cipher_hex = "0e0b213f26041e480b26217f27342e175d0e070a3c5b103e2526217f27342e175d0e077e263451150104"

cipher = bytes.fromhex(cipher_hex)

key = b"myXORkey"

flag = bytes([c ^ k for c, k in zip(cipher, cycle(key))])

print(flag.decode())
```

## FLAG: crypto{1f_y0u_Kn0w_En0uGH_y0u_Kn0w_1t_4ll}
