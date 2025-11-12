# 👨‍🎓 Operadors de Comparació i Estructures de Control en Python

## ♦️ Operadors de Comparació

En general, la condició que segueix l'`if` conté un o més dels operadors següents:

- `<` (menor) — la condició és cert si el costat esquerre és menor que el costat dret
- `>` (major) — la condició és cert si el costat esquerre és més gran que el costat dret
- `<=` (menor o igual)
- `>=` (major o igual)
- `==` (igual)
- `!=` (diferent) — indica que no és igual

## ♦️ Tipus de Dades Bool i Operadors Lògics

Els operadors de comparació ens permeten avaluar expressions on el resultat és un valor booleà `True` o `False`.

### 🔍 Exemple d'operadors de comparació
```python
a = 10
b = 5

print(a < b)   # False → 10 no és menor que 5
print(a > b)   # True  → 10 és més gran que 5
print(a <= b)  # False → 10 no és menor ni igual que 5
print(a >= b)  # True  → 10 és més gran o igual que 5
print(a == b)  # False → 10 no és igual a 5
print(a != b)  # True  → 10 és diferent de 5
```

## ♦️ Els Operadors Lògics

Els operadors lògics (o booleans) serveixen per combinar o modificar condicions en un programa. S'utilitzen sobretot dins d'expressions que retornen `True` o `False`, per exemple en els `if`.

- **`and`** → Retorna `True` només si totes les condicions són certes
- **`or`** → Retorna `True` si com a mínim una de les condicions és certa
- **`not`** → Inverteix el valor lògic. Si és `True`, el converteix en `False`, i viceversa

### 🔍 Exemple d'operadors lògics
```python
edat = 20
nota = 8
registre = True

print(edat > 18 and nota >= 5)   # True → totes dues condicions són certes
print(edat > 18 or nota >= 9)    # True → almenys una de les dues és certa
print(not registre)              # False → inverteix el valor de True a False
```

## ♦️ Estructura de Control `if`
```python
if condició:
    # bloc-cert
    # diverses instruccions que s'executen
    # si la condició s'avalua com a Cert
```

### 🔍 Exemple `if`
```python
day = 'Dissabte'
if day == 'Dissabte':  # Evaluem si el dia és igual a Dissabte
    print("És festa!")

lucky_number = 3

if lucky_number == 3:  # Evaluem si el nombre coincideix
    print("Has endevinat el nombre :)")

if lucky_number != 3:  # Evaluem si el nombre és diferent
    print("No has endevinat el nombre")
```

### 🔍 Exemple `if` i operador lògic `and`
```python
punts = 120
energia = 80

if punts > 100 and energia > 50:
    print("Has desbloquejat el nivell secret!")
```

⚠️**Observació:** Només s'executa si totes dues condicions són certes: més de 100 punts i més de 50 d'energia.

## ♦️ Estructura de Control `if-else`
```python
if condició:
    # bloc-cert
    # diverses instruccions que s'executen
    # si la condició s'avalua com a Cert
else:
    # bloc-fals
    # diverses instruccions que s'executen
    # si la condició s'avalua com a Fals
```

### 🔍 Exemple `if-else`
```python
number = int(input("Introdueix la nota de l'examen: "))

if number >= 5:
    print("Has aprovat l'examen")
else:
    print("Has suspès l'examen")

energia = 20

if energia > 0:
    print("El jugador encara pot continuar.")
else:
    print("Game Over!")
```

### 🔍 Exemple `if-else` i operador lògic `or`
```python
municio = 0
armaEspecial = True

if municio > 0 or armaEspecial:
    print("Pots atacar l'enemic!")
else:
    print("No tens cap manera d'atacar.")
```

⚠️**Observació:** S'executa el primer bloc si hi ha munició o si tens arma especial.

## ♦️ Estructura de Control `if-elif-else`
```python
if condició:
    # bloc-cert
elif altra_condició:
    # bloc-alternatiu
elif altra_condició:
    # bloc-alternatiu
else:
    # bloc-fals
```

⚠️**Observació:** Podem tenir una o més d'una condició `elif`.

### 🔍 Exemple `if-elif-else`
```python
punts = 85

if punts >= 90:
    print("Nivell Mestre!")
elif punts >= 70:
    print("Nivell Avançat.")
else:
    print("Nivell Principiant.")
```

### 🔍 Exemple `if-elif-else` amb operadors lògics `not` i `and`
```python
visible = False
energia = 30

if not visible and energia > 20:
    print("Estàs ocult i preparat per atacar.")
elif visible and energia > 20:
    print("Et veuen, però tens prou energia per defensar-te.")
else:
    print("Necessites descansar o amagar-te millor.")
```

⚠️**Observació:** `not visible` vol dir que el jugador no és visible (està amagat). Les altres condicions controlen si pot atacar o ha de descansar.

## ♦️ Condicions Anidades

Les condicions anidades permeten crear decisions més complexes i jeràrquiques.

### 🔍 Exemple de condicions anidades
```python
vida = 60
energia = 40
nivell = 5

if vida > 0:  # Primer comprovem que el jugador estigui viu
    print("El jugador és viu.")
    
    if energia > 30:  # Condició dins de la primera
        print("Tens prou energia per continuar lluitant.")
        
        if nivell >= 5:  # Una tercera condició dins de l'anterior
            print("Has desbloquejat una habilitat especial!")
        else:
            print("Encara no tens prou nivell per l'habilitat especial.")
    else:
        print("L'energia és baixa, busca un punt de descans.")
else:
    print("Game Over!")
```

⚠️**Com funciona:**

- El primer `if` comprova si el jugador està viu
- Si és així, dins d'aquest bloc hi ha un altre `if` que comprova l'energia
- I dins d'aquest segon, un tercer `if` que comprova el nivell

Això permet crear decisions més complexes i jeràrquiques, molt útils en videojocs o lògiques de joc (menús, combats, diàlegs...).
