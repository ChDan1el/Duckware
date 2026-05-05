## Greatest Common Divisor
```python
maior = 66528
menor = 52920

while(True):
    resto = maior % menor
    if(resto == 0):
        break
    inteiro = int(maior/menor)
    maior = menor
    menor = resto

print(menor)
```
## FLAG: 1512

## Modular Arithmetic 1
```python
print(11%6,8146798528947%17)
```
## FLAG: 4
