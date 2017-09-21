# calculadorajava
package calculadora;

public class Calculadora {

    private static int potencia(double x, int i) {
        throw new UnsupportedOperationException("Not supported yet."); //To change body of generated methods, choose Tools | Templates.
    }

    public Calculadora() { //contiene las operaciones 
    }

    public static int sum(int num1, int num2) { //para realizar la suma 
        return num1 + num2;//devuelve la operacion de los dos numeros 
    }

    public static int res(int num1, int num2) {//para realizar la resta 
        return num1 - num2;//devuelve la operacion de los dos numeros 
    }

    public static int mod(int num1, int num2) {//para ralizar el modulo 
        return num1 % num2;//devuelve la operacion de los dos numeros 
    }

    public static int multiplicacion(int num1, int num2) {//realizar multiplicacion recursiva 
        int result = 0;//variabre para guardar resultado 
        for (int i = 0; i < num2; i++) {//ciclo para realizar la suma del mismo numero hasta llegar al numero 2
            result = sum(result, num1);//llama a la operacion suma y suma el resultado con num1
        }
        return result;//devuelve el resultado final del ciclo 
    }

    public static double division(double num1, double num2) {//para realizar la division 
        if (num2 != 0) {//condicion para indeterminacion 
            return num1 / num2;//si se cumple la condicion se realiza la division normalmente
        } else {//si no se cumple la condicion anterior 
            return Double.NaN;//devuelve NaN que da a conocer la indeterminacion 
        }

    }

    public static int factorial(int x) {// para ralizar el factorial 
        if (x < 1) {//condicion cuando x sea menor que 1
            return 1;//si la condicion es true devolver 1
        } else {//si la condicion es false 
            return multiplicacion(x, factorial(x - 1));//devolver el factorial llamando a las funcioness respectivas
        }

    }

    public static double potencia(int base, int exponente) {//realizar la potencia de forma recursiva
        if (exponente == 1) {//condicion exponente igual a uno
            return base;// si la condicion es true devolver la base 
        } else {//si la condicion es false 
            if (exponente == 0) {//condicion para exponente igial a cero 
                return 1;//si la condicion es true devolver 1
            } else {//si la condicion es false 
                if (exponente > 1) {//condicion exponente mayor qur 1 
                    return multiplicacion(base, (int) potencia(base, exponente - 1));//devolver el resultaso de la potencia 
                } else {//si la condicion es false 
                    return 1 / potencia(base, multiplicacion(exponente, (-1)));//devolver el resultado invirtiendo la base para quitar exp negativo
                }
            }

        }
    }

    public static double seno( double x) { //para realizar el seno con serie de taylor 
        double A = 0;
        int B = 1; 
        for (int i = 1; i < 10; i+=2) {//ciclo para realizar operacion desde 1 hasta que i llegue a ser menor a 10
            A += multiplicacion(B,potencia( x, i)) / factorial(i);//operacion para seno 
        }
        return A;//resultado final del ciclo y operaciones 
    }

    public static double coseno( double x) {//realizar el coseno 
       double A = 0;
        int B = 1;
        for (int i = 0; i < 10; i+=2) {//ciclo desde 0 hasta 10 con paso 2 
            A += multiplicacion(B,potencia( x, i)) / factorial(i);//operacion para hallar coseno 
        }
        return A;//devuelve el resultaso del coceno 
    }
    public static int cuadratiaca(int num1, int num2, int num3) {//funcion cuadratica 
        int [] resultados = new int[2]; // arreglo para guardar los 2 resultados 
        if(num1 !=0)//condicion para indeterminacion 
        {//a cinticuacin se pueden ver las operaciones respectivas llamando a las funciones necezarias para los dos resultados
         int b = multiplicacion(num2,-1); //para cambiar b a negativo
         resultados[0]= sum(b, (int) Math.sqrt( res((int) potencia( b,2),multiplicacion(4,multiplicacion(num1,num3)))))/multiplicacion(2,num1); 
         resultados[1]= res(b, (int) Math.sqrt( res((int) potencia( b,2),multiplicacion(4,multiplicacion(num1,num3)))))/multiplicacion(2,num1); 
         return resultados[1];//devuelve los resultado 2 
        }  
        return resultados[0];//devuelve resultado 1 
       
    }
    public static int integral(int inicio, int fin, int paso) {//realizar la integral 
         
        int acum =0;//variable acumuladora 
        for(int i =inicio; i<fin; i+=paso)//ciclo dados inicio fin y paso por el usuario
        {
            acum+=(paso*potencia(i,2));//operacion de integral
        }
        
        return acum;//devuelve el resultado de la integral 
    }

    public int addition(int parameter, int parameter0) {
        throw new UnsupportedOperationException("Not supported yet."); 
    }

}
