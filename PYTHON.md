<div style="color:#588157">PYTHON</div>

```python
print("WELCOME ROLERCOASTER\n")
print("---------------------\n")
age = int(input("Que edad tienes? "))
foto = input("Quieres foto? (y/n) ")
ticket = 5

if age > 18:
    ticket = 7

if foto == "y":
    ticket = ticket + 3

print(f"El costo de tu boleto sera: {ticket}")
```