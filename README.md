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

#### datos de entrada
FUNCIONALIDAD 1: Voltajes, resistencia, valor del beta del transistor.

FUNCIONALIDAD 2: Colores del código de colores de las resistencias.

FUNCIONALIDAD 3: Voltaje y valores de 4 resistencias.

FUNCIONALIDAD 4: Voltajes, resistencia, valor del beta del transistor, voltaje de entrada para amplificación

FUNCIONALIDAD 5: Valores numéricos de Resistencias

FUNCIONALIDAD 6: Voltajes, y corrientes.

Especificación: Todos los datos se deben ingresar en unidades del sistema internacional, es decir, en Voltios, Ohmios, Amperios etc.

#### datos de salinda
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

##


    
