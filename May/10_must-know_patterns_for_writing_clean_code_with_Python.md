## 10 must-know patterns for writing clean code with Python π
https://dev.to/alexomeyer/10-must-know-patterns-for-writing-clean-code-with-python-56bf

1. ν΄λ¦°μ½λλ highly focused λμ΄μΌνλ€.
    - κ° ν΄λμ€, ν¨μ, λͺ¨λμ ν  μΌμ μ λλ‘ ν΄μΌ νλ€.
2. ν΄λ¦°μ½λλ μ½κΈ° μ¬μμΌ νλ€.
3. ν΄λ¦°μ½λλ λλ²κ·ΈνκΈ° μ¬μμΌ νλ€.
4. ν΄λ¦°μ½λλ μ μ§λκΈ° μ¬μμΌ νλ€.
  - λ€λ₯Έ κ°λ°μμ μν΄ ν₯μλκΈ° μ¬μμΌ νλ€.
5. ν΄λ¦°μ½λλ μ±λ₯μ΄ μ’μμΌ νλ€.

**********

#### Naming Convention

1. κΈΈκ³  μ€λͺμ΄ μ λμ΄ μλ μ΄λ¦μ μ¨λΌ => μ½λ©νΈλ₯Ό λ§λΆμΌ μ΄μ κ° μμ΄μ§λ€
```Python
# auλ number of activer users
au = 105
# better
total_active_users = 105
```

2. μλκ° λνλλλ‘ μ¨λΌ
```Python
c = ['UK','USA']
for x in c:

#better
cities = ['UK','USA']
for city in cities:
```

3. μ λ§€ν μ€μλ§μ μ§μν΄λΌ
4. μΌκ΄λ κ·μΉμ μ¬μ©ν΄λΌ (κ΅¬μ‘°, λ³μλͺ, ν¨μλͺ, κ²½λ‘λͺμλ)
```Python
#bad code
def fetch_clients(response, variable):
    # do something
    pass

def fetch_posts(res, var):
    # do something
    pass

# Recommended
def fetch_clients(response, variable):
    # do something
    pass

def fetch_posts(response, variable):
    # do something
    pass
```
5. ν­μ μλν° λ΄μμ μ½λλ² μ΄μ€μ μ΄μλ₯Ό μΆμ ν΄λΌ
6. λ§€μ§λλ²λ₯Ό μ°μ§λ§λΌ ex) random.randint

#### Functions
1. ν¨μλͺ κ·μΉμ΄ μΌκ΄λκ² νλΌ
2. ν κ°μ§ μΌμ μ ν΄λ΄κ² νλΌ
3. Boolean flags λ₯Ό μ°μ§ λ§μλΌ

#### Classes
1. λΆνμν λ΄μ©μ λ΄μ§ λ§μλΌ

#### μ ννλμ΄ μλ μ½λλ₯Ό μ μ§νκΈ° μνλ€λ©΄,
- λ‘μ§μ μ¬λ¬κ°μ νμΌμ΄λ ν΄λμ€λ‘ λλκ³  λͺ¨λλ‘ λΆλ¬μλΌ

- κ²°λ‘  : ν΄λ¦°μ½λλ‘ technical debt λ₯Ό μ€μ¬μΌ νλ€.
