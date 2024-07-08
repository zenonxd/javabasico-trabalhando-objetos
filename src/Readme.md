# Trabalhando com Objetos

## Orientação à Objeto (OO)

Ao invés de colocarmos a lógica de tudo dentro do Main ou em uma função como na **estrutura procedural**: 
![img.png](img.png)

Nós criaremos um objeto
para que ele esteja encarregado de fazer as operações necessárias. Onde somente iremos chamar ele 
dentro do Main depois.

![img_1.png](img_1.png)

Se temos uma calculadora, por exemplo, criamos um objeto Calculadora e dentro dele terá os métodos de 
operação.

**Em suma, mover dados, métodos, comportamentos para dentro de um objetos específicos.**

## Vantagens da OO

Fazendo isso, teremos uma estrutura mais clara, boa legibilidade do código, podemos fazer reuso dos métodos
e tudo terá uma boa coesão.

![img_2.png](img_2.png)

## Classes

Classes representam conceitos, coisas do mundo real: Usuário, Produto, Compra, Carrinho, Calculdora...

### Qual a relação entre classes e objetos?

Bom, classe em suma é o manual que a gente usa (JVM) para criar os objetos.

Por exemplo, uma Classe específica pode ser uma planta de uma casa. E com essa planta, construiremos VÁRIAS
casas. E as casas, neste contexto, são os objetos.

![img_3.png](img_3.png)

## Atributos
### O que a Classe possui? Qual sua estrutura? O que ela pode fazer?

Classes possuem atributos, ou seja, características dela. Já que estamos no conceito de Planta/Casa...
Uma casa pode ter uma sala, quarto, cozinha ou banheiro. Isso são características dela (atributos).

![img_4.png](img_4.png)

Numa classe **Compra**, por exemplo, que tipo de atributos poderiamos ter? Poderiamos ter atributos de nome do
produto, valor, quantidade e por aí vai.

![img_5.png](img_5.png)

Já um **Usuário**, pode ter um username, email e password.

![img_6.png](img_6.png)
<hr>

## Métodos
### Ok, e como definimos o que essa Classe irá fazer?

Métodos são operações, funções. Ainda no exemplo de casa, uma casa terá que acender a luz, trancar a porta,
ativar alarme.... isso serão métodos dentro da Classe.

![img_7.png](img_7.png)

Uma Casa, por exemplo, pode ser uma casa inteligente, com comandos de voz. Podemos criar um atributo boolean
para identificar isso dentro de um método.
```java
public class Casa {
    boolean inteligente;
    
    void ascenderLuz() {
        if (inteligente) {
            System.out.println("Comando de Voz.");
        }
        else {
            System.out.println("Usar interruptor.");
        }
    }
}
```

Os métodos podem retornar qualquer coisa. Se fosse um "int" ao invés de void acima, teriamos que colocar
para ele retornar um inteiro no final da função.

Além disso, dentro dos (), podemos passar parâmetros para o método ler. Exemplo, podemos colocar qual parte
da casa ele irá acender a luz colocando (int comodo).
<hr>

## Construtores Padrão
### Como usar esse Objeto/Classe?

Construtores são usados para criar objetos e executálos. **As classes serão instanciadas no método Main**.

![img_8.png](img_8.png)

Ok, nós instanciamos. E para construir esse objeto? Passaremos um "= new Casa()"

![img_9.png](img_9.png)

**Todas as classes possuem ao menos um construtor padrão sem argumentos (parâmetros).**

A partir desse momento, nós podemos acessar os métodos dessa classe, chamando a variável e passando um "."

![img_10.png](img_10.png)
<hr>

## Construtores com Parâmetros

Dentro da classe Casa, nós criaremos um construtor com argumentos. Podemos selecionar quais queremos que
estejam ali dentro. Ou seja, se temos 4 atributos, podemos colocar só 3 se desejarmos.

![img_11.png](img_11.png)

**Isso é importante:** Que fique claro, o (boolean inteligente) é somente um parâmetro do construtor.
Para atribuirmos o valor desse parâmetro, para o atributo inicial da nossa clase, usamos o **this.**

O this irá falar com o objeto que estamos (Casa), o "." é o acesso, onde neste caso, acessamos o atributo
inteligente e atualizamos o valor dele, para o do parâmetro.

Ao voltarmos para o Main, podemos dessa vez, passar parâmetros dentro da instanciação da classe:

![img_12.png](img_12.png)

Lembrar que, ao criamos um construtor com argumentos, não será possível iniciar no Main um objeto sem 
parâmetros. Para que seja possível, precisamos criar dentro do nosso Objeto, um construtor padrão
sem argumentos, vazio mesmo.

![img_13.png](img_13.png)
<hr>

## Valores Padrão de Atributos

Os atributos nos objetos são inicializados com valores default. Um boolean por exemplo, sempre irá 
iniciar **false**, uma String **null** e por aí vai.

Então a ideia é a partir de agora, a gente inicializar esses atributos. Declarou no objeto? Informe
os valores.
<hr>

## Pacotes

Nesse exemplo do estudo aqui, estamos usando conceito de Casa. Podemos criar pacotes específicos para tais
coisas, como: Pacote chamado Moradias, onde terá: Casa, Apartamento, Trailer...

![img_15.png](img_15.png)

Cada "." é uma divisão ou "/", de pasta. br/com/giulianabezerra/moradias/Casa.java
<hr>

## Importando Pacotes

Se colocamos um objeto dentro de um pacote específico precisamos passar isso ao main (importar ele), pois
o Main está alocado no Default.

![img_14.png](img_14.png)
<hr>

## Membros Públicos

Nota-se que quando criamos os nossos atributos, não declaremos o tipo deles (public/private). Se não há nenhuma
declaração, não é possível acessá-los de outras Classes.

Public - Qualquer pessoa/classe pode acessar, torna a classe visível para quem está fora do pacote.
Então agora, os métodos e atributos serão public, podendo ser acessados.

![img_16.png](img_16.png)
<hr>

## Tipos de Referência

Nós temos alguns tipos de variáveis:

![img_17.png](img_17.png)

Qual referência é armazenada?

![img_18.png](img_18.png)

### Ok, qual a diferença de Primitivo vs Referência?
Bom, eles possuem estados e comportamentos definidos por classes.

Os primitivos só irão guardar valores.

![img_19.png](img_19.png)

Já referência, podemos ter vários atributos e métodos associados a este valor.

![img_21.png](img_21.png)

### Detalhando isso
Vamos pensar numa **Classe Café**.

![img_22.png](img_22.png)

Como criamos essa classe, podemos instanciar ela agora.

![img_23.png](img_23.png)

Mas como não foi atribuído nenhum valor, será inicialmente null. Não terá nenhuma referência, nenhum
espaço na JVM.

Então iremos para o passo 3:

![img_24.png](img_24.png)