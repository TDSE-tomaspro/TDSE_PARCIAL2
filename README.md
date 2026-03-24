# TDSE_PARCIAL2
## autor:Tomas felipe Ramirez Alvarez

Parcial:
- La conjetura de Collatz dice que si usted crea una secuencia de números, a partir de cualquier entero positivo, 
siguiendo las reglas descritas abajo, siempre la secuencia terminará en le número 1. Esta conjetura aún no se ha demostrado.

- Las reglas son:
  - f(n)=n/2
  - si n es par.
  - f(n)=3n+1
  - si n es impar.
  - La secuencia se construye a partir de un número dado k
- así:
  - a0=k
  - ai=f(ai−1)
  - Por ejemplo, dato el número k=13
  - la secuencia sería:

  - 13→40→20→10→5→16→8→4→2→1

Detalles adicionales de la arquitectura y del API
Servicio REST para construcción de la secuencia de Collatz, el servicio puede ser GET o POST. El servicio recibe 
el número inicial en la variable del query con el nombre "value".

Ejemplo de una llamado:

- http://amazonxxx.x.xxx.x.xxx:{port}/collatzsequence?value=13

Salida. El formato de la salida y la respuesta debe ser un JSON con el siguiente formato

{</div> <div> </div> <div> "operation": "collatzsequence",</div> <div> </div> <div> "input":  13,</div> <div> </div> 
<div> "output":  "13 -> 40 -> 20 -> 10 -> 5 -> 16 -> 8 -> 4 -> 2 -> 1"</div> <div> </div> <div>}

# estructura
utilizamos una estructura donde tenemos controladores, servicios y conectibilidad con dos maquinas virtuales de aws (EC2)
esto con el fin de tener dos servidores desplegados y funcionando correctamente y respaldandose uno al otro esto quiere 
decir que si uno de ellos se cae el otro toma sus actividades y las resuelve sin ningun problema.
- ![4.png](Imagenes%2F4.png)

# instrucciones de uso:
- `git clone https://github.com/TDSE-tomaspro/TDSE_PARCIAL2.git`
- `git mvn clean compile`
- `mvn mvn clean run`

Luego de correrlo correctamente vamos a la cuenta de aws.
- Logeamos con la cuenta correctamente:
  - creamos una instancia de EC2 
  - corremos por ssh o por el mismo buscador 
  - luego instalamos las dependencias:
    - `sudo yum install java-21-amazon-corretto-headless`
    - `sudo yum localinstall java-21-amazon-corretto*.rpm`
  - luego de ello ponemos los servicions de http y https a correr para que puedan conectarse a la url
  - al conectarse a la instancia:
    - `ec2-52-90-147-168.compute-1.amazonaws.com`
    - se podra ver el sistema de calculo correctamente. 

## Estructura de aws
- comenzamos creando y cargardo correctamente las extenciones y puertos para que corra segura la aplicacion:
- ![1.png](Imagenes%2F1.png)
- ![2.png](Imagenes%2F2.png)
- ![3.png](Imagenes%2F3.png)
## evidencias
- 
- ![3.png](Imagenes%2F3.png)

## conclusiones
- En primera instancia se puede concluir que los servidores estan sincronizados mediante HTML y JS, haciendo que la
comunicacion sea asincronica.
- al ser un programa de cliente servidor es rapido y eficiente al resolver la operacion matematica que se le esta proporcinando
dando asi un resultado acertado y extendible
- por ser desplegado en aws su alcance y ejecusion es mas amplia a tal grado de usarla con una url.