# Taller-2

# Punto 1 

Desarrollar un programa que ingrese un número entero n y separe todos los digitos que componen el número.

1. Para solucionar este punto se  pide ingresar un numero entero, y se crea una lista vacia en la cual se almacenaran los digitos que compongan el numero
2. Para poder desglosar el numero se crea un bucle for en el cual se recorre el numero n ingresado.
3. Al separar los digitos se agregan en la lista vacia y se imprimira la lista con los digitos.

Codigo : 

       n = int(input("Ingrese un número entero: ")) # Ingreso del número entero 

       lista = [] # Creación de una lista vacia en donde se guardarán los dígitos que componen el número

       for i in str(n):  
           lista.append(i) # Separando los dígitos y agregandolos al final en la lista 
 
       print("Los dígitos que componen al número son: "+str(lista)) # Impresión del resultado
       
       
# Punto 2 

Desarrollar un programa que ingrese un número flotante n y separe su parte entera de la parte decimal, y luego entrege los digitos tanto de la parte entera como de la decimal.

1. Para el desarrolo de este punto se define una función llamada "digitosNumero" que recibe un parámetro "n" , que es el número real que se desea descomponer en sus dígitos.
2. Se crean dos listas vacías  "listaEntera" y "listaDecimal", que se utilizarán para almacenar los dígitos de la parte entera y decimal del número real "n".
3.  Se inicia  "bandera" en "True" para indicar que se está en la parte entera del número.
4. Se imprimen dos mensajes para mostrar como se divide el numero .
       5. Se crea un bucle "for", se verifica si la variable "bandera" es verdadera y si el carácter que se esta recorriendo en el bucle no es un punto decimal. Si ambas condiciones se cumplen, el carácter se agrega a la lista "listaEntera" utilizando la función "append()".

5. Si el carácter actual en el bucle es un punto decimal, la variable "bandera" se establece en "False" para indicar que se está en la parte decimal del número.

6. Si la variable "bandera" es falsa,  los dígitos se agregan a la lista "listaDecimal" utilizando la función "append()".

7. See imprimen las dos listas "listaEntera" y "listaDecimal" en líneas separadas para mostrar los dígitos de la parte entera y decimal del número, respectivamente.

8.  Se solicita ingresar un número real y se llama a la función "digitosNumero" para descomponer el número y mostrar sus dígitos.

        def digitosNumero(n:float):
        # Función que separa los dígitos de un número n recibido como parámetro, en su parte entera y su parte decimal

        listaEntera = [] # Creación de una lista vacia donde se guardarán los dígitos de la parte entera del número
        listaDecimal = [] # Creación de una lista vacia donde se guardarán los dígitos de la parte decimal del número
        bandera = True

        print("Los dígitos que componen al número son:") 
        print("PARTE ENTERA")

        for i in str(n):  
            if bandera and i != ".":
            listaEntera.append(i) # Separando los dígitos de la parte entera y agragandolos en el filan de la lista correspondiente 
            elif i == ".":
                bandera = False # Validando si nos encontramos en la parte decimal del número, en caso de serlo, obviar el punto
                continue
        
            if bandera == False:
                listaDecimal.append(i) # Separando los dígitos de la parte decimal y agregandolos en el final de la lista correspondiente
    
        print(listaEntera) # Impresión de los dígitos de la parte entera
        print("PARTE DECIMAL") 
        print(listaDecimal) # Impresión de los dígitos de la parte decimal 

         if __name__ == "__main__":
          n = float(input("Ingrese un número real: ")) # Ingreso del número entero
          digitosNumero(n) # Llamado de la función digitosNumero y envío del parámetro n 

# Punto 3 
Desarrollar un programa que permita ingresar dos números enteros y determinar si se tratan de números espejos.

#### Código:
    if __name__ == "__main__":

    n1 = int(input("Ingrese el primer número entero: ")) # Ingreso del primer número
    n2 = int(input("Ingrese el segundo número entero: ")) # Ingreso del segundo número 
    
    lista1 = [] # Creación de la primera lista en donde guardaremos los dígitos del primer número al final de la lista  
    lista2 = [] # Creación de la segunda lista en donde guardaremos los datos del segundo número al principio de la lista 

    for i in str(n1):
        lista1.append(i) # Adición de los dígitos del primer número al final en la lista
    for i in str(n2): 
        lista2.insert(0,i)  # Adición de los dígitos del segundo número al principio en la lista 

    if lista1 == lista2: # Validación de la igualdad de las 2 listas, en caso de ser iguales los números se considerarán como espejo y en caso de no serlo no se considerarán como espejo
        print("Los números son espejo")
    else:
        print("Los números no son espejo")
# Punto 4
Diseñar una función que permita calcular una aproximación de la función coseno alrededor de 0 para cualquier valor x (real), utilizando los primeros n términos de la serie de Taylor. nota: use math para traer la función coseno y mostrar la diferencia entre el valor real y la aproximación. Con cuántos valores de la serie, se tienen errores del 10%, 1%, 0.1% y 0.001%.
#### Código:
    import math
    def aproximacion_coseno (x:float) -> float:
        sumatoria = 0
        for i in range (0, n):
            sumatoria += math.pow(-1, i) * (math.pow(x, 2*i)/ math.factorial(2*i))
        return sumatoria

    if __name__ == "__main__":
      n = (int(input("Número de términos de la serie de Maclaurin: ")))
      x = (float(input("Valor real para calcular la aproximación de la función coseno alrededor de 0: ")))
      sumatoria = aproximacion_coseno (x, n)
  
    print("Resultado usando la función creada: "+ str(sumatoria))
    print("Resultado usando la función importada de math: "+ str(math.exp(x))) 
    diferencia = math.exp(x) - sumatoria
    print("La diferencia entre el valor real y la aproximación es: " + str(diferencia))

# Punto 5
Desarrollar un programa que permita determinar el Minimo Comun Multiplo de dos numeros enteros. Abordar el problema desde la perpectiva iterativa como recursiva.

# Punto 6
Desarrollar un programa que determine si en una lista no existen elementos repetidos.

####Código:
    def Creador_listas (n: str) -> list: #Funcion para crear la lista a examinar. 
        lista = []
    
        for i in range(t): #Ciclo for para ingresar los elementos de la lista.
            n = input("Ingresar elementos de la lista: ")
            lista.append(n)
        return lista

    if __name__ == "__main__": #Función principal con variables definidas.
        n = 0
        t = int(input("Insertar tamaño deseado para la lista: "))
        lista_creada = Creador_listas (n)#Llamando a la función que creamos para hacer la lista. 
        print(lista_creada)

        for i in lista_creada :
            if lista_creada.count(i) == 1:
               bandera = True
            else:
                bandera = False
        if bandera == True:
            print("En la lista " + str(lista_creada) + " no hay elementos repetidos")
        else:
            print("En la lista " + str(lista_creada) + " existen elementos repetidos")
            
# Punto 7 

Desarrollar un programa que determine si en una lista se encuentra una cadena de caracteres con dos o más vocales. Si la cadena existe debe imprimirla y si no existe debe imprimir 'No existe'.


1. Para este punto se crea una funcion la cual nos permirira hallar las vocales que se encuentran en la cadena ingresada, se crean dos listas una vacia para almacenar los datos de vocales que se encuentren en la cadena, y otra para poder comprar y saber si son o no vocales.
![reto 8 1](https://user-images.githubusercontent.com/124607325/236600027-4b48f2f2-7eb7-4937-b65d-295c9bde430c.png)


2. Para encontrar y contar las vocales de la cadena se inicia un contador en cero de vocales, y se recorre con un ciclo for cada caracter de la cadena. Si el caracter  recorrido llega a ser una vocal, se agrega a la lista vacía Lista y se aumenta el contador de vocales. Si el contador de vocales alcanza o supera el valor de 2, significa que se han encontrado dos o más vocales y se retorna la lista de vocales encontradas. si no existen vocales en la cadena se imprimira no existe.

![reto 8 2](https://user-images.githubusercontent.com/124607325/236600032-34a47994-6450-40ee-9bcf-54927c83018a.png)


3. Para ejectuar el programa se pide ingresar la cadena la cual se evaluara por la funcion, y se evaluara si cumple con las condiciones establecidas, si cumple se imprimira que se encontraron dos o mas vocales.

![reto 8 3](https://user-images.githubusercontent.com/124607325/236600046-b078d008-aa9a-41cb-8e9a-8a17fc15a356.png)

## Codigo :


       def Hallar_vocales_cadena(Cadena) -> chr:
           Lista = []  # Se Crea una lista vacía para almacenar las vocales encontradas
           Lista_vocales = ["a", "e", "i", "o", "u", "A", "E", "I", "O", "U"]  # se crea una lista con todas las vocales en minúsculas y mayúsculas para poder comparar.
    
           vocales = 0  # se inicia el contador de vocales a cero
          for caracter in Cadena:  #  se recorre con el ciclo for cada caracter en la cadena
               if caracter in Lista_vocales:  # Si el caracter es una vocal,  se agregara a la lista vacia y aumentar el contador de vocales
                   Lista.append(caracter)
                   vocales += 1
                   if vocales >= 2:  # Si se han encontrado dos o más vocales, retornar la lista de vocales y terminar la función
                      return Lista
    
           print("No existe")  # Si no se encontraron dos o más vocales,  se imprimir un mensaje de error
    

       if __name__ == "__main__":
           cadena = input("Ingrese la cadena: ")
           Lista = Hallar_vocales_cadena(cadena)  # se llama a la función Hallar_vocales_cadena() para buscar las vocales en la cadena
           if Lista:  # Si se encontraron dos o más vocales, imprimir la lista de vocales encontradas
                   print("Se encontraron dos o más vocales en la cadena "+str(cadena) +", estas son: "+ str(Lista))     
                   
                   
                   
                   
# Punto 8 

Desarrollar un programa que dadas dos listas determine que elementos tiene la primer lista que no tenga la segunda lista.

1. Para este punto se cran tres listas vacias las cuales almmacenaran datos durante el priceso, las dos primeras listas seran aquellas que llenaremos con los valores que queremos comparar, y la tercera lista que es la lista de diferencia sera la que guarda los valores que no estan en la segunda lista pero si en la primera.

![reto 8 1](https://user-images.githubusercontent.com/124607325/236601075-0dc3cf0e-087b-482b-b4ec-f5359aac9d0d.png)

2. Se define la función para hallar los elementos que no se encuentran. Dentro de la función, se recorre con un ciclo for cada elemento de la lista 1 y se verifica si ese elemento no está en la lista 2. Si el elemento no está en la ista 2, se agrega a la lista Diferencia, y se devuelve la lista Diferencia con los elementos de la primera lista que no están en la segunda lista.

![reto 8 2](https://user-images.githubusercontent.com/124607325/236601699-2af4b1d5-0ba8-4bc4-8352-4d1625ccf97c.png)

3. Para ejecutar se pide ingresar el tamaño y los elementos de la lista 1 y 2. Luego, se llama a la función hallar_elemento() para obtener la lista de diferencia y se imprime la lista 1, la lista 2 y la lista de diferencia. 

![reto 8 3](https://user-images.githubusercontent.com/124607325/236601754-b6650f91-ba0b-4e7c-a91e-69996571a644.png)



## Codigo

       lista1 = []  # se crea una lista 1 vacia a la cual se le agregaran los valores
       lista2 = []  # se crea una lista 2  vacia a la cual se le agregaran los valores
       Diferencia = []   # se crea una lista  vacia llamada diferencia a la cual se le agregaran los valores que no esten en la segunda lista

       # se crea una función que recibe dos listas como parámetros y devuelve una lista con los elementos de la primera lista que no están en la segunda lista
       def hallar_elemento(lista1, lista2):
           for i in lista1:  # Se recorre cada elemento de la lista 1
               if i not in lista2:  # Si el elemento no está en la lista 2, se agrega a la lista de diferencia
                   Diferencia.append(i)
           return Diferencia  # Se devuelve la lista de diferencia

       if __name__ == "__main__":
           n = int(input("tamaño de la lista: "))  # Se solicita el tamaño de la lista 1 al usuario
           for i in range(n):  # Se itera n veces para que el usuario ingrese n elementos a la lista 1
              valor = input(" ingrese elementos a la lista: ")
              lista1.append(valor)  # Se agrega el valor ingresado a la lista 1
    
          m = int(input("tamaño de la lista: "))  # Se solicita el tamaño de la lista 2 al usuario
           for i in range(m):  # Se itera m veces para que el usuario ingrese m elementos a la lista 2
               valor = input(" ingrese elementos a la lista : ")
               lista2.append(valor)  # Se agrega el valor ingresado a la lista 2
    
           diferencia = hallar_elemento(lista1, lista2)  # Se llama a la función hallar_elemento() para obtener la lista de diferencia
           print(" la lista 1 es " + str(lista1), " la lista dos es " + str(lista2))  # Se imprime la lista 1 y la lista 2
           print("Elementos en la primera lista que no están en la segunda lista son :")
           print(diferencia)  # Se imprime la lista de diferencia

