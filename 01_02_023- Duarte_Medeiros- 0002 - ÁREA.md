## 1. Proposições

### 1.1 Termos e Proposições

As expressões utilizadas pela linguagem matemática formal são semelhantes às expressões utilizadas na linguagem corrente. No entanto, a sua interpretação e análise podem ser diferentes. Na linguagem matemática é utilizado essencialmente dois tipos de expressões: termos e proposições.


#### Definição 1.1.1
Termos é uma expressão que designa um objeto.


Alguns exemplos de expressões:
“$\pi$”
“O número real cujo dobro é 10.”


#### Definição 1.1.2
Proposição é uma expressão à qual se pode atribuir um valor lógico “Verdadeiro” ou “Falso” que pode ser representação por V e F, respetivamente.


Alguns exemplos de proposições:
“$\pi$ é um número irracional.”
“4 é o número real cujo dobro é 10.”

No estudo da lógica proposicional admitem-se os seguintes princípios:


#### Princípio do Terceiro Excluído
Uma proposição ou é verdadeira ou a sua negação é verdadeira, isto é, verifica-se sempre um destes casos e nunca um terceiro.

#### Princípio de Não Contradição
Uma proposição não pode ser simultaneamente verdadeira e falsa.


#### Definição 1.1.3 Equivalência de Proposições
Duas proposições, $p$ e $q$, dizem-se equivalentes se tiverem o mesmo valor lógico. Representa-se $p \Leftrightarrow q$ para afirmar que $p$ e $q$ são equivalentes.


### 1.2 Operações e propriedades sobre proposições

A parir de proposições mais simples, utilizando operações que designamos por operações lógicas conseguimos criar raciocínios que podem assumir qualquer valor lógico.


#### Definição 1.2.1 Negação
Dada uma proposição $p$, não $p$ é uma nova proposição com valor lógico e representamos por $~p$.

Tabela de Verdade:



Assim pela tabela de verdade:

$\sim V \Leftrightarrow F$

$\sim F \Leftrightarrow V$


Exemplo:

$p$: “A Matemática é uma ciência.”

$sim p$: ”A Matemática não é uma ciência.”



#### Definição 1.2.2 Lei da dupla negação
Dada proposição $p$, tem-se que:
$\sim(\sim p) \Leftrightarrow p$


Tabela de Verdade:


Assim pela tabela de verdade:


$\sim (\sim V) \Leftrightarrow V$

$\sim (\sim F) \Leftrightarrow F$


Exemplo:

$p$: “11 é um número primo.”

$~p$: 11 não é um número primo.”

$\sim (\sim p)$: “Não é verdade que 11 não é um número primo.”


####Definição 1.2.3 Conjunção
Dadas duas proposições $p$ e $q$, a conjunção de $p$ e $q$ é uma nova proposição que é verdadeira se e somente se $p$ e $q$ forem simultaneamente verdadeiras. A nova proposição representa-se por $p \wedge q$ e lê-se “$p$ e $q$”.

Tabela de Verdade:


Assim pela tabela de verdade:

V $\wedge$ V $\Leftrightarrow$ V
V $\wedge$ F $\Leftrightarrow$ F
F $\wedge$ V $\Leftrightarrow$ F
F $\wedge$ F $\Leftrightarrow$ F


Exemplo:

$p$: “Chanel foi um importante matemático.”

$q$: “Picasso foi um importante matemático.”

$p \wedge q$: “Chanel e Picasso foram ambos importantes matemáticos.”

 Como as duas proposições são falsas, a conjunção das duas também é falsa.


####Definição 1.2.4 Disjunção
Dadas duas proposições $p$ e $q$, a disjunção de $p$ e $q$ é uma nova proposição que é falsa se e somente se $p$ e $q$ forem simultaneamente falsas. A nova proposição representa-se por $p \vee q$ e lê-se “$p$ ou $q$”.


Assim pela tabela de verdade:

V $\vee$ V $\Leftrightarrow$ V
V $\vee$ F $\Leftrightarrow$ V
F $\vee$ V $\Leftrightarrow$ V
F $\vee$ F $\Leftrightarrow$ F

Exemplo:

$p$: “4 ´é um número par.”

$q$: “4 é um número primo.”

$p \vee q$: “4 é um número par ou 4 é um número primo”

 Como as uma das proposições é verdadeira, a disjunção das duas também é verdadeira.

Na linguagem corrente e num contexto não matemático a palavra “ou” pode ter outro significado. Quando por exemplo temos de escolher um, dos dois filmes para ver no cinema. Não podemos ver os dois, mas também podemos não ir a nenhum. A este tipo de disjunção chamamos de disjunção exclusiva. Este tipo de disjunção é menos utilizado num contexto matemático, pelo que quando se refere disjunção é a disjunção definida acima.