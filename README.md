# Final-project-UN
## Calculadora de circuitos y resistencias de diferentes tipos
En el siguiente repositorio explicaremos a detalle cada funcion de dicha calculadora para un mayor entendimiento y proposito ya que sus funciones son muy especifícas.
Comenzando por su estructura este programa utiliza el lenguaje Python para su desarrollo y funcionamiento, complementado con las librerias conocidas como Matplolib, la cual su funcionamiento en el programa es para la graficacion entre corriente y voltaje para la calculadora de resistencia en un sistema.
#### Planteamiento del problema.


Un ingeniero eléctrico desea poder tener un aplicativo en Python que pueda resolver:

1.	Circuitos de polarización DC de configuraciones básicas para transistores BJT NPN.

2.	Calcular por código de colores las resistencias de 4 bandas y 5 bandas con los valores estándar comerciales de tolerancia.

3.	Calcular las corrientes y los voltajes y resistencias totales de circuitos serie y paralelo de resistencias.

4.	Calcular la amplificación de una pequeña señal ac mediante las configuraciones en cascada de fases I y II polarización universal, fase I polarización universal y fase II emisor común con resistencia de emisor, fase I polarización universal y fase II emisor común sin resistencia de emisor, todas las anteriores con el concepto de utilización de by-pass. 

5.	Realizar conversiones de escala de resistencias.

6.	Graficar y definir la resistencia de un sistema mediante dos voltajes y corrientes determinados.

### Requisitos
Requisitos funcionales

●	R1 El programa deberá estar dispuesto en su mayoría mediante funciones.

●	R2 El programa deberá tener gestión de errores de parte del usuario cuando este digite un dato que no sea correcto.

●	R3 El programa se ejecutará en Google Colab.

●	R4 El programa requiere la librería Matplotlib para las graficas de la calculadora de resistencias de un sistema si se quiere ejecutar en un editor de codigo externo a Google Colab.

Requisitos no funcionales

●	R1 El programa estará codificado en Python.

●	R2 El programa debe tener una precisión máxima de 5 decimales, es decir máximo 5 decimales puede mostrar por respuesta.

●	R3 El código debe superar las 800 líneas de código.

#### Datos de entrada
FUNCIONALIDAD 1: Voltajes, resistencia, valor del beta del transistor.

FUNCIONALIDAD 2: Colores del código de colores de las resistencias.

FUNCIONALIDAD 3: Voltaje y valores de 4 resistencias.

FUNCIONALIDAD 4: Voltajes, resistencia, valor del beta del transistor, voltaje de entrada para amplificación

FUNCIONALIDAD 5: Valores numéricos de Resistencias

FUNCIONALIDAD 6: Voltajes, y corrientes.

Especificación: Todos los datos se deben ingresar en unidades del sistema internacional, es decir, en Voltios, Ohmios, Amperios etc.

#### Datos de salinda
FUNCIONALIDAD 1: Voltajes y corrientes del transistor.

FUNCIONALIDAD 2: Valor numérico de las resistencias.

FUNCIONALIDAD 3: Voltajes y corrientes de las 4 resistencias.

FUNCIONALIDAD 4: Voltajes y corrientes del transistor y las amplificaciones parciales, totales y la salida de voltaje total

FUNCIONALIDAD 5: Valores numéricos de Resistencias según la escala

FUNCIONALIDAD 6: Grafica de resistencia en con ejes V vs I y el valor de dicha resistencia

Especificación: Todos los datos se mostrarán en unidades del sistema internacional, es decir, en Voltios, Ohmios, Amperios etc.

### Estrategia de solición
Utilización de fórmulas de cálculo dadas en los libros de electricidad y electrónica.

Utilización de la ley de Ohm.

Utilización de los objetos geométricos asociados al comportamiento proporcional de voltajes y resistencias en un sistema.

Utilización de conocimientos previos para la implementación de las funcionalidades de los transistores polarizados.

### Algoritmo de solución
![image](https://github.com/diegocapera/Final-project-UN/assets/124608110/311ceb0d-1ab2-411c-9055-770190c229eb)



## Calculadora de polarizaciones básicas
Comenzanco con esta calculadora se tienen 4 tipos de circuitos en las cuales se puede usar as cuales son la polarizacion universal, base comun, emisor comun con resistencia de emisor y por ultimo polarizacion de emisor comun.
![Polarizaciones](https://github.com/diegocapera/Final-project-UN/assets/124608110/0ddfa21a-e069-43cf-8dbf-e10c33c9a1db)
![Polarizaciones 2](https://github.com/diegocapera/Final-project-UN/assets/124608110/93d14dd1-c1d7-4cb0-b050-6ab86d0a3db4)

### Polarizacion universal
Este código es una función que calcula las corrientes y voltajes de polarización de un circuito transistorizado en configuración de polarización universal. Los parámetros de entrada son vcc (voltaje de alimentación), r1 y r2 (resistencias de polarización del transistor), rc (resistencia de carga), RE (resistencia del emisor) y beta (ganancia de corriente del transistor). La función utiliza fórmulas de análisis de circuitos para calcular las corrientes de base, emisor y colector, así como el voltaje de colector-emisor y los voltajes de las resistencias de carga y emisor. Los resultados se imprimen en la consola utilizando la función print().
```python
   def p_u(vcc,r1,r2,rc,RE,beta): #funcion de polarizacion universal
    vth = vcc*(r2/(r1+r2))
    rth = ((r1*r2)/(r1+r2))
    Ib = (vth-0.7)/(rth+RE*(beta+1))
    Ie = (beta+1)*Ib
    Ic = beta*Ib
    Vce = vcc - Ic*(rc+RE)
    print(f"\nLa corriente de base es {round(Ib,5)} amperios")
    print(f"La corriente de emisor es {round(Ie,4)} amperios ")
    print(f"La corriente de colector es {round(Ic,4)} amperios")
    print(f"El voltaje de colector emisor es {round(Vce,4)} Voltios")
    print(f"La voltaje de Resistencia de colector es {round((Ic*rc),4)} Voltios")
    print(f"La voltaje de Resistencia de emisor es {round((Ie*RE),4)} Voltios")

```
### Polarizacion de base común
Este código es una función que calcula las corrientes y voltajes de un circuito transistorizado en configuración de polarización común. La función toma cinco parámetros: vcc, vee, rc, RE y beta, que representan el voltaje de la fuente de alimentación positiva, el voltaje de la fuente de alimentación negativa, la resistencia de colector, la resistencia de emisor y la ganancia del transistor, respectivamente.

La función utiliza las fórmulas de análisis de circuitos para calcular la corriente de base (Ib), la corriente de emisor (Ie), la corriente de colector (Ic), el voltaje colector-emisor (Vce) y los voltajes de las resistencias de colector y emisor. Luego, la función imprime los resultados utilizando la función "print".

En resumen, esta función es útil para calcular las corrientes y voltajes de un circuito transistorizado en configuración de polarización común.

```python
  def p_b_c(vcc,vee,rc,RE,beta): #funcion de polarizacion base comun
    Ie = (abs(vee)-0.7)/RE
    Ib = (Ie/(beta+1))
    Ic = beta*Ib
    Vce = abs(vee) + abs(vcc) - Ie*(rc+RE)
    print(f"\nLa corriente de base es {round(Ib,5)} amperios")
    print(f"La corriente de emisor es {round(Ie,4)} amperios ")
    print(f"La corriente de colector es {round(Ic,4)} amperios")
    print(f"El voltaje de colector emisor es {round(Vce,4)} Voltios")
    print(f"La voltaje de Resistencia de colector es {round((Ic*rc),4)} Voltios")
    print(f"La voltaje de Resistencia de emisor es {round((Ie*RE),4)} Voltios")

```
### Polarizacion de emisor comun con resistencia de emisor
El código es una función que calcula las corrientes y voltajes de un circuito transistor de polarización de emisor común con una resistencia de emisor. La función toma cinco parámetros de entrada: vcc (voltaje de la fuente de alimentación), rb (resistencia de base), rc (resistencia de colector), RE (resistencia de emisor) y beta (ganancia de corriente del transistor).

La función calcula la corriente de base (Ib), la corriente de emisor (Ie), la corriente de colector (Ic), el voltaje colector-emisor (Vce) y los voltajes de las resistencias de colector, emisor y base. Luego, los resultados se imprimen utilizando la función "print".

En resumen, esta función es útil para analizar circuitos de transistores de polarización de emisor común con una resistencia de emisor en diferentes configuraciones, y puede ayudar a los ingenieros a diseñar y solucionar problemas en circuitos de transistores.
```python
  def p_e_c_r_e(vcc,rb,rc,RE,beta): #funcion de polarizacion emisor comun con resistencia de emisor
    Ib = (vcc-0.7)/((rb+RE)*(beta+1))
    Ie = (beta+1)*Ib
    Ic = beta*Ib
    Vce = vcc - Ic*(rc+RE)
    print(f"\nLa corriente de base es {round(Ib,5)} amperios")
    print(f"La corriente de emisor es {round(Ie,4)} amperios ")
    print(f"La corriente de colector es {round(Ic,4)} amperios")
    print(f"El voltaje de colector emisor es {round(Vce,4)} Voltios")
    print(f"La voltaje de Resistencia de colector es {round((Ic*rc),4)} Voltios")
    print(f"La voltaje de Resistencia de emisor es {round((Ie*RE),4)} Voltios")
    print(f"La voltaje de Resistencia de base es {round((Ib*rb),4)} Voltios")
```
### Polarizacion de emisor comun
Este es una función de polarización de emisor común en un circuito de transistor. Los parámetros que se le pasan a la función son vcc (voltaje de alimentación), rb (resistencia de la base), rc (resistencia del colector) y beta (ganancia de corriente del transistor). La función calcula las corrientes y voltajes en el circuito usando fórmulas de análisis de circuitos. La corriente de base se calcula dividiendo la diferencia de voltaje entre vcc y la tensión base-emisor (0,7V) por la resistencia de base. La corriente de emisor se obtiene multiplicando la corriente de base por la suma de beta y 1. La corriente de colector es igual a beta por la corriente de base. El voltaje colector-emisor se obtiene restando el producto de la corriente de colector y la resistencia del colector a vcc. Finalmente, se imprimen los valores de las corrientes y voltajes calculados usando la función print().

```Python
  def p_e_c(vcc,rb,rc,beta): #funcion de polarizacion emisor comun
    Ib = (vcc-0.7)/(rb)
    Ie = (beta+1)*Ib
    Ic = beta*Ib
    Vce = vcc - Ic*(rc)
    print(f"\nLa corriente de base es {round(Ib,5)} amperios")
    print(f"La corriente de emisor es {round(Ie,4)} amperios ")
    print(f"La corriente de colector es {round(Ic,4)} amperios")
    print(f"El voltaje de colector emisor es {round(Vce,4)} Voltios")
    print(f"La voltaje de Resistencia de colector es {round((Ic*rc),4)} Voltios")
    print(f"La voltaje de Resistencia de base es {round((Ib*rb),4)} Voltios")

```
### Funciones y valores para la calculadora de polarizaciones básicas
Este es un código que usa una serie de instrucciones "try-except" y "while" para solicitar y validar las entradas de usuario para un programa que resuelve circuitos transistorizados en configuración común emisor, común base y emisor común.
Primero, el código solicita al usuario que ingrese un número entero entre 1 y 4 que representa la opción deseada. Si el usuario ingresa un valor no válido, se muestra un mensaje de error y se le solicita que ingrese un valor válido hasta que lo haga.
Luego, si el usuario selecciona la opción 1, se solicita al usuario que ingrese un conjunto de valores de resistencia y voltaje de entrada para calcular la corriente y el voltaje de salida del circuito en configuración común emisor. Si el usuario selecciona la opción 2, se solicita un conjunto diferente de valores para calcular la corriente y el voltaje de salida en configuración común base. Si el usuario selecciona la opción 3, se solicita otro conjunto de valores para calcular la corriente y el voltaje de salida en configuración emisor común.
Y por último solicita al usuario que ingrese valores para 4 variables (vcc, rb, rc y beta) si la variable c es igual a 4. Primero, el programa verifica si la variable c es igual a 4 con la declaración if (c==4). Si es así, entonces se solicita al usuario que ingrese los valores de vcc, rb, rc y beta utilizando la instrucción de entrada. Después de cada entrada, se verifica si el valor ingresado es aceptable mediante una declaración while. Si el valor ingresado no es aceptable, se solicita al usuario que ingrese un valor válido.
Finalmente, la función devuelve el valor devuelto por otra función llamada pec, que utiliza los valores ingresados para calcular los valores de corriente y voltaje en un circuito de transistor.
En cada caso, si el usuario ingresa un valor no válido, se muestra un mensaje de error y se le solicita que ingrese un valor válido hasta que lo haga. Cuando se han ingresado todas las entradas válidas, se llama a una función específica para calcular y devolver los resultados del circuito según la configuración seleccionada. 
```Python
  try:
      c = int(input())
  except ValueError:
      print("por favor ingrese un dato valido")
      cond = True
      fin = cond
      while(fin == True):
        try:
           c = int(input())
           if(type(c)==int):
            fin=False
        except ValueError:
           print("por favor ingrese un dato valido")
           fin = True
  while(c>4 or c<1):
        print("Por favor ingrese una opcion valida")
        c = int(input())
  if (c==1):
    print("Por favor ingrese los siguientes datos")
    vcc = float(input("Ingrese el valor del Voltaje de colector comun:   "))
    while(vcc<=0):
      vcc = float(input("Ingrese el valor del Voltaje de colector comun mayor a 0:   "))
    r1 = float(input("Ingrese el valor de la resistencia r1 en ohmios:   "))
    while(r1<0):
      r1 = float(input("Ingrese el valor de la resistencia r1 en ohmios:   "))
    r2 = float(input("Ingrese el valor de la resistencia r2 en ohmios:   "))
    while(r2<0):
      r2 = float(input("Ingrese el valor de la resistencia r2 en ohmios:   "))
    rc = float(input("Ingrese el valor de la resistencia rc en ohmios:   "))
    while(rc<0):
      rc = float(input("Ingrese el valor de la resistencia rc en ohmios:   "))
    RE = float(input("Ingrese el valor de la resistencia RE en ohmios:   "))
    while(RE<0):
      RE = float(input("Ingrese el valor de la resistencia RE en ohmios:   "))
    beta = int(input("Ingrese un numero mayor o igual a 50 y menor o igual a 500:  "))
    while(beta<50 or beta>500):
      beta = int(input("Ingrese un numero mayor o igual a 50 y menor o igual a 500:  "))
    return p_u(vcc,r1,r2,rc,RE,beta)

  if (c==2):
    print("Por favor ingrese los siguientes datos")
    vcc = float(input("Ingrese el valor del Voltaje de colector comun:   "))
    vee = float(input("Ingrese el valor del voltaje de emisor aplicado debe ser menor a 0:   "))
    while(vee>=vcc):
      vcc = float(input("Ingrese el valor del Voltaje de colector comun:   "))
      vee = float(input("Ingrese el valor del voltaje de emisor aplicado debe ser menor que el Vcc:   "))
    rc = float(input("Ingrese el valor de la resistencia rc en ohmios:   "))
    while(rc<0):
      rc = float(input("Ingrese el valor de la resistencia rc en ohmios:   "))
    RE = float(input("Ingrese el valor de la resistencia RE en ohmios:   "))
    while(RE<0):
      RE = float(input("Ingrese el valor de la resistencia RE en ohmios:   "))
    beta = int(input("Ingrese un numero mayor o igual a 50 y menor o igual a 500:  "))
    while(beta<50 or beta>500):
      beta = int(input("Ingrese un numero mayor o igual a 50 y menor o igual a 500:  "))
    return p_b_c(vcc,vee,rc,RE,beta)

  if (c==3):
    print("Por favor ingrese los siguientes datos")
    vcc = float(input("Ingrese el valor del Voltaje de colector comun:   "))
    while(vcc<=0):
      vcc = float(input("Ingrese el valor del voltaje de colector comun mayor a 0:   "))
    rb = float(input("Ingrese el valor de la resistencia rb en ohmios:   "))
    while(rb<0):
      rb = float(input("Ingrese el valor de la resistencia rc en ohmios:   "))
    rc = float(input("Ingrese el valor de la resistencia rc en ohmios:   "))
    while(rc<0):
      rc = float(input("Ingrese el valor de la resistencia rc en ohmios:   "))
    RE = float(input("Ingrese el valor de la resistencia RE en ohmios:   "))
    while(RE<0):
      RE = float(input("Ingrese el valor de la resistencia RE en ohmios:   "))
    beta = int(input("Ingrese un numero mayor o igual a 50 y menor o igual a 500:  "))
    while(beta<50 or beta>500):
      beta = int(input("Ingrese un numero mayor o igual a 50 y menor o igual a 500:  "))
    return p_e_c_r_e(vcc,rb,rc,RE,beta)

  if (c==4):
    print("Por favor ingrese los siguientes datos")
    vcc = float(input("Ingrese el valor del Voltaje de colector comun:   "))
    while(vcc<=0):
      vcc = float(input("Ingrese el valor del voltaje de colector comun mayor a 0:   "))
    rb = float(input("Ingrese el valor de la resistencia rb en ohmios:   "))
    while(rb<0):
      rb = float(input("Ingrese el valor de la resistencia rc en ohmios:   "))
    rc = float(input("Ingrese el valor de la resistencia rc en ohmios:   "))
    while(rc<0):
      rc = float(input("Ingrese el valor de la resistencia rc en ohmios:   "))
    beta = int(input("Ingrese un numero mayor o igual a 50 y menor o igual a 500:  "))
    while(beta<50 or beta>500):
      beta = int(input("Ingrese un numero mayor o igual a 50 y menor o igual a 500:  "))
    return p_e_c(vcc,rb,rc,beta)
```
## Calculadora de valor Ohmico por bandas
### Para 4 bandas
El código para 4 bandas es una función llamada fo_b que toma un argumento C (cadena de caracteres) que representa el código de colores de una resistencia en formato de cuatro bandas. La función convierte el código de colores en un valor de resistencia y su tolerancia.

El diccionario "val" contiene las claves que representan los colores de las bandas de la resistencia y sus valores correspondientes, que son números del 0 al 9. La función utiliza un bucle for para recorrer cada letra del código de colores y buscar su valor en el diccionario. Los valores se concatenan en una variable "cont", que representa la resistencia total en ohmios.

La tercera banda representa el factor de multiplicación de la resistencia. Si la banda es negra, no se agrega ningún cero a la resistencia total. Si la banda es marrón, se agrega un cero, si es rojo, se agregan dos ceros, y así sucesivamente.

La cuarta banda representa la tolerancia, que puede ser del 5% (banda dorada) o del 10% (banda plateada). La función utiliza una declaración condicional if para imprimir el valor de la resistencia total y su tolerancia.

```Python
  def fo_b(C): #cuatro bandas
    cont = ""
    val = {"n":"0", "c":"1", "r":"2", "na":"3", "a":"4", "ve":"5", "az":"6", "v":"7", "g":"8", "b":"9"}
    for i,j in val.items():
      if i == C[0].lower():
        cont+=j
    for i,j in val.items():
      if i == C[1].lower():
        cont+=j
    for i,j in val.items():
      if i==C[2].lower():
        cont+=("0"*int(j))
    if C[3].lower() == "d":
      print(f"La resistencia total es de {cont} ohmios con 5% de tolerancia")
    if C[3].lower() == "p":
      print(f"La resistencia total es de {cont} ohmios con 10% de tolerancia")

```

### Para 5 bandas

Este código es una función llamada fi_b(C), que toma un argumento C que representa el código de colores de una resistencia de 5 bandas. El código de colores se descompone en sus valores numéricos utilizando un diccionario llamado val. En la función, se utiliza un loop for para recorrer el diccionario y obtener el valor numérico correspondiente a cada color. Luego, los valores numéricos se concatenan en una cadena cont.

Después, se utiliza una condición if para eliminar cualquier cero inicial en la cadena cont. Entonces, si la última letra del código de colores es una "d", se imprime la resistencia total con una tolerancia del 5%. Si la última letra es una "p", se imprime la resistencia total con una tolerancia del 10%.

En resumen, esta función toma el código de colores de una resistencia de 5 bandas, lo convierte en su valor numérico correspondiente y lo imprime con su tolerancia correspondiente en ohmios.

```Python
  def fi_b(C): #cinco bandas
    cont = ""
    val = {"n":"0", "c":"1", "r":"2", "na":"3", "a":"4", "ve":"5", "az":"6", "v":"7", "g":"8", "b":"9"}
    for i,j in val.items():
      if i == C[0].lower():
        cont+=j
    for i,j in val.items():
      if i == C[1].lower():
        cont+=j
    for i,j in val.items():
      if i == C[2].lower():
        cont+=j
    for i,j in val.items():
      if i==C[3].lower():
        cont+=("0"*int(j))
    if(cont[0]=="0"):
      cont = cont[1:]
    if C[4].lower() == "d":
      print(f"La resistencia total es de {cont} ohmios con 5% de tolerancia")
    if C[3].lower() == "p":
      print(f"La resistencia total es de {cont} ohmios con 10% de tolerancia")

```

### Calculadora de resistencias para 4 o 5 bandas
Este código es una función que permite al usuario calcular la resistencia de una banda de 4 o 5 colores. Primero, el usuario debe ingresar un número (1 o 2) para seleccionar la cantidad de bandas. Si el usuario ingresa un valor que no es un número, se imprimirá un mensaje de error y se le pedirá que ingrese un valor válido. Si el usuario ingresa un número que no es 1 o 2, se imprimirá un mensaje de error y se le pedirá que ingrese un valor válido.

Si el usuario elige 1, se le pedirá que ingrese los colores de las bandas y se verificará si se han ingresado suficientes bandas. Si no se han ingresado suficientes bandas, se imprimirá un mensaje de error y se le pedirá que ingrese los colores de las bandas nuevamente. La función llama a otra función llamada "fo_b" para calcular la resistencia de la banda de 4 colores.

Si el usuario elige 2, se le pedirá que ingrese los colores de las bandas y se verificará si se han ingresado suficientes bandas. Si no se han ingresado suficientes bandas, se imprimirá un mensaje de error y se le pedirá que ingrese los colores de las bandas nuevamente. La función llama a otra función llamada "fi_b" para calcular la resistencia de la banda de 5 colores.

```Python
  try:
      c = int(input())
  except ValueError:
      print("por favor ingrese un dato valido")
      cond = True
      fin = cond
      while(fin == True):
        try:
           c = int(input())
           if(type(c)==int):
            fin=False
        except ValueError:
           print("por favor ingrese un dato valido")
           fin = True
  while(c>2 or c<1):
        print("Por favor ingrese una opcion valida")
        c = int(input())
  if (c==1):
    print("""Los colores posibles a ingresar son
    Negro = N,  Café = C,  Rojo = R, Naranja = NA,
    Amarillo = A,  Verde = Ve,  Azul = AZ,
    Blanco = B,  Gris = G,  Violeta = V

    Y para tolerancias solo es valido Dorado = D,  Plata = P
    """)
    print("Para calcular su resistencia de 4 bandas")
    C = [str(k) for k in input("Por favor ingrese las letras que acompañan a los colores separadas por espacio: ").split()]
    while(len(C)<4):
      print("No ingreso las suficientes bandas, intenta de nuevo")
      C = [str(k) for k in input("Por favor ingrese las letras que acompañan a los colores separadas por espacio: ").split()]
    return fo_b(C)

  if (c==2):
    print("""Los colores posibles a ingresar son
    Negro = N,  Café = C,  Rojo = R, Naranja = NA,
    Amarillo = A,  Verde = Ve,  Azul = AZ,
    Blanco = B,  Gris = G,  Violeta = V

    Y para tolerancias solo es valido Dorado = D,  Plata = P
    """)
    print("Para calcular su resistencia de 5 bandas")
    C = [str(k) for k in input("Por favor ingrese las letras que acompañan a los colores separadas por espacio: ").split()]
    while(len(C)<5):
      print("No ingreso las suficientes bandas, intenta de nuevo")
      C = [str(k) for k in input("Por favor ingrese las letras que acompañan a los colores separadas por espacio: ").split()]
    return fi_b(C)

````

## Calculadora ley de ohm para circuitos de 4 resistencias y fuente de voltaje DC.
En esta calculadora se tienen 4 tipos de circuitos los cuales difieren enla posicion que tengan las resistencias, es decir, que 4 resistencias pueden estar en serie o en paralelo, las primeras dos en paralelo y las otras dos en serie, e iviseversa.

### 4 en paralelo
El código que se te muestra es una función llamada "fo_p" que calcula el voltaje, corriente y resistencia total de un circuito eléctrico en paralelo con cuatro resistencias (R1, R2, R3 y R4) a partir de la fuente de voltaje (V) dada. La función llama a otras dos funciones "cor_p" y "paralelo" para realizar los cálculos.

La función "cor_p" calcula la corriente en una resistencia en paralelo, mientras que la función "paralelo" calcula la resistencia total de un conjunto de resistencias en paralelo.

En cuanto a la salida del código, la función "fo_p" imprime el voltaje total y el voltaje de cada resistencia, la corriente de cada resistencia y la resistencia total del circuito. La función "round" se utiliza para redondear los valores de corriente y resistencia a cinco y dos decimales, respectivamente.

```Python
  def fo_p(V,R1,R2,R3,R4): #4 paralelo
    print(f"El voltaje total es {V} voltios")
    print(f"El voltaje de R1 es {V} voltios")
    print(f"El voltaje de R2 es {V} voltios")
    print(f"El voltaje de R3 es {V} voltios")
    print(f"El voltaje de R4 es {V} voltios")
    print(f"La corriente de R1 es {round(cor_p(V,R1),5)} amperios ")
    print(f"La corriente de R2 es {round(cor_p(V,R2),5)} amperios ")
    print(f"La corriente de R3 es {round(cor_p(V,R3),5)} amperios ")
    print(f"La corriente de R4 es {round(cor_p(V,R4),5)} amperios ")
    print(f"La resistencia total del circuito es {round(paralelo(R1,paralelo(R2,paralelo(R3,R4))),2)} ohmios")
```

### 1 y 2 en serie y 3 y 4 en paralelo
El código es una función que calcula las características eléctricas de un circuito eléctrico compuesto por cuatro resistencias, dos en serie y dos en paralelo. Recibe como argumentos el voltaje de la fuente y los valores de resistencia de cada una de las cuatro resistencias.

La función imprime el voltaje total y la resistencia total del circuito, así como la corriente total del circuito. Luego, calcula el voltaje y la corriente de cada una de las resistencias individuales.

El código utiliza otras dos funciones, "serie" y "paralelo", para calcular la resistencia total del circuito. También utiliza la función "cor_p" para calcular la corriente a través de las resistencias en paralelo.

En resumen, el código es una herramienta útil para calcular las características eléctricas de un circuito específico y puede ser utilizado por personas que trabajan con electrónica o electricidad.

```Python
  def t_s_t_p(V,R1,R2,R3,R4): # 2 serie 2 paralelo
    print(f"El voltaje total es {V} voltios")
    print(f"La resistencia total del circuito es {round(serie(R1,R2)+paralelo(R3,R4),2)} ohmios")
    print(f"La corriente total del circuito es {round(V/(serie(R1,R2)+paralelo(R3,R4)),5)} amperios")
    It = V/(serie(R1,R2)+paralelo(R3,R4))
    print(f"El voltaje de R1 es {round((R1*It),2)} voltios")
    print(f"El voltaje de R2 es {round((R2*It),2)} voltios")
    print(f"El voltaje de R3 es {round((V-(R1*It+R2*It)),2)} voltios")
    print(f"El voltaje de R4 es {round((V-(R1*It+R2*It)),2)} voltios")
    print(f"La corriente de R1 es {round(It,5)} amperios ")
    print(f"La corriente de R2 es {round(It,5)} amperios ")
    print(f"La corriente de R3 es {round((cor_p((V-(R1*It+R2*It)),R3)),5)} amperios ")
    print(f"La corriente de R4 es {round((cor_p((V-(R1*It+R2*It)),R4)),5)} amperios ")

```

### 1 y 2 en paralelo y 3 y 4 en serie
Este código es una función que calcula las características eléctricas de un circuito con 4 resistencias, 2 en paralelo y 2 en serie.

La función toma 5 argumentos: el voltaje total del circuito (V) y las resistencias de las 4 resistencias (R1, R2, R3 y R4).

La función utiliza otras funciones llamadas "paralelo", "serie" y "cor_p" para calcular la resistencia total del circuito, la corriente total y el voltaje y corriente individuales de cada resistencia.

Los resultados se imprimen en pantalla utilizando la función "print", y se redondean a 2 o 5 decimales según corresponda para mayor claridad.

```Python
  def t_p_t_s(V,R1,R2,R3,R4): #2 paralelo 2 serie
    print(f"El voltaje total es {V} voltios")
    print(f"La resistencia total del circuito es {round((paralelo(R1,paralelo(R2,serie(R3,R4)))),2)} ohmios")
    print(f"La corriente total del circuito es {round((V/(paralelo(R1,paralelo(R2,serie(R3,R4))))),5)} amperios")
    It = V/(paralelo(R1,paralelo(R2,serie(R3,R4))))
    print(f"El voltaje de R1 es {V} voltios")
    print(f"El voltaje de R2 es {V} voltios")
    print(f"El voltaje de R3 es {round((R3*(It-(cor_p(V,R1)+cor_p(V,R2)))),2)} voltios")
    print(f"El voltaje de R4 es {round((R4*(It-(cor_p(V,R1)+cor_p(V,R2)))),2)} voltios")
    print(f"La corriente de R1 es {round((cor_p(V,R1)),5)} amperios ")
    print(f"La corriente de R2 es {round((cor_p(V,R2)),5)} amperios ")
    print(f"La corriente de R3 es {round((It-(cor_p(V,R1)+cor_p(V,R2))),5)} amperios ")
    print(f"La corriente de R4 es {round((It-(cor_p(V,R1)+cor_p(V,R2))),5)} amperios ")

```

### Cuatro resistencias en serie
Este código es una función en Python que calcula las características eléctricas de un circuito con cuatro resistencias conectadas en serie. La función toma como entrada el voltaje V y las resistencias R1, R2, R3 y R4. A continuación, utiliza la función "serie", que está definida en algún otro lugar del código, para calcular la resistencia total del circuito. Luego, utiliza la ley de Ohm para calcular la corriente total del circuito, que se utiliza para calcular el voltaje y la corriente en cada una de las resistencias. Finalmente, se imprimen los resultados en la pantalla. Los valores se redondean a dos o cinco decimales para mayor claridad.

```Python
  def fo_s(V,R1,R2,R3,R4): #4 serie
    print(f"El voltaje total es {V} voltios")
    print(f"La resistencia total del circuito es {round((serie(R1,serie(R2,serie(R3,R4)))),2)} ohmios")
    print(f"La corriente total del circuito es {round((V/(serie(R1,serie(R2,serie(R3,R4))))),5)} amperios")
    It=V/serie(R1,serie(R2,serie(R3,R4)))
    print(f"El voltaje de R1 es {round((It*R1),2)} voltios")
    print(f"El voltaje de R2 es {round((It*R2),2)} voltios")
    print(f"El voltaje de R3 es {round((It*R3),2)} voltios")
    print(f"El voltaje de R4 es {round((It*R4),2)} voltios")
    print(f"La corriente de R1 es {round(It,5)} amperios ")
    print(f"La corriente de R2 es {round(It,5)} amperios ")
    print(f"La corriente de R3 es {round(It,5)} amperios ")
    print(f"La corriente de R4 es {round(It,5)} amperios ")

```

### Calculadora de las resistencias
Este código es una función que recopila información sobre un circuito eléctrico y utiliza varias subfunciones para calcular su resistencia total, corriente y voltaje. Primero, el usuario debe elegir una opción (1, 2 o 3), que se almacena en la variable "c", y luego debe ingresar información sobre la fuente de voltaje y cuatro resistencias (cuyos valores se almacenan en las variables "r1", "r2", "r3" y "r4"). Cada vez que el usuario ingresa un valor negativo, se le solicita que lo ingrese nuevamente. Después de recopilar toda la información, la función llama a una subfunción diferente ("fo_p", "t_s_t_p" o "t_p_t_s") dependiendo de la opción elegida por el usuario, que realiza los cálculos necesarios y devuelve un resultado que se imprime en la pantalla.

```Python
  try:
      c = int(input())
  except ValueError:
      print("por favor ingrese un dato valido")
      cond = True
      fin = cond
      while(fin == True):
        try:
           c = int(input())
           if(type(c)==int):
            fin=False
        except ValueError:
           print("por favor ingrese un dato valido")
           fin = True
  while(c>4 or c<1):
        print("Por favor ingrese una opcion valida")
        c = int(input())
  if (c==1):
    print("Por favor ingrese el voltaje de la fuente del circuito")
    v = int(input())
    while(v<0):
      print("Por favor ingrese el voltaje de la fuente del circuito")
      v = int(input())
    print("Por favor ingrese el valor de la resistencia 1")
    r1 = int(input())
    while(r1<0):
      print("Por favor ingrese el valor de la resistencia 1")
      r1 = int(input())
    print("Por favor ingrese el valor de la resistencia 2")
    r2 = int(input())
    while(r2<0):
      print("Por favor ingrese el valor de la resistencia 2")
      r2 = int(input())
    print("Por favor ingrese el valor de la resistencia 3")
    r3 = int(input())
    while(r3<0):
      print("Por favor ingrese el valor de la resistencia 3")
      r3 = int(input())
    print("Por favor ingrese el valor de la resistencia 4")
    r4 = int(input())
    while(r4<0):
      print("Por favor ingrese el valor de la resistencia 4")
      r4 = int(input())
    return fo_p(v,r1,r2,r3,r4)

  if (c==2):
    print("Por favor ingrese el voltaje de la fuente del circuito")
    v = int(input())
    while(v<0):
      print("Por favor ingrese el voltaje de la fuente del circuito")
      v = int(input())
    print("Por favor ingrese el valor de la resistencia 1")
    r1 = int(input())
    while(r1<0):
      print("Por favor ingrese el valor de la resistencia 1")
      r1 = int(input())
    print("Por favor ingrese el valor de la resistencia 2")
    r2 = int(input())
    while(r2<0):
      print("Por favor ingrese el valor de la resistencia 2")
      r2 = int(input())
    print("Por favor ingrese el valor de la resistencia 3")
    r3 = int(input())
    while(r3<0):
      print("Por favor ingrese el valor de la resistencia 3")
      r3 = int(input())
    print("Por favor ingrese el valor de la resistencia 4")
    r4 = int(input())
    while(r4<0):
      print("Por favor ingrese el valor de la resistencia 4")
      r4 = int(input())
    return t_s_t_p(v,r1,r2,r3,r4)

  if (c==3):
    print("Por favor ingrese el voltaje de la fuente del circuito")
    v = int(input())
    while(v<0):
      print("Por favor ingrese el voltaje de la fuente del circuito")
      v = int(input())
    print("Por favor ingrese el valor de la resistencia 1")
    r1 = int(input())
    while(r1<0):
      print("Por favor ingrese el valor de la resistencia 1")
      r1 = int(input())
    print("Por favor ingrese el valor de la resistencia 2")
    r2 = int(input())
    while(r2<0):
      print("Por favor ingrese el valor de la resistencia 2")
      r2 = int(input())
    print("Por favor ingrese el valor de la resistencia 3")
    r3 = int(input())
    while(r3<0):
      print("Por favor ingrese el valor de la resistencia 3")
      r3 = int(input())
    print("Por favor ingrese el valor de la resistencia 4")
    r4 = int(input())
    while(r4<0):
      print("Por favor ingrese el valor de la resistencia 4")
      r4 = int(input())
    return t_p_t_s(v,r1,r2,r3,r4)

  if (c==4):
    print("Por favor ingrese el voltaje de la fuente del circuito")
    v = int(input())
    while(v<0):
      print("Por favor ingrese el voltaje de la fuente del circuito")
      v = int(input())
    print("Por favor ingrese el valor de la resistencia 1")
    r1 = int(input())
    while(r1<0):
      print("Por favor ingrese el valor de la resistencia 1")
      r1 = int(input())
    print("Por favor ingrese el valor de la resistencia 2")
    r2 = int(input())
    while(r2<0):
      print("Por favor ingrese el valor de la resistencia 2")
      r2 = int(input())
    print("Por favor ingrese el valor de la resistencia 3")
    r3 = int(input())
    while(r3<0):
      print("Por favor ingrese el valor de la resistencia 3")
      r3 = int(input())
    print("Por favor ingrese el valor de la resistencia 4")
    r4 = int(input())
    while(r4<0):
      print("Por favor ingrese el valor de la resistencia 4")
      r4 = int(input())
    return fo_s(v,r1,r2,r3,r4)
```

## Calculadora de amplificación en Cascada de transistores BJT.
Una calculadora de amplificación en cascada con transistores BJT programada en Python es una herramienta útil para diseñar y analizar circuitos electrónicos que utilizan transistores bipolares de unión (BJT) en configuración de cascada. El programa permite al usuario ingresar los valores de las resistencias, capacitores y voltajes de entrada y salida del circuito, y calcula automáticamente los valores de ganancia de voltaje, ganancia de corriente, impedancia de entrada, impedancia de salida y otros parámetros importantes del circuito.

El programa se basa en las ecuaciones matemáticas que describen el comportamiento de los transistores BJT en configuración de cascada, y utiliza técnicas de programación orientada a objetos para organizar el código en módulos y clases que facilitan la lectura y el mantenimiento del código.

### Fase I Polarizacion Universal Fase II Polarizacion Universal.
El código es una función que realiza el análisis y cálculo de un amplificador en cascada con transistores BJT. La función recibe como entrada valores de voltajes, resistencias y beta para dos etapas del amplificador. En la primera etapa, se realiza la polarización del transistor y se calculan las corrientes de base, emisor y colector, así como el voltaje de colector-emisor y los voltajes de las resistencias de colector y emisor. En la segunda etapa se realiza el análisis AC del circuito y se calcula la amplificación total del sistema, así como el voltaje resultante de la amplificación total y parcial de la señal de entrada. El código es útil para estudiantes y profesionales interesados en el diseño y análisis de circuitos electrónicos con transistores BJT en cascada.

```Python
  def po_un_2(vin,vcc,r1,r2,rc,RE,beta,vcc2,r12,r22,rc2,RE2,beta2): #polarizacion universal polarizacion universal
     #polarizacion fase I
    vth = vcc*(r2/(r1+r2))
    rth = ((r1*r2)/(r1+r2))
    Ib = (vth-0.7)/(rth+RE*(beta+1))
    Ie = (beta+1)*Ib
    Ic = beta*Ib
    Vce = vcc - Ic*(rc+RE)
    #polarizacion fase II
    vth2 = vcc2*(r22/(r12+r22))
    rth2 = ((r12*r22)/(r12+r22))
    Ib2 = (vth2-0.7)/(rth2+RE2*(beta2+1))
    Ie2 = (beta2+1)*Ib2
    Ic2 = beta2*Ib2
    Vce2 = vcc2 - Ic2*(rc2+RE2)

    #Analisis AC1
    re = 0.026/Ie
    AVnl1 = -rc/re
    Zi2 = (rth2*RE2)/(rth2+RE2)
    Av1 = ((Zi2)/(Zi2+rc))*AVnl1
    #Analisis AC2
    re2= 0.026/Ie2
    AVnl2 = -rc2/re2
    Av2 = ((1000)/(1000+rc2))*AVnl2
    #Analisis total AC
    Avt = Av1*Av2
    Voutp = vin*Av1
    Vout = vin*Avt

    #polarizacion fase I
    print(f"\nLa corriente de base es {round(Ib,5)} amperios")
    print(f"La corriente de emisor es {round(Ie,4)} amperios ")
    print(f"La corriente de colector es {round(Ic,4)} amperios")
    print(f"El voltaje de colector emisor es {round(Vce,4)} Voltios")
    print(f"La voltaje de Resistencia de colector es {round((Ic*rc),4)} Voltios")
    print(f"La voltaje de Resistencia de emisor es {round((Ie*RE),4)} Voltios")
    #polarizacion fase II
    print(f"\nLa corriente de base es {round(Ib2,5)} amperios")
    print(f"La corriente de emisor es {round(Ie2,4)} amperios ")
    print(f"La corriente de colector es {round(Ic2,4)} amperios")
    print(f"El voltaje de colector emisor es {round(Vce2,4)} Voltios")
    print(f"La voltaje de Resistencia de colector es {round((Ic2*rc2),4)} Voltios")
    print(f"La voltaje de Resistencia de emisor es {round((Ie2*RE2),4)} Voltios")
    #Amplificacion de señal
    print(f"\nLa amplificacion total del sistema es de {round(Avt,5)}")
    print(f"El voltaje resultante de la amplificacion de la señal de entrada es {round(Vout,5)} V")
    print(f"El voltaje resultante de la amplificacion parcial de la señal de entrada es {round(Voutp,5)} V")
```

### Fase I Polarizacion Universal Fase II Emisor comun con resistencia de emisor.

El código es una función que calcula las características de una polarización universal de un circuito amplificador compuesto por dos etapas de un transistor BJT en cascada. La función toma los valores de resistencia, voltaje y factor beta de cada etapa y realiza una serie de cálculos para obtener la corriente, voltaje y amplificación total del circuito.

La función también realiza un análisis AC del circuito, que incluye el cálculo de la ganancia de voltaje, la impedancia de entrada y la ganancia de voltaje total del sistema. Finalmente, la función muestra los resultados de la polarización de cada etapa y la amplificación de la señal de entrada.

```Python
  def po_un_ecre(vcc,r1,r2,rc,RE,beta,vcc2,rb2,rc2,RE2,beta2): #polarizacion universal polarizacoin emisor comun resistencia emisor
    vth = vcc*(r2/(r1+r2))
    rth = ((r1*r2)/(r1+r2))
    Ib = (vth-0.7)/(rth+RE*(beta+1))
    Ie = (beta+1)*Ib
    Ic = beta*Ib
    Vce = vcc - Ic*(rc+RE)

    Ib2 = (vcc2-0.7)/(rb2+RE2*(beta2+1))
    Ie2 = (beta2+1)*Ib2
    Ic2 = beta2*Ib2
    Vce2 = vcc2 - Ic2*(rc2+RE2)

    #Analisis AC1
    re = 0.026/Ie
    AVnl1 = -rc/re
    Zi2 = (rb2*RE2)/(rb2+RE2)
    Av1 = ((Zi2)/(Zi2+rc))*AVnl1
    #Analisis AC2
    re2 = 0.026/Ie2
    AVnl2 = -rc2/re2
    Av2 = ((1000)/(1000+rc2))*AVnl2
    #Analisis total AC
    Avt = Av1*Av2
    Voutp = vin*Av1
    Vout = vin*Avt

    #polarizacion fase I
    print(f"\nLa corriente de base es {round(Ib,5)} amperios")
    print(f"La corriente de emisor es {round(Ie,4)} amperios ")
    print(f"La corriente de colector es {round(Ic,4)} amperios")
    print(f"El voltaje de colector emisor es {round(Vce,4)} Voltios")
    print(f"La voltaje de Resistencia de colector es {round((Ic*rc),4)} Voltios")
    print(f"La voltaje de Resistencia de emisor es {round((Ie*RE),4)} Voltios")
    #polarizacion fase II
    print(f"\nLa corriente de base es {round(Ib2,5)} amperios")
    print(f"La corriente de emisor es {round(Ie2,4)} amperios ")
    print(f"La corriente de colector es {round(Ic2,4)} amperios")
    print(f"El voltaje de colector emisor es {round(Vce2,4)} Voltios")
    print(f"La voltaje de Resistencia de colector es {round((Ic2*rc2),4)} Voltios")
    print(f"La voltaje de Resistencia de emisor es {round((Ie2*RE2),4)} Voltios")
    print(f"La voltaje de Resistencia de base es {round((Ib2*rb2),4)} Voltios")
    #Amplificacion de señal
    print(f"\nLa amplificacion total del sistema es de {round(Avt,5)}")
    print(f"El voltaje resultante de la amplificacion de la señal de entrada es {round(Vout,5)} V")
    print(f"El voltaje resultante de la amplificacion parcial de la señal de entrada es {round(Voutp,5)} V")
````

### Fase I Polarización Universal Fase II Emisor común.

El código es una función llamada "po_un_ec" que calcula los parámetros de un circuito amplificador en cascada basado en transistores BJT. Los parámetros de entrada son la fuente de alimentación Vcc, las resistencias R1, R2, RC, y RE, el parámetro beta del transistor, otra fuente de alimentación Vcc2, las resistencias RB2 y RC2, y el parámetro beta2 del segundo transistor.

La función primero realiza la polarización del circuito, calculando las corrientes de base, emisor y colector, así como el voltaje de colector-emisor y las tensiones a través de las resistencias de colector y emisor. Luego, realiza un análisis AC del circuito, calculando la amplificación de voltaje en cada etapa y la amplificación total. También calcula el voltaje de salida de la señal de entrada para cada etapa y la señal de salida total.

Finalmente, la función imprime los resultados de la polarización de cada etapa y la amplificación total del circuito, así como los voltajes resultantes de la amplificación de la señal de entrada en cada etapa y la señal de salida total.

```Python
  def po_un_ec(vcc,r1,r2,rc,RE,beta,vcc2,rb2,rc2,beta2): #polarizacion universal emisor comun
    vth = vcc*(r2/(r1+r2))
    rth = ((r1*r2)/(r1+r2))
    Ib = (vth-0.7)/(rth+RE*(beta+1))
    Ie = (beta+1)*Ib
    Ic = beta*Ib
    Vce = vcc - Ic*(rc+RE)

    Ib2 = (vcc2-0.7)/(rb2)
    Ie2 = (beta2+1)*Ib2
    Ic2 = beta2*Ib2
    Vce2 = vcc2 - Ic2*(rc2)

    #Analisis AC1
    re = 0.026/Ie
    AVnl1 = -rc/re
    Zi2 = (rb2*(beta*re))/(rb2+(beta*re))
    Av1 = ((Zi2)/(Zi2+rc))*AVnl1
    #Analisis AC2
    re2 = 0.026/Ie2
    AVnl2 = -rc2/re2
    Av2 = ((1000)/(1000+rc2))*AVnl2
    #Analisis total AC
    Avt = Av1*Av2
    Voutp = vin*Av1
    Vout = vin*Avt

    #polarizacion fase I
    print(f"\nLa corriente de base es {round(Ib,5)} amperios")
    print(f"La corriente de emisor es {round(Ie,4)} amperios ")
    print(f"La corriente de colector es {round(Ic,4)} amperios")
    print(f"El voltaje de colector emisor es {round(Vce,4)} Voltios")
    print(f"La voltaje de Resistencia de colector es {round((Ic*rc),4)} Voltios")
    print(f"La voltaje de Resistencia de emisor es {round((Ie*RE),4)} Voltios")
    #polarizacion fase II
    print(f"\nLa corriente de base es {round(Ib2,5)} amperios")
    print(f"La corriente de emisor es {round(Ie2,4)} amperios ")
    print(f"La corriente de colector es {round(Ic2,4)} amperios")
    print(f"El voltaje de colector emisor es {round(Vce2,4)} Voltios")
    print(f"La voltaje de Resistencia de colector es {round((Ic2*rc2),4)} Voltios")
    print(f"La voltaje de Resistencia de base es {round((Ib2*rb2),4)} Voltios")
    #Amplificacion de señal
    print(f"\nLa amplificacion total del sistema es de {round(Avt,5)}")
    print(f"El voltaje resultante de la amplificacion de la señal de entrada es {round(Vout,5)} V")
    print(f"El voltaje resultante de la amplificacion parcial de la señal de entrada es {round(Voutp,5)} V")
```

### Calculadora de amplificación
El código que consta de una función llamada "po_un_2" para realizar cálculos en un amplificador en cascada con transistores BJT. Esta función requiere varios parámetros de entrada para llevar a cabo los cálculos. Antes de ingresar los parámetros, se realiza una verificación para asegurarse de que el usuario ingrese una opción válida para la función. En caso de que el usuario proporcione un valor inválido, se le solicita que ingrese un valor válido hasta que lo haga.

Una vez que se han ingresado los parámetros válidos, se procede a solicitar los valores necesarios para realizar los cálculos. Si el usuario ingresa un valor negativo o cero para alguno de los parámetros, se le pide que ingrese un valor válido hasta que lo haga.

Una vez que se han ingresado todos los valores de los parámetros, la función "po_un_2" realiza los cálculos necesarios y devuelve un resultado. Parece que este código es una extensión de un programa previo que calcula la configuración de un amplificador en cascada utilizando transistores BJT.

La sección de código proporcionada parece encargarse de la entrada del usuario y los valores necesarios para calcular la ganancia de voltaje, la impedancia de entrada y la ganancia total de la configuración del amplificador. Se utiliza un bucle while para asegurar que los valores ingresados por el usuario sean válidos. Si el usuario proporciona un valor negativo o cero, el programa solicita al usuario que ingrese un valor válido. Una vez que se ingresan los valores válidos, se devuelve la salida del programa mediante una llamada a la función "po_un_ecre", que posiblemente realice los cálculos necesarios para determinar la ganancia de voltaje, la impedancia de entrada y la ganancia total del amplificador.

```Python
  try:
      c = int(input())
  except ValueError:
      print("por favor ingrese un dato valido")
      cond = True
      fin = cond
      while(fin == True):
        try:
           c = int(input())
           if(type(c)==int):
            fin=False
        except ValueError:
           print("por favor ingrese un dato valido")
           fin = True
  while(c>3 or c<1):
        print("Por favor ingrese una opcion valida")
        c = int(input())
  if (c==1):
    print("Por favor ingrese los siguientes datos")
    vin = float(input("Ingrese el valor del Voltaje de entrada:   "))
    while(vin<0 or vin==0):
      vin = float(input("Ingrese el valor del Voltaje de entrada a 0:   "))
    vcc = float(input("Ingrese el valor del Voltaje de colector comun:   "))
    while(vcc<0 or vcc==0):
      vcc = float(input("Ingrese el valor del Voltaje de colector comun mayor a 0:   "))
    r1 = float(input("Ingrese el valor de la resistencia r1 en ohmios:   "))
    while(r1<0):
      r1 = float(input("Ingrese el valor de la resistencia r1 en ohmios:   "))
    r2 = float(input("Ingrese el valor de la resistencia r2 en ohmios:   "))
    while(r2<0):
      r2 = float(input("Ingrese el valor de la resistencia r2 en ohmios:   "))
    rc = float(input("Ingrese el valor de la resistencia rc en ohmios:   "))
    while(rc<0):
      rc = float(input("Ingrese el valor de la resistencia rc en ohmios:   "))
    RE = float(input("Ingrese el valor de la resistencia RE en ohmios:   "))
    while(RE<0):
      RE = float(input("Ingrese el valor de la resistencia RE en ohmios:   "))
    beta = int(input("Ingrese un numero mayor o igual a 50 y menor o igual a 500:  "))
    while(beta<50 or beta>500):
      beta = int(input("Ingrese un numero mayor o igual a 50 y menor o igual a 500:  "))

    vcc2 = float(input("Ingrese el valor del Voltaje de colector comun:   "))
    while(vcc2<0 or vcc2==0):
        vcc2 = float(input("Ingrese el valor del Voltaje de colector comun mayor a 0:   "))
    r12 = float(input("Ingrese el valor de la resistencia r1 en ohmios:   "))
    while(r12<0):
      r12 = float(input("Ingrese el valor de la resistencia r1 en ohmios:   "))
    r22 = float(input("Ingrese el valor de la resistencia r2 en ohmios:   "))
    while(r22<0):
      r22 = float(input("Ingrese el valor de la resistencia r2 en ohmios:   "))
    rc2 = float(input("Ingrese el valor de la resistencia rc en ohmios:   "))
    while(rc2<0):
      rc2 = float(input("Ingrese el valor de la resistencia rc en ohmios:   "))
    RE2 = float(input("Ingrese el valor de la resistencia RE en ohmios:   "))
    while(RE2<0):
      RE2 = float(input("Ingrese el valor de la resistencia RE en ohmios:   "))
    beta2 = int(input("Ingrese un numero mayor o igual a 50 y menor o igual a 500:  "))
    while(beta2<50 or beta2>500):
      beta2 = int(input("Ingrese un numero mayor o igual a 50 y menor o igual a 500:  "))
    return po_un_2(vin,vcc,r1,r2,rc,RE,beta,vcc2,r12,r22,rc2,RE2,beta2)


  if (c==2):
    print("Por favor ingrese los siguientes datos")
    vin = float(input("Ingrese el valor del Voltaje de entrada:   "))
    while(vin<0 or vin==0):
      vin = float(input("Ingrese el valor del Voltaje de entrada a 0:   "))
    vcc = float(input("Ingrese el valor del Voltaje de colector comun:   "))
    while(vcc<0 or vcc==0):
      vcc = float(input("Ingrese el valor del Voltaje de colector comun mayor a 0:   "))
    r1 = float(input("Ingrese el valor de la resistencia r1 en ohmios:   "))
    while(r1<0):
      r1 = float(input("Ingrese el valor de la resistencia r1 en ohmios:   "))
    r2 = float(input("Ingrese el valor de la resistencia r2 en ohmios:   "))
    while(r2<0):
      r2 = float(input("Ingrese el valor de la resistencia r2 en ohmios:   "))
    rc = float(input("Ingrese el valor de la resistencia rc en ohmios:   "))
    while(rc<0):
      rc = float(input("Ingrese el valor de la resistencia rc en ohmios:   "))
    RE = float(input("Ingrese el valor de la resistencia RE en ohmios:   "))
    while(RE<0):
      RE = float(input("Ingrese el valor de la resistencia RE en ohmios:   "))
    beta = int(input("Ingrese un numero mayor o igual a 50 y menor o igual a 500:  "))
    while(beta<50 or beta>500):
      beta = int(input("Ingrese un numero mayor o igual a 50 y menor o igual a 500:  "))
    vcc2 = float(input("Ingrese el valor del Voltaje de colector comun:   "))
    while(vcc2<0 or vcc2==0):
      vcc2 = float(input("Ingrese el valor del voltaje de colector comun mayor a 0:   "))
    rb2 = float(input("Ingrese el valor de la resistencia rb en ohmios:   "))
    while(rb2<0):
      rb2 = float(input("Ingrese el valor de la resistencia rc en ohmios:   "))
    rc2 = float(input("Ingrese el valor de la resistencia rc en ohmios:   "))
    while(rc2<0):
      rc2 = float(input("Ingrese el valor de la resistencia rc en ohmios:   "))
    RE2 = float(input("Ingrese el valor de la resistencia RE en ohmios:   "))
    while(RE2<0):
      RE2 = float(input("Ingrese el valor de la resistencia RE en ohmios:   "))
    beta2 = int(input("Ingrese un numero mayor o igual a 50 y menor o igual a 500:  "))
    while(beta2<50 or beta2>500):
      beta2 = int(input("Ingrese un numero mayor o igual a 50 y menor o igual a 500:  "))
    return po_un_ecre(vcc,r1,r2,rc,RE,beta,vcc2,rb2,rc2,RE2,beta2)


  if (c==3):
    print("Por favor ingrese los siguientes datos")
    vin = float(input("Ingrese el valor del Voltaje de entrada:   "))
    while(vin<0 or vin==0):
      vin = float(input("Ingrese el valor del Voltaje de entrada a 0:   "))
    vcc = float(input("Ingrese el valor del Voltaje de colector comun:   "))
    while(vcc<0 or vcc==0):
      vcc = float(input("Ingrese el valor del Voltaje de colector comun mayor a 0:   "))
    r1 = float(input("Ingrese el valor de la resistencia r1 en ohmios:   "))
    while(r1<0):
      r1 = float(input("Ingrese el valor de la resistencia r1 en ohmios:   "))
    r2 = float(input("Ingrese el valor de la resistencia r2 en ohmios:   "))
    while(r2<0):
      r2 = float(input("Ingrese el valor de la resistencia r2 en ohmios:   "))
    rc = float(input("Ingrese el valor de la resistencia rc en ohmios:   "))
    while(rc<0):
      rc = float(input("Ingrese el valor de la resistencia rc en ohmios:   "))
    RE = float(input("Ingrese el valor de la resistencia RE en ohmios:   "))
    while(RE<0):
      RE = float(input("Ingrese el valor de la resistencia RE en ohmios:   "))
    beta = int(input("Ingrese un numero mayor o igual a 50 y menor o igual a 500:  "))
    while(beta<50 or beta>500):
      beta = int(input("Ingrese un numero mayor o igual a 50 y menor o igual a 500:  "))

    vcc2 = float(input("Ingrese el valor del Voltaje de colector comun:   "))
    while(vcc2<0 or vcc2==0):
      vcc2 = float(input("Ingrese el valor del voltaje de colector comun mayor a 0:   "))
    rb2 = float(input("Ingrese el valor de la resistencia rb en ohmios:   "))
    while(rb2<0):
      rb2 = float(input("Ingrese el valor de la resistencia rc en ohmios:   "))
    rc2 = float(input("Ingrese el valor de la resistencia rc en ohmios:   "))
    while(rc2<0):
      rc2 = float(input("Ingrese el valor de la resistencia rc en ohmios:   "))
    beta2 = int(input("Ingrese un numero mayor o igual a 50 y menor o igual a 500:  "))
    while(beta2<50 or beta2>500):
      beta2 = int(input("Ingrese un numero mayor o igual a 50 y menor o igual a 500:  "))
    return po_un_ec(vcc,r1,r2,rc,RE,beta,vcc2,rb2,rc2,beta2)
```

## Calculadora de resistencias equivalentes
Una calculadora de resistencias es una herramienta que permite convertir un valor de resistencia equivalente a otro. Esto se logra ingresando el valor de resistencia original y seleccionando el tipo de conversión que se desea realizar, ya sea por el código de colores de las bandas de la resistencia, por la notación científica, o por el valor numérico de la resistencia. La calculadora muestra entonces el valor de resistencia equivalente y puede incluso mostrar un diagrama con las bandas de colores correspondientes a la nueva resistencia. Este tipo de calculadora es muy útil para diseñar y analizar circuitos electrónicos, ya que permite seleccionar las resistencias adecuadas para cada etapa del circuito y asegurar un funcionamiento óptimo del mismo.

### Valores disponibles por cada función
El código proporciona seis funciones para convertir valores de resistencia entre diferentes unidades. La función k_o(r) convierte una resistencia en kiloohmios (kΩ) a ohmios (Ω), la función M_o(r) convierte una resistencia en megaohmios (MΩ) a ohmios, la función m_o(r) convierte una resistencia en miliohmios (mΩ) a ohmios, la función o_k(r) convierte una resistencia en ohmios a kiloohmios y la función o_M(r) convierte una resistencia en ohmios a megaohmios. Por último, la función o_m(r) convierte una resistencia en ohmios a miliohmios. Cada función utiliza una fórmula matemática para realizar la conversión y muestra el resultado en un mensaje de texto.

```Python
  def k_o(r):
    convr = r*1000
    print(f"La resistencia ingresada es de {r} kiloohmios y su equivalente en ohmios es {convr} ohmios")

  def M_o(r):
    convr = r*1000000
    print(f"La resistencia ingresada es de {r} megaohmios y su equivalente en ohmios es {convr} ohmios")

  def m_o(r):
    convr = r/1000
    print(f"La resistencia ingresada es de {r} miliohmios y su equivalente en ohmios es {convr} ohmios")

  def o_k(r):
    convr = r/1000
    print(f"La resistencia ingresada es de {r} ohmios y su equivalente en kiloohmios es {convr} kiloohmios")

  def o_M(r):
    convr = r/1000000
    print(f"La resistencia ingresada es de {r} ohmios y su equivalente en megaohmios es {convr} megaohmios")

  def o_m(r):
    convr = r*1000
    print(f"La resistencia ingresada es de {r} ohmios y su equivalente en miliohmios es {convr} miliohmios")
```

### Calculadora de equivalencia

Este código es una función que convierte valores de resistencia entre diferentes unidades: ohms, kiloohms, megaohms y miliohmios. La función comienza pidiendo al usuario que ingrese un número entero entre 1 y 6 para seleccionar la unidad de resistencia que desea convertir. Si el usuario ingresa un valor que no es un número entero, se le pedirá que ingrese un dato válido. Si el usuario ingresa un número que no está en el rango de 1 a 6, se le pedirá que ingrese una opción válida. Luego, se le pide al usuario que ingrese el valor de la resistencia que desea convertir y se verifica que sea un número positivo. Dependiendo de la opción seleccionada por el usuario, se llama a una de las funciones de conversión correspondientes y se devuelve el valor convertido.

```Python
  try:
      c = int(input())
  except ValueError:
      print("por favor ingrese un dato valido")
      cond = True
      fin = cond
      while(fin == True):
        try:
           c = int(input())
           if(type(c)==int):
            fin=False
        except ValueError:
           print("por favor ingrese un dato valido")
           fin = True
  while(c>6 or c<1):
        print("Por favor ingrese una opcion valida")
        c = int(input())
  if (c==1):
    print("Por favor ingrese solamente el valor numerico de una resistencia en kiloohmios, ejemplo: 1, 2, 3...")
    r = float(input())
    while(r<0):
      print("Por favor ingrese solamente el valor numerico de una resistencia en kiloohmios, ejemplo: 1, 2, 3...")
      r = float(input())
    return k_o(r)

  if (c==2):
    print("Por favor ingrese solamente el valor numerico de una resistencia en megaohmios, ejemplo: 1, 2, 3...")
    r = float(input())
    while(r<0):
      print("Por favor ingrese solamente el valor numerico de una resistencia en megaohmios, ejemplo: 1, 2, 3...")
      r = float(input())
    return M_o(r)

  if (c==3):
    print("Por favor ingrese solamente el valor numerico de una resistencia en miliohmios, ejemplo: 1, 2, 3...")
    r = float(input())
    while(r<0):
      print("Por favor ingrese solamente el valor numerico de una resistencia en miliohmios, ejemplo: 1, 2, 3...")
      r = float(input())
    return m_o(r)

  if (c==4):
    print("Por favor ingrese solamente el valor numerico de una resistencia en ohmios, ejemplo: 1, 2, 3...")
    r = float(input())
    while(r<0):
      print("Por favor ingrese solamente el valor numerico de una resistencia en ohmios, ejemplo: 1, 2, 3...")
      r = float(input())
    return o_k(r)

  if (c==5):
    print("Por favor ingrese solamente el valor numerico de una resistencia en ohmios, ejemplo:1 , 2, 3...")
    r = float(input())
    while(r<0):
      print("Por favor ingrese solamente el valor numerico de una resistencia en ohmios, ejemplo:1 , 2, 3...")
      r = float(input())
    return o_M(r)

  if (c==6):
    print("Por favor ingrese solamente el valor numerico de una resistencia en ohmios, ejemplo: 1, 2, 3...")
    r = float(input())
    while(r<0):
      print("Por favor ingrese solamente el valor numerico de una resistencia en ohmios, ejemplo: 1, 2, 3...")
      r = float(input())
    return o_m(r)
```

## Calculadora de resistencia en un sistema

Esta calculadora permitiría al usuario introducir valores de resistencia y voltaje, y calcular la corriente que fluye a través del circuito. También permitiría al usuario trazar una gráfica del voltaje con respecto a la corriente para visualizar mejor la relación entre estas dos variables. Al utilizar Python como lenguaje de programación, el usuario podría aprovechar todas las funcionalidades que ofrece este lenguaje para llevar a cabo cálculos complejos y visualizaciones de datos en tiempo real.

### Funcionamiento

Este es un código de una función llamada seleccion() que muestra un menú de opciones al usuario para seleccionar una herramienta. El usuario ingresa un número correspondiente a la herramienta que desea utilizar. La función luego procesa la entrada del usuario y redirige al usuario a la herramienta correspondiente según el número ingresado.

La función también contiene bloques try y except para manejar excepciones en caso de que el usuario ingrese una entrada no válida. Si el usuario ingresa un número que no está dentro del rango de opciones, la función le pedirá al usuario que ingrese una opción válida.

Las herramientas disponibles son: polarización, bandas, ley de Ohm, amplificadores BJT, resistencias equivalentes y un programa de gráficos resistencia-corriente.

En general, esta función se utiliza para brindar opciones a los usuarios y guiarlos a través del proceso de selección de una herramienta específica en función de sus necesidades.

```Python

def seleccion():#funcion de seleccion de utilidades generales
  print("Por favor ingrese el numero de la herramienta que desea utilizar")
  try:
      s = int(input())
  except ValueError:
      print("por favor ingrese un dato valido")
      cond = True
      fin = cond
      while(fin == True):
        try:
           s = int(input())
           if(type(s)==int):
            fin=False
        except ValueError:
           print("por favor ingrese un dato valido")
           fin = True
  while(s>6 or s<1):
        print("Por favor ingrese una opcion valida")
        s = int(input())
  if (s==1):
    return polarizacion()
  if (s==2):
    return bandas()
  if (s==3):
    return C_ley_de_ohm_r_VDC()
  if (s==4):
    return C_amp_en_Cda_BJT()
  if (s==5):
    return C_r_eq()
  if (s==6):
    print("Por favor ingrese dos coordenadas de voltaje, tenga en cuenta que deben ser positivas")
    v = [float(x) for x in input().split()]
    while(len(v)>2 or len(v)<2):
      print("Por favor ingrese dos coordenadas de voltaje, tenga en cuenta que deben ser positivas")
      v = [float(x) for x in input().split()]
    print("Por favor ingrese dos coordenadas de corriente, tenga en cuenta que deben ser positivas")
    c = [float(y) for y in input().split()]
    while(len(c)>2 or len(c)<2):
      print("Por favor ingrese dos coordenadas de voltaje, tenga en cuenta que deben ser positivas")
      c = [float(y) for y in input().split()]
    return C_r_s(c,v)
```
## Finalización del programa
Para finalizar, esta parte del codigo que muestra un menú de opciones y le pregunta al usuario qué opción desea seleccionar. Después de que el usuario selecciona una opción, el programa realiza una acción y le pregunta al usuario si desea utilizar el programa de nuevo.
La función main() llama a las funciones menu() y seleccion() que se encargan de mostrar el menú y permitir que el usuario seleccione una opción.
La línea main() llama a la función main() para iniciar el programa.
Después de que el programa se ejecuta, le pregunta al usuario si desea utilizar el programa nuevamente utilizando un bucle while para permitir que el usuario utilice el programa varias veces si lo desea.
Finalmente, el programa muestra un mensaje de agradecimiento al usuario por utilizar el programa.

```Python
def main():
  menu()
  seleccion()
main()
print("Desea utilizar otra el programa? S o N")
des = input()
while(des.lower()=="s" or des.lower()=="si"):
  main()
  print("Desea utilizar otra el programa? S o N")
  des = input()
print("Gracias por utilizar este programa")
```
