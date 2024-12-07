# 1. Formulación del problema

<p align="center">
  <img src="image.png" alt="Imagen del ejercicio n°4" />
</p>

# 2. Resolución

> I) Entrada del n° de filas y columnas en la matriz

- En este ejercicio se pide ingresar 2 variables n° de filas y n° de columnas respectivamente (n y m), se utiliza la libreria Scanner para ingresar dichos datos siempre y cuando cumplan la condición de ser mayores a 0.

```bash
import java.util.Scanner;
```

```bash
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.println("Ingresar dimension [n]: ");
        int n = sc.nextInt();
        
        if(n <= 0){
           n = sc.nextInt();;
        }  
        System.out.println("Ingresar dimension [m]: ");
        int m = sc.nextInt();
        
        if(m <= 0){
           m = sc.nextInt();;
        } 
```

> II) Ingreso de numeros enteros en la matriz 
```bash
transpuesta(n,m);
```
- Se llama a la función `transpuesta(n,m)` la cual utilizara las variables `"n"` y `"m"`.
- Se inicializa dos estructuras bidimensionales: `Matriz[n][m]` y `Transpuesta[m][n]`.
- Se ingresan los datos numericos a cada elemento de la matriz mediante un bucle doble.

```bash
public class Main {
    public static void transpuesta(int n,int m){
    Scanner sc = new Scanner(System.in);
    int[][] Matriz = new int[n][m]; 
    int[][] Transpuesta = new int[m][n];
    
    for(int i=0; i < n; i++){
        
        for(int j=0; j < m;j++){
            System.out.print("["+i+"]"+"[" + j+"]");
            Matriz[i][j] = sc.nextInt();           
        }
    }
```
> III) Impresión de matrices (original y transpuesta) e transferencia de elementos de la matriz original hacia la transpuesta

- Nuevamente se hace un recorrido en doble bucle para imprimir cada elemento de ambas matrices
- Una matriz traspuesta se trata del resultado cuando las filas se vuelven columas y viceversa a partir de una matriz original, al tener la matriz `Matriz` rellenada vamos a pasar estos elementos a la matriz `Transpuesta[m][n]` mientras imprime sus elementos de salida, al final el algoritmo concluye con la matriz original y su contraparte traspuesta.

```bash
    System.out.println("MATRIZ ORIGINAL:");
     for(int i=0; i < n; i++){
        for(int j=0; j < m;j++){
         System.out.print("["+Matriz[i][j]+"]"); 
        }
    System.out.println("");
    }
    System.out.println("MATRIZ TRANSPUESTA:");
    for(int i=0; i < m; i++){
        for(int j=0; j < n;j++){
        Transpuesta[i][j] = Matriz[j][i];
        System.out.print("["+Transpuesta[i][j]+"]"); 
        }
    System.out.println("");    
    }
    }
```

### Codigo completo

```bash
import java.util.Scanner;

public class Main {
    public static void transpuesta(int n,int m){
    Scanner sc = new Scanner(System.in);
    int[][] Matriz = new int[n][m]; 
    int[][] Transpuesta = new int[m][n];
    
    for(int i=0; i < n; i++){
        
        for(int j=0; j < m;j++){
            System.out.print("["+i+"]"+"[" + j+"]");
            Matriz[i][j] = sc.nextInt();           
        }
    }
    
    System.out.println("MATRIZ ORIGINAL:");
     for(int i=0; i < n; i++){
        for(int j=0; j < m;j++){
         System.out.print("["+Matriz[i][j]+"]"); 
        }
    System.out.println("");
    }
    System.out.println("MATRIZ TRANSPUESTA:");
    for(int i=0; i < m; i++){
        for(int j=0; j < n;j++){
        Transpuesta[i][j] = Matriz[j][i];
        System.out.print("["+Transpuesta[i][j]+"]"); 
        }
    System.out.println("");    
    }
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.println("Ingresar dimension [n]: ");
        int n = sc.nextInt();
        
        if(n <= 0){
           n = sc.nextInt();;
        }  
        System.out.println("Ingresar dimension [m]: ");
        int m = sc.nextInt();
        
        if(m <= 0){
           m = sc.nextInt();;
        } 
        transpuesta(n,m);
    }
}
```

# 3. Complejidad

> I) Entrada del n° de filas y columnas en la matriz

- Complejidad de tiempo: 𝑂(1) (Ya que toma una entrada,en el peor caso de multiples entradas erroneas seria 𝑂(k))
- Complejidad de espacio: 𝑂(1) (Debido a que utiliza solo variables escalares)

> II) Ingreso de numeros enteros en la matriz

- Complejidad de tiempo: 𝑂(n x m) (Debido a que requiere recorrer `n` x `m` dependiendo del n° de filas y columnas)
- Complejidad de espacio: 𝑂(n x m) (Debido a que ocupa una estructura de datos bidimensional de tamaño `n` x `m`)

> III) Impresión de matrices (original y transpuesta) e transferencia de elementos de la matriz original hacia la transpuesta

- Complejidad de tiempo: 𝑂(n x m) 
- Complejidad de espacio: 𝑂(n x m)
  - Todas sus complejidades llegan a ser de `n x m` tanto en la impresión de las matrices y calculo de la traspuesta.
