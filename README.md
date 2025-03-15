
# 💻 Lista de Exercícios – Concatenação e StringBuilder em Java

Esta lista contém **10 exemplos** para praticar concatenação de strings em Java, utilizando tanto o operador `+` quanto a classe `StringBuilder`.  

---

## 1️⃣ Concatenação Simples de Nomes
**Enunciado:**  
Crie um programa que concatene três strings representando **nome, sobrenome e um sufixo opcional**, como "Jr." ou "Filho". Caso o sufixo seja uma string vazia, ele não deve ser incluído no nome final.  

```java
public class ConcatenaNome {
    public static void main(String[] args) {
        String nome = "João";
        String sobrenome = "Silva";
        String sufixo = "Jr."; // Teste com "" para ver o outro caso

        String nomeCompleto = nome + " " + sobrenome + (sufixo.isEmpty() ? "" : " " + sufixo);
        System.out.println("Nome completo: " + nomeCompleto);
    }
}
```

---

## 2️⃣ Comparação de Performance: String vs StringBuilder
**Enunciado:**  
Implemente um programa que concatene a string `"Teste"` **100.000 vezes** e meça o tempo de execução, comparando o uso de `String` e `StringBuilder`.  

```java
public class PerformanceConcat {
    public static void main(String[] args) {
        int repeticoes = 100000;
        
        // Usando String (+)
        long inicio = System.nanoTime();
        String texto = "";
        for (int i = 0; i < repeticoes; i++) {
            texto += "Teste";
        }
        long fim = System.nanoTime();
        System.out.println("Tempo com String: " + (fim - inicio) + " ns");
        
        // Usando StringBuilder
        inicio = System.nanoTime();
        StringBuilder sb = new StringBuilder();
        for (int i = 0; i < repeticoes; i++) {
            sb.append("Teste");
        }
        fim = System.nanoTime();
        System.out.println("Tempo com StringBuilder: " + (fim - inicio) + " ns");
    }
}
```

---

## 3️⃣ Geração de Frase com Números
**Enunciado:**  
Escreva um programa que gere a string `"Número 1, Número 2, Número 3, ..."`, indo até o número **20**. Use `StringBuilder`.  

```java
public class NumerosConcatenacao {
    public static void main(String[] args) {
        StringBuilder sb = new StringBuilder();
        for (int i = 1; i <= 20; i++) {
            sb.append("Número ").append(i);
            if (i < 20) sb.append(", ");
        }
        System.out.println(sb.toString());
    }
}
```

---

## 4️⃣ Inversão de String
**Enunciado:**  
Crie um programa que use `StringBuilder` para inverter uma string digitada pelo usuário.  

```java
import java.util.Scanner;

public class InverterString {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.print("Digite uma palavra: ");
        String palavra = sc.nextLine();

        StringBuilder sb = new StringBuilder(palavra);
        System.out.println("Invertida: " + sb.reverse().toString());
        sc.close();
    }
}
```

---

## 5️⃣ Montagem de URL com Parâmetros
**Enunciado:**  
Escreva um programa que monte uma URL dinâmica baseada em três variáveis: `site`, `pagina`, e `id`.  

```java
public class MontaURL {
    public static void main(String[] args) {
        String site = "https://meusite.com";
        String pagina = "produto";
        int id = 123;

        String url = site + "/" + pagina + "?id=" + id;
        System.out.println("URL gerada: " + url);
    }
}
```

---

## 6️⃣ Repetição de String
**Enunciado:**  
Crie um programa que receba um número `N` e repita `"Java "` `N` vezes em uma única string.  

```java
public class RepetirString {
    public static void main(String[] args) {
        int n = 10;
        StringBuilder sb = new StringBuilder();
        for (int i = 0; i < n; i++) {
            sb.append("Java ");
        }
        System.out.println(sb.toString());
    }
}
```

---

## 7️⃣ Formatação de Lista de Compras
**Enunciado:**  
Dada uma lista de compras, concatene os itens em uma string única, separando por vírgulas.  

```java
public class ListaCompras {
    public static void main(String[] args) {
        String[] itens = {"Pão", "Leite", "Café", "Açúcar"};
        StringBuilder sb = new StringBuilder();
        
        for (int i = 0; i < itens.length; i++) {
            sb.append(itens[i]);
            if (i < itens.length - 1) sb.append(", ");
        }
        
        System.out.println("Lista de compras: " + sb.toString());
    }
}
```

---

## 8️⃣ Substituição de Palavra em um Texto
**Enunciado:**  
Escreva um programa que substitua todas as ocorrências da palavra `"erro"` por `"correção"` dentro de uma string.  

```java
public class SubstituirPalavra {
    public static void main(String[] args) {
        String texto = "O código tem um erro grave. O erro precisa ser corrigido.";
        String novoTexto = texto.replace("erro", "correção");
        System.out.println(novoTexto);
    }
}
```

---

## 9️⃣ Extração de Nome do E-mail
**Enunciado:**  
Dado um e-mail no formato `usuario@email.com`, extraia apenas o nome do usuário.  

```java
public class ExtraiUsuarioEmail {
    public static void main(String[] args) {
        String email = "marcelo@gmail.com";
        String usuario = email.split("@")[0];
        System.out.println("Usuário: " + usuario);
    }
}
```

---

## 🔟 Remoção de Espaços Extras
**Enunciado:**  
Crie um programa que remova espaços extras no início e fim de uma string e substitua espaços múltiplos dentro da string por um único espaço.  

```java
public class RemoverEspacos {
    public static void main(String[] args) {
        String frase = "   Java   é   incrível!    ";
        String fraseLimpa = frase.trim().replaceAll("\\s+", " ");
        System.out.println("Frase corrigida: '" + fraseLimpa + "'");
    }
}
```

---

## 📌 O que esses exercícios abordam?
✅ Concatenação com `+` e `StringBuilder`  
✅ Comparação de performance  
✅ Substituições e manipulações de texto  
✅ Extração e formatação de dados  

🚀 **Agora é sua vez! Teste os códigos, analise o tempo de processamento. Pratique e melhore suas habilidades com manipulação de strings em Java!**
