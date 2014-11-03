Tablas
======

tablas de verdad. 
## INICIO DEL PROGRAMA
##
##
import time ## se importa la librería que utilizaremos para jugar con el tiempo
print 'bienvenido al programa: PARCIAL 2' ## introducción 
print 'por favor espere...' ##efecto de que es un programa complejo
time.sleep( 2 ) #pausa que le dimos para que parezca mas real con respecto a que es complejo
print 'cargando...' ##entrando al programa
time.sleep( 2 ) #pausa, las pausas también las usamos para que así, nuestro proyecto por más coincidencia que haya, no se parezca al de los demás
print "Inicio : %s" % time.ctime() ##comando encontrado en internet para desplegar los datos de fecha y hora
print '\n' ##salto
print 'Cargado.' ##inicio del programa
print 'realizardores:' ##información de estudiantes
print 'Manuel Alberto Marquez Aleman----carnet 201403687'
print 'Jose Pablo Monterroso Urrutia----carnet 201314634\n'

print 'en este programa, se desplegaran los ejercicios con terminación 4 y 7', ## más explicación
print 'del parcial dado. empecemos:'

print 'el programa se basa en encontrar los resultados en un arreglo de tablas de verdad,'
print 'de todos los casos posibles, con 3 variables (A, B, C)'


## ----------------------aquí empezamos con la fase de tabla -------------------------- ##


"""las listas usadas en esta sección son lista1, lista2, lista3--- las cuales tienen como propósito almacenar los números,
almacenar el arreglo de numeros, y almacenar la matriz ya creada para desplegar, respectivamente"""

##los contadores usados en esta sección son: a, x, i, j, b y c
  
lista1 = []
n = int(raw_input('ingrese numero de variables: '))
time.sleep( 1 )
a = 1
while a <= n: ##ciclo para repetir el llenado de la lista 1 ##
    x = 0
    while x< (((2**n)/2)): ##ciclo para llenar primera variable
        i = 0
        while i < 2**(a-1): ##llenado de numeros 0 en la lista
            lista1.append(0)
            i = i+1
        j = 0
        while j < 2**(a-1): ##llenado de numeros 1 en la lista
            lista1.append(1)
            j = j+1
        x = (x + (2**(a-1)))
    a = a+1
lista3 = [] ##lista máxima, la que se despliega al final
b = 0
while b < 2**n: ##ciclo para agrupar todo en la matriz
    lista2 = []
    c = n-1
    while c >= 0: ##ciclo para llenar lista2 con las listas 1
        lista2.append(lista1[b+(c*(2**n))])
        c = c-1
    lista3.append(lista2)
    b = b+1
for o in lista3:
    print o
## ----fase tablas finalizada---- ##


## ----------------------aquí empezamos con la fase de funciones ---------------------- ##
"""al realizar las operaciones logicas en las terminaciones 4,5,6,7 se omiten ciertas conexiones
ya que su función no es eficiente, ya que se ve, luego contrarrestada con otra. así que se omite para salvaguardar
el uso de datos del programa, evitar perder el tiempo en operaciones que al fin y al cabo no se usan. por favor tomar estas consideraciones
para bien. """

print ("\n")
print "Para correr el programa, escribir objecto=Logical() y presionar ENTER."

# Clase que lleva cada una de las funciones logicas solicitadas.
class Logical(object):

    #Se declararon variables globales para no tener problemas de reconocimiento en las funciones.
    global lista1,lista2,lista3,lista4,pro,pro1,pro2
    pro=[]
    pro1=[]
    pro2=[]
    lista1 = []
    lista2 = []
    lista3 = []
    lista4 = []

    #Valores de A
    for i in range(4):
        lista1.append(0)
    for j in range(4,8):
        lista1.append(1)
        
    #Valores de B
    for k in range(2):
        lista2.append(0)
    for l in range(2,4):
        lista2.append(1)
    for m in range(4,6):
        lista2.append(0)
    for n in range(6,8):
        lista2.append(1)
        
    #Valores de C
    for u in range(8):
        if u % 2 == 0:
            lista3.append(0)
        else: 
            lista3.append(1)
    lista4.append(lista1)
    lista4.append(lista2)
    lista4.append(lista3)

    #Despliega la Matriz de los valores A,B,C
    for s in lista4:
        print s
        
    #El despliegue inmediato de las funciones siguientes.
    def __init__(self):
        self.carnet = " "
        self.ask()
        self.logor()
        print "Las respuestas a los problemas planteados son: "
        self.logand()
        self.lognotor()
        print 'Bendiceme, Ivan'
        print 'Gracias por la atencion' ##despedida
        
    #Recibe el nombre del usuario para interactuar con él.
    def ask(self):
        while 1:
            carnet = raw_input("Ingrese nombre: ")
            if carnet == " ":
                print "No sea macho e Ingrese un nombre."
            else:
                print "Buen dia ",carnet,", querido joven imberbe de la creacion"
                break
        self.carnet = carnet
        
    #Realiza la conexion logica "OR" entre los valores de las columnas A y B.
    def logor(Logical):
            for j in range(8):
                    if lista1[j]==1 and lista2[j]==1:
                        pro.append(lista1[j] and lista2[j])
                    else:
                        pro.append(lista1[j] or lista2[j])

    #Realiza la negacion de la lista "C" y la disyuncion entre la negacion de C y el valor de la disyuncion de A y B 
    def lognotor(Logical):
            for j in range(8):
                if lista3[j]==0:
                    lista3[j]+=1
                else:
                    lista3[j]-=1
                if pro[j]==1 and lista3[j]==1:
                    pro2.append(pro[j] and lista3[j])
                else:
                    pro2.append(pro[j] or lista3[j])
            print "Terminaciones: 6, 7--->", pro2

     #Realiza la conjuncion entre los valores de la Columna C y el valor de la disyuncion entre A y B.
    def logand(Logical):
            for j in range(8):
                pro1.append(pro[j] and lista3[j])
            print "Terminaciones: 4, 5--->", pro1

## ----fase funciones finalizada ---- ##
