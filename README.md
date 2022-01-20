# Examen-20-01-2022-ordinaria

En el ejercicio numero 1 he utilizado la estructura try-except,para prevenir posibles errores a la hora de introducir los datos,de tal froma que el programa no te dejara
continuar hasta que hayas introducido el valor correcto y de paso evita que el programa se detenga.Despues,he creado dos listas vacias para almacenar los digitos de los numeros
y he añadido dichos digitos transformando los numeros a datos de tipo cadena para poder iterar sobre ellos y poder completar las listas.Por ultimo he transformado las listas
a conjuntos utilizando la funcion set(),debido a que los conjuntos pueden compararse y  ver si son iguales o no independientemente del orden en el que se encuentren sus elementos.

En el ejercicio numero 3 primero he inportado  la funcion radnint del modulo random.He programado un input() con el que se determina el numero de jugadores que participan,una variable con la que determinar el numero de jugador que juega cada vez y dos listas vacias,una que almacenara a su vez listas de dos elementos,uno es el numero del jugador y el otro es su correspondiente puntuacion.La otra almacena todaslas puntuaciones,para despues poder determinar cual es el mayor valor de todas ellas utilizando la funcion max().Por ultimo he utilizado un bucle for para comparar el segundo valor de cada lista dentro de la lista que almacena a su vez las listas con el numero de jugador y su correspondiente puntuacion,para encontrar a que jugador corresponde la maxima puntuacion.
///from random import randint


while True:
    try:
        numero1=int(input("ingrese un numero entre 0 y 9999"))
        numero2=int(input("ingrese otro numero entre 0 y 9999"))
    except:
        print("vuelva a ingresar los numeros porfavor")
        continue
    break


lista_numero1=[]#almacena los digitos del primer numero
lista_numero2=[]#almacena los digitos del segundo numero
for i in str(numero1):#convierto el entero a str para poder iterar con el
    lista_numero1=lista_numero1+[int(i)]
print(lista_numero1)
for j in str(numero2):
    lista_numero2=lista_numero2+[int(j)]
print(lista_numero2)


if set(lista_numero1)==set(lista_numero2):#convierto las listas a conjuntos.Aunque elimine los valores repetidos,el hecho de que sean repetidos implica que son iguales,por tanto es irrelevante.
    print("los numeros",numero1,numero2,"estan formados por las mismas cifras")
else:
    print("los numeros",numero1,numero2,"no estan formados por las mismas cifras") 





#EJERCICIO NUMERO 3
numero_de_jugadores=int(input("cuantos van a jugar"))

c=1#indica el numero del jugador
lista_lanzamientos=[]#almacena el numero del jugador junto con su puntuacion
valores_obtenidos=[]#almacena todas las puntuaciones
while True:
    lanzamiento1=randint(1,6)
    lanzamiento2=randint(1,6)
    if lanzamiento1==lanzamiento2:
        print("la puntuacion del jugador",c," es:",lanzamiento2)
        lista_lanzamientos=lista_lanzamientos+[[c,lanzamiento2]]
        valores_obtenidos=valores_obtenidos+[lanzamiento2]
    else:
        if lanzamiento1!=lanzamiento2:
            continue
    if c<=numero_de_jugadores:
        c=c+1
    else:
        print("lista con los jugadores y sus correspondientes puntuaciones:",lista_lanzamientos)
        mayor_v=max(valores_obtenidos)
        for k in range(len(lista_lanzamientos)):
            if lista_lanzamientos[k][1]==mayor_v:
                print("el jugador ",lista_lanzamientos[k][0],"ha ganado la partida ")
        break      


///
