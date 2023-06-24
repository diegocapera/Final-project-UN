# Final-project-UN
## Calculadora de circuitos y resistencias de diferentes tipos
En el siguiente repositorio explicaremos a detalle cada funcion de dicha calculadora para un mayor entendimiento y proposito ya que sus funciones son muy especifícas.
Comenzando por su estructura este programa utiliza el lenguaje Python para su desarrollo y funcionamiento, complementado con las librerias conocidas como Matplolib, la cual su funcionamiento en el programa es para la graficacion entre corriente y voltaje para la calculadora de resistencia en un sistema.
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
## 
