# Conta Bancaria 
 Conta Bancaria em Java 

 🚀 Projetos iniciais em Java desenvolvidos para praticar lógica de programação, estruturas condicionais e os fundamentos da Orientação a Objetos (POO).


public class Main {
    public static void main(String[] args) {



       ContaBancaria conta1 = new ContaBancaria();

        System.out.println();
        conta1.titular = "Anderson";
        conta1.saldo = 1000;
        conta1.depositar (200);
        conta1.sacar (300);

        System.out.println( conta1.titular);
        System.out.println("Saldo Atual:" + conta1.saldo);

        ContaBancaria conta2 = new ContaBancaria();

        System.out.println();
        conta2.titular = "Luzimar";
        conta2.saldo = 1000;
        conta2.sacar (200);

        System.out.println(conta2.titular);
        System.out.println("Saldo Atual:" + conta2.saldo);


    }
}
