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
