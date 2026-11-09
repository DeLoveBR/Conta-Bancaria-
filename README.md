# 🚀 Projetos Iniciais em Java: Lógica e Orientação a Objetos

Este repositório foi criado para consolidar meus estudos em Java, abordando desde a lógica de programação estruturada até os primeiros conceitos de **Orientação a Objetos (POO)**. 

O projeto está dividido em duas aplicações principais executadas via console:
1. **Calculadora Interativa:** Prática de estruturas condicionais (`switch-case`) e manipulação de dados com a classe `Scanner`.
2. **Sistema de Conta Bancária:** Introdução à POO utilizando classes, atributos, objetos e métodos com regras de negócio (validação de saque).

---

## 🛠️ Como o Projeto Está Estruturado

Para o código funcionar corretamente e seguir os padrões de mercado do Java, os arquivos foram separados da seguinte forma:

```text
├── Calculadora.java         # Código da calculadora interativa
├── ContaBancaria.java       # Classe (molde) com atributos e métodos da conta
└── Main.java                # Arquivo principal que executa e testa a conta bancária
```

---

## 💻 Códigos Fontes

### 1. `Calculadora.java`
Uma calculadora dinâmica que lê valores decimais e processa as quatro operações matemáticas básicas.

```java
import java.util.Scanner;

public class Calculadora {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        double V1, V2, resultado;
        int operacao;

        System.out.println("***CALCULADORA***\n");

        System.out.print("Digite o primeiro valor: ");
        V1 = sc.nextDouble();

        System.out.print("Digite o segundo valor: ");
        V2 = sc.nextDouble();

        System.out.println("\n===Digite o Operador===\n");
        System.out.println("Digite 1 para Soma");
        System.out.println("Digite 2 para Subtração:");
        System.out.println("Digite 3 para Multiplicação:");
        System.out.println("Digite 4 para Dividir:");
        operacao = sc.nextInt();

        switch (operacao) {
            case 1:
                resultado = V1 + V2;
                System.out.println("Resultado: " + resultado);
                break;
            case 2:
                resultado = V1 - V2;
                System.out.println("Resultado: " + resultado);
                break;
            case 3:
                resultado = V1 * V2;
                System.out.println("Resultado: " + resultado);
                break;
            case 4:
                if (V2 != 0) {
                    resultado = V1 / V2;
                    System.out.println("Resultado: " + resultado);
                } else {
                    System.out.println("Erro: Não é possível dividir por zero!");
                }
                break;
            default:
                System.out.println("Valor Inválido");
        }

        System.out.println("\nFIM DO PROGRAMA OBRIGADO!!!");
        sc.close();
    }
}
```

### 2. `ContaBancaria.java`
Classe que define a estrutura de uma conta, possuindo os métodos de depósito e saque com validação de saldo.

```java
public class ContaBancaria {

    String titular;
    double saldo;

    // Método para depositar dinheiro
    void depositar(double valor) { 
        saldo = saldo + valor; 
    }

    // Método para sacar dinheiro com validação
    void sacar(double valor) {
        if (saldo >= valor) {
            saldo = saldo - valor;
        } else {
            System.out.println("Erro: Saldo insuficiente para o saque de: " + valor);
        }
    }
}
```

### 3. `Main.java`
Classe responsável por instanciar os objetos da `ContaBancaria` e simular as transações financeiras.

```java
public class Main {
    public static void main(String[] args) {

        // Teste da Conta 1
        ContaBancaria conta1 = new ContaBancaria();
        conta1.titular = "Anderson";
        conta1.saldo = 1000;
        conta1.depositar(200); 
        conta1.sacar(300);     

        System.out.println("Titular: " + conta1.titular);
        System.out.println("Saldo Atual: " + conta1.saldo);
        System.out.println();

        // Teste da Conta 2
        ContaBancaria conta2 = new ContaBancaria();
        conta2.titular = "Luzimar";
        conta2.saldo = 1000;
        conta2.sacar(200);     

        System.out.println("Titular: " + conta2.titular);
        System.out.println("Saldo Atual: " + conta2.saldo);
    }
}
```

---

## 🚀 Como Executar o Projeto

### Pré-requisitos
* Ter o [JDK (Java Development Kit)](https://oracle.com) instalado (versão 8 ou superior).

### Executando a Calculadora
1. Abra o terminal na pasta do projeto.
2. Compile o arquivo: `javac Calculadora.java`
3. Execute o programa: `java Calculadora`

### Executando o Sistema Bancário
1. Abra o terminal na pasta do projeto.
2. Compile os arquivos juntos: `javac ContaBancaria.java Main.java`
3. Execute a classe principal: `java Main`

---

## 📝 Conceitos Praticados

* Entrada de dados dinâmica com `java.util.Scanner`.
* Controle de fluxo com `switch-case` e estruturas condicionais (`if-else`).
* Abstração de classes, atributos e métodos.
* Instanciação de múltiplos objetos independentes na memória.
