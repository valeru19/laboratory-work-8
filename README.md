# laboratory-work-8
import java.util.Scanner;

import static java.lang.Math.pow;

public class Main {
    static Scanner in = new Scanner(System.in);
    public static void main(String[] args) {
        System.out.println("Введите размерность массива N");
        int N = in.nextInt();
        int A[] = new int[N];
        System.out.println("Введите элементы массива, как компоненты 7 - ого числа целой дробной части");
        System.out.println("Это цифры от 0 до 6");
        for (int i = 0; i < N; i++) {
            A[i] = Vvod_dannih(i, N);
        }
        System.out.println("Массив дробной части в 7-ой форме имеет вид: ");
        printNas(A);
        System.out.println();
        double temp = 0;
        for(int i = 0,  j = -1; i <= N-1; i++, j--){
            temp += pow(7, j)*A[i];
        }
        System.out.println("В десятичной системе счисления число = \t" +temp);
    }
    public static void printNas(int[] array) {
        for(int i=0; i <= array.length-1; i++){
            System.out.print(array[i]+"\t");
        }
    }
    public static int Vvod_dannih(int i, int N) {
        System.out.println("A["+i+"] = ");
        int A = in.nextInt();
        if (A > 6 || A < 0) {
            System.out.println("Вы ввели число не из интервала от 0 до 6");
            while (A <= 0 || A > 6) {
                System.out.println("Повторите попытку A[i] от 0 до 6");
                System.out.print("A[" + i + "] =");
                A = in.nextInt();
            }
        }else if(i==0 && A == 0){
            while(A==0){
                System.out.println("Вы ввели не верно A[0], оно может быть от 1 до 6");
                System.out.println("A[ "+i+"] =");
                A=in.nextInt();
            }
        }
        return A;
    }
} ****
