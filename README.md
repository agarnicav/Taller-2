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

6. Si el carácter actual en el bucle es un punto decimal, la variable "bandera" se establece en "False" para indicar que se está en la parte decimal del número.

7. Si la variable "bandera" es falsa,  los dígitos se agregan a la lista "listaDecimal" utilizando la función "append()".

8. Se imprimen las dos listas "listaEntera" y "listaDecimal" en líneas separadas para mostrar los dígitos de la parte entera y decimal del número, respectivamente.

9.  Se solicita ingresar un número real y se llama a la función "digitosNumero" para descomponer el número y mostrar sus dígitos.

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
1. Se crean dos listas vacías y se declaran las variables n1 y n2 donde se almacenarán los números a analizar.
2. A partir de un ciclo for se van a dividir los elementos de n1, antes transformado a string, que serán añadidos a la lista1. 
3. Se intercambia el orden de los elementos de la lista2 al añadir los dígitos del segundo número a la misma también con un ciclo for.
4. Finalmente se comparan ambas listas y con un condicional se establece que si son iguales se imprima el mensaje de que los números son espejos, y en el caso contrario no lo son. 
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
1. En este punto primero se abordó el cálculo del mcm desde la perspectiva iterativa. Se crea una función que recibirá como parámetros os números a los q se les desea calcular el mcm y la cantidad de iteraciones (estas estaran dadas por la comparación del mayor entre ambos números). En cada iteración se divide i entre x y y, usando un condicional se determina que i es múltiplo de ambos números si su módulo es cero al dividir entre ambos números, de lo contrario se suma uno a i y continúa el ciclo. Al finalizar la función retorna el valor final de i.
2. Desde la perspectiva recursiva igualmente se define la función, que va a recibir los mismos parámetros mencionados anteriormente. Luego planteamos un caso base en que x o y es igual a uno. Se plantea el condicional de que si el módulo de i entre x y y es cero entonces i es múltiplo, de lo contrario se altera el valor de i en 1. 
3. El usuario podrá seleccionar cual de las funciones desea utilizar para lo cual podrá elegir las opciones uno o dos definidas en la función principal como True. Si no ingresa una opción válida se imprimirá un mensaje.


# Punto 6
Desarrollar un programa que determine si en una lista no existen elementos repetidos.
1. El primer paso para este punto crear una función con la cual haremos nuestra lista. Creamos una lista vacía y en la variable t almacenamos el número de datos que deseamos tenga la lista. Luego a partir de un ciclo for los elementos son ingresados en la lista.
2. Ya con la lista creada con otro ciclo for la recorremos y con la función integrada cunt() obtendremos el número de cada elemento.
3. Establecemos una bandera q en caso de ser igual a uno el programa imprimirá que no hay elementos repetidos en la lista, de lo contrario imprimirá que existen elementos repetidos.

#### Código:
        
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
           
 # Punto 9
 Resolver el punto 7 del taller 1 usando operaciones con vectores.
 1. En este punto lo primero que hicimos fue una función para crear el vector con 5 elementos.
 2. Llamamos a nuestra función 
 3. Para el promedio utilizamos la función sum() para conocer la sumatoria de los números y luego dividimos entre 5
 4. Para el promedio multiplicativo empleamos un ciclo for para multiplocar todos números del vector. Luego le hallamos la ríz quinta al resultado.
 5. Con la función sort() organizamos los elementos e orden ascendente, con los números organizados de esta manera imprimimos el número que ocupa la posición dos que sería el elemento cetral y por tanto la mediana. 
6. Utilizando reverse los reorganizamos en orden descendente.
7. Con los elementos organizados de esta manera ubicamos el menor, que corresponderá al índice [5-1], o sea estará ubicado de último mientras q el índice cero será el mayor. Elevamos el mayor número a la potencia del menor.
8. Con esta misma lógica al menor número se le halla la raíz cuadrada elevándolo a la 1/3.
 
 
        def Crear_vector (elementos: float) -> list:
            v = [] #Crear un arreglo vacío para el vector
            for i in range (5): # Ciclo for para ingresar los elementos que formarán el vector
                elementos = float(input("Inserta elementos del vector: "))
                v.append(elementos)
            return v
        if __name__ == "__main__":
            elementos = 0
            v = Crear_vector(elementos)
            print("Vector: " + str(v)) 
    
            #El promedio
            sumatoria = sum(v) #Es la suma de todos los elementos del vector dividido entre la cantidad de elementos. Se utiliza la                   función sum() 
            promedio = sumatoria/5
            print("El promedio es: " + str(promedio))

            #El promedio multiplicativo (multilplica todos y luego calcula la raíz de la cantidad de operandos)
            mult = 1
            for i in v:#Ciclo for para multiplicar todos los elementos dentro del arreglo y luego se halla la raíz 5ta, ya que son 5                   operandos.
            mult *= i 
            promedio_multiplicativo = mult**(1/5)
            print("El promedio multiplicativo es:" + str(promedio_multiplicativo))

            # Ordenar los números de forma ascendente
            v.sort()
            print("Números ordenados de forma ascendente: " + str(v))

            #La mediana
            print("La mediana es: " + str(v[2])) # Como el vector tiene 5 elementos la mediana será el valor que ocupe la tercera posición             una vez ordenados estos de menor a mayor

            #Ordenar los números de forma descendente
            v.sort(reverse = True) 
            print("Números ordenados de forma descendente: " + str(v))

            #La potencia del mayor número elevado al menor número
            potencia: float = v[0]**v[4] #En este caso basado en el orden que se le dio al arreglo en el paso anterior se realiza la                   operación de potenciación indicando como base el primer elemento de la lista y como exponente el último
            print("Potencia del mayor número elevado al menor número: " +  str(potencia))

            #La raíz cúbica del menor número
            raiz_cubica = v[4]**(1/3) # Como los números fueron ordenados de mayor a menor anteriormente, solo se debe hallar la raíz del             último elemento en el arreglo
            print("Raíz cúbica del menor número: " + str(raiz_cubica))
            
# Punto 10
Desarrollar un algoritmo que determine si una matriz es mágica. Se dice que una matriz cuadrada es mágica si la suma de cada una de sus filas, de cada una de sus columnas y de cada diagonal es igual.

1. El primer paso será crear una función la cual realizará el llenado de la matriz de tamaño n, el cual será asignado por el usuario y se enviará como parámetro a la función.

2. Luego, crearemos otra función la cual tendrá como objetivo imprimir la matriz anteriormente llenada y recibida como parámetro en esta nueva función.

3. Como tercer paso lo que haremos será crear una nueva función que determine si la matriz ingresada anteriormente, es una matriz mágica, esto se consigue realizando la suma de cada una de las filas, columnas, la diagonal principal y la diagonal secundaria. Si cada una de estas sumas nos da como resultado el valor de n * ( n ^ 2 + 1 ) // 2 siendo n el tamaño de la matriz (La cual debe ser cuadrada y no tener elementos repetidos), podremos decir que la matriz es mágica.

4. Posteriormente crearemos una nueva función que determinará si en la matriz existen elementos repetidos, esto, guardando todos los elementos en una lista y luego verificando que cada uno de los elementos se encuentre solo una vez en dicha lista. Si efectivamente solo se encuentran una vez, existe la posibilidad de que la matriz sea mágica; Sin embargo, si al menos un elemento se repite en la lista podremos decir que la matriz no es mágica.

5. Por último, definiremos una función main en donde asignaremos el tamaño de la matriz, para luego enviar este valor como parámetro a las funciones correspondientes. Realizaremos el llamado de las 4 funciones creadas y haremos las validaciones de si existen elementos repetidos en la matriz y si se determinó que la matriz fuese mágica. Dependiendo del caso se mostrarán los mensajes pertinentes. 

#### Código:
    def crearMatriz(n:int) -> list:
        # Función que realiza el llenado de una matriz cuadrada de tamaño n recibido como parámetro 
        matriz = [] # Creación de la matriz a la cual se le agregarán las fulas con los elementos 
        fila = [] # Creación de la fila en donde agregaremos los elementos 
        for i in range(n):
            for j in range(n):
                num = float(input("Ingrese el elemento ["+str(i+1)+"]["+str(j+1)+"] : ")) # Ingreso de los elementos que compondrán a las         filas y despues a la matriz
                fila.append(num) # Adición de cada uno de los elementos al final de la fila 
            matriz.append(fila) # Adición de cada fila al final de la matriz
            fila = [] # Vaciado de la fila para que pueda volver a ser llenada
        return matriz # Retorno de la matriz creada

    def imprimirMatriz(n:int,matriz:list):
        # Función que imprime las filas de una matriz recibida como parámetro de tamaño n también recibido como parámetro
        for i in range(n): print(matriz[i]) # Impresión de cada fila de la matriz

    def matrizMagica(n:int,matriz:list) -> bool:
        # Función que realiza la sumatoria de las filas, columnas y diagonales de una matriz recibida como parámetro y comprueba si cada           suma es igual a n * ( n ** 2 + 1 ) // 2 siendo n el tamaño de la matriz recibido como parámetro 
        sumaFilas = 0 
        sumaColumnas = 0 
        sumaDiagonal1 = 0 
        sumaDiagonal2 = 0 
        bandera = True 
        sumaMagica = n * ( n ** 2 + 1 ) // 2 # Formula que indica el resultado que debe tener cada suma de filas, columnas y diagonales           para que la matriz se considere como mágica

        for i in range(n):
            for j in range(n):
                sumaFilas = sumaFilas + matriz[i][j] # Cálculo de la sumatoria de cada una de las filas de la matriz
            if sumaFilas != sumaMagica: # Comparación del resultado de la suma de filas con el valor que debería ser para que se considere             la matriz como mágica
                bandera = False
                break 
            sumaFilas = 0

        for i in range(n):
            for j in range(n):
                sumaColumnas = sumaColumnas + matriz[j][i] # Cálculo de la sumatoria de cada una de las columnas de la matriz
            if sumaColumnas != sumaMagica: # Comparación del resultado de la suma de filas con el valor que debería ser para que se                   considere la matriz como mágica
                bandera = False
                break
            sumaColumnas = 0 
    
        for i in range(n):
            for j in range(n):
                if i == j:
                    sumaDiagonal1 = sumaDiagonal1 + matriz[i][j] # Cálculo de la sumatoria de la diagonal principal de la matriz
        if sumaDiagonal1 != sumaMagica: # Comparación del resultado de la suma de filas con el valor que debería ser para que se considere         la matriz como mágica
            bandera = False

        for i in range(n):
            sumaDiagonal2 = sumaDiagonal2 + matriz[i][n-i-1] # Cálculo de la sumatoria de la diagonal secundaria de la matriz
        if sumaDiagonal2 != sumaMagica: # Comparación del resultado de la suma de filas con el valor que debería ser para que se considere         la matriz como mágica
            bandera = False

        return bandera 

    def elementosRepetidos(n:int,matriz:list) -> bool:
        # Función que comprueba si los elementos ingresados en un matriz recibida como parámetros se repiten  
        repetidos = [] # creación de una lista vacia a la cual ingresaremos los datos de la matriz y comprobaremos si sus elementos se             repiten 
        for i in range(n): 
            for j in range(n):
                 repetidos.append(matriz[i][j]) # Ingreso de los elementos de la matriz a la lista 

        for i in repetidos:
            if repetidos.count(i) == 1: # Validación de que cada elemento en la lista exista solo una vez, en caso de serlo bandera = True         y en caso de no serlo bandera = False
                bandera = True
            else: 
                bandera = False 
                break
        return bandera # Retorno del valor de bandera 
    

    if __name__ == "__main__":
        n = int(input("Ingrese el tamaño de la matriz: ")) # Ingreso del tamaño que tendrá la matriz (para que pueda ser mágica debe ser           cuadarada)
        matrizM = crearMatriz(n) # Llamado de la función crearMatriz y envío del parámetro n 
        print("\nMATRIZ INGRESADA") 
        imprimirMatriz(n,matrizM) # Impresión de la matriz haciendo el llamado de la función imprimirMatriz y envío de los parámtros n y           matrizM
        magica = matrizMagica(n,matrizM) # Comprobación de que la matriz sea mágica haciendo el llamado de la función matrizMagica y envio         de los parámetros n y matrizM
        elementos = elementosRepetidos(n,matrizM) # Comprobación de que no existan elementos repetidos en la matriz haciendo el llamado de         la función elementosRepetidos y envio de los parámetros n y matrizM
        if elementos == True: # Validación de que no existan elementos repetidos en la matriz, en caso de que si se repitan, la matriz no         podrá ser mágica
            if magica == True: # Validación de que la matriz sea mágica 
                print("\nLa matriz ingresada es mágica")
            else:
                print("\nLa matriz ingresada no es mágica")
        else:
            print("\nLa matriz ingresada no es mágica debido a que hay elementos repetidos")
