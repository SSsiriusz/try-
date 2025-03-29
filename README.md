# try-
import java.util.Scanner;

public class DivisaoPorZero {
    public static void main(String[] args) {
        
        Scanner scanner = new Scanner(System.in);

       
        System.out.print("Digite o primeiro número: ");
        int num1 = scanner.nextInt();

        
        System.out.print("Digite o segundo número: ");
        int num2 = scanner.nextInt();

        try {
           
            int resultado = num1 / num2;
            System.out.println("Resultado da divisão: " + resultado);
        } catch (ArithmeticException e) {
            
            System.out.println("Erro: Não é possível dividir por zero.");
        } finally {
            
            scanner.close();
        }
    }
}
-------------------------------------------------------------------------------

import java.util.Scanner;

public class ConversaoDeStringParaNumero {
    public static void main(String[] args) {
        
        Scanner scanner = new Scanner(System.in);

        
        System.out.print("Digite um número: ");
        String entrada = scanner.nextLine();

        try {
            
            int numero = Integer.parseInt(entrada);
            System.out.println("Número digitado: " + numero);
        } catch (NumberFormatException e) {
            
            System.out.println("Erro: O valor inserido não é um número válido.");
        } finally {
            
            scanner.close();
        }
    }
}

--------------------------------------------------------------------------------

import java.util.Scanner;

public class RaizQuadradaDeNumero {
    public static void main(String[] args) {
        
        Scanner scanner = new Scanner(System.in);

        
        System.out.print("Digite um número: ");
        double numero = scanner.nextDouble();

        try {
           
            if (numero < 0) {
                throw new IllegalArgumentException("Não é possível calcular a raiz quadrada de um número negativo.");
            }

           
            double raizQuadrada = Math.sqrt(numero);
            System.out.println("A raiz quadrada de " + numero + " é: " + raizQuadrada);

        } catch (IllegalArgumentException e) {
           
            System.out.println("Erro: " + e.getMessage());
        } finally {
            
            scanner.close();
        }
    }
}

-----------------------------------------------------------------------------

import java.util.Scanner;
import java.util.InputMismatchException;

public class SomaDeDoisNumeros {
    public static void main(String[] args) {
        
        Scanner scanner = new Scanner(System.in);

        try {
            
            System.out.print("Digite o primeiro número: ");
            int num1 = scanner.nextInt();

            
            System.out.print("Digite o segundo número: ");
            int num2 = scanner.nextInt();

            
            int soma = num1 + num2;
            System.out.println("A soma dos dois números é: " + soma);

        } catch (InputMismatchException e) {
            
            System.out.println("Erro: Você deve inserir um número válido.");
        } finally {
            
            scanner.close();
        }
    }
}

----------------------------------------------------------------------------------

import java.util.Scanner;

public class AcessoIndiceInvalido {
    public static void main(String[] args) {
        int[] numeros = {10, 20, 30, 40, 50};

        
        Scanner scanner = new Scanner(System.in);

        try {
            System.out.print("Digite o índice do elemento que deseja acessar: ");
            int indice = scanner.nextInt();

           
            System.out.println("Elemento no índice " + indice + ": " + numeros[indice]);

        } catch (ArrayIndexOutOfBoundsException e) {
            
            System.out.println("Erro: Índice fora dos limites do array.");
        } finally {
            scanner.close();
        }
    }
}

--------------------------------------------------------------------------

import java.util.Scanner;

class DadosInvalidosException extends Exception {
    public DadosInvalidosException(String message) {
        super(message);
    }
}

public class CadastroUsuario {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        try {
            System.out.print("Digite seu nome: ");
            String nome = scanner.nextLine();

            System.out.print("Digite sua idade: ");
            int idade = scanner.nextInt();

            
            if (nome.isEmpty() || idade < 0) {
                throw new DadosInvalidosException("Nome não pode ser vazio e idade não pode ser negativa.");
            }

            System.out.println("Cadastro realizado com sucesso!");

        } catch (DadosInvalidosException e) {
            System.out.println("Erro: " + e.getMessage());
        } finally {
            scanner.close();
        }
    }
}
------------------------------------------------------------------------------

import java.util.Scanner;
import java.util.InputMismatchException;

public class CalculadoraDeMedia {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        try {
            System.out.print("Digite a primeira nota: ");
            double nota1 = scanner.nextDouble();

            System.out.print("Digite a segunda nota: ");
            double nota2 = scanner.nextDouble();

            System.out.print("Digite a terceira nota: ");
            double nota3 = scanner.nextDouble();

            double media = (nota1 + nota2 + nota3) / 3;
            System.out.println("A média das notas é: " + media);

        } catch (InputMismatchException e) {
            System.out.println("Erro: Você deve inserir um número válido.");
        } finally {
            scanner.close();
        }
    }
}
-----------------------------------------------------------------------------------

import java.util.Scanner;

class IdadeInvalidaException extends Exception {
    public IdadeInvalidaException(String message) {
        super(message);
    }
}

public class VerificacaoIdade {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        try {
            System.out.print("Digite sua idade: ");
            int idade = scanner.nextInt();

            if (idade < 0) {
                throw new IdadeInvalidaException("Idade não pode ser negativa.");
            }

            if (idade >= 18) {
                System.out.println("Você é maior de idade.");
            } else {
                System.out.println("Você é menor de idade.");
            }

        } catch (IdadeInvalidaException e) {
            System.out.println("Erro: " + e.getMessage());
        } finally {
            scanner.close();
        }
    }
}

__________________________________________________________________________________________

import java.util.Scanner;
import java.util.InputMismatchException;

class TemperaturaInvalidaException extends Exception {
    public TemperaturaInvalidaException(String message) {
        super(message);
    }
}

public class ConversaoTemperatura {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        try {
            System.out.print("Digite a temperatura em Celsius: ");
            double celsius = scanner.nextDouble();

            // Verificando o zero absoluto
            if (celsius < -273.15) {
                throw new TemperaturaInvalidaException("Temperatura abaixo do zero absoluto.");
            }

            double fahrenheit = (celsius * 9 / 5) + 32;
            System.out.println("Temperatura em Fahrenheit: " + fahrenheit);

        } catch (TemperaturaInvalidaException e) {
            System.out.println("Erro: " + e.getMessage());
        } catch (InputMismatchException e) {
            System.out.println("Erro: Você deve inserir um número válido.");
        } finally {
            scanner.close();
        }
    }
}


import java.util.Scanner;

class NumeroNegativoException extends Exception {
    public NumeroNegativoException(String message) {
        super(message);
    }
}

class LimiteFatorialExcedidoException extends Exception {
    public LimiteFatorialExcedidoException(String message) {
        super(message);
    }
}

public class CalculadoraFatorial {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        try {
            System.out.print("Digite um número para calcular o fatorial: ");
            int numero = scanner.nextInt();

            if (numero < 0) {
                throw new NumeroNegativoException("Número não pode ser negativo.");
            }

            if (numero > 20) {
                throw new LimiteFatorialExcedidoException("Número não pode ser maior que 20 devido ao limite de recursão.");
            }

            long fatorial = calcularFatorial(numero);
            System.out.println("O fatorial de " + numero + " é: " + fatorial);

        } catch (NumeroNegativoException | LimiteFatorialExcedidoException e) {
            System.out.println("Erro: " + e.getMessage());
        } finally {
            scanner.close();
        }
    }

    public static long calcularFatorial(int n) {
        if (n == 0 || n == 1) {
            return 1;
        }
        return n * calcularFatorial(n - 1);
    }
}



