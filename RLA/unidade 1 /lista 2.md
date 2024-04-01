
# UNIFOR
**Nome**: Silvio de azevedo rocha filho <br>
**Disciplina**: Raciocínio Lógico Algorítmo

## Exercício exemplo
Represente, em fluxograma e pseudocódigo, um algoritmo para calcular o adicional de salário de funcionário por cargo de uma empresa fictícia. Sabe-se que os funcionários de cargo técnico receberão reajuste de 50%, cargo de gerência, um reajuste de 30% e demais, um reajuste de 10%. 

#### Fluxograma
```mermaid
flowchart TD
A([INICIO]) --> B{{Digite o salário e profissão}}
B --> C[\sal, prof\]
C --> D{prof == 'Tecnico'}
D --FALSE--> E{prof == 'Gerente'}
D --TRUE--> F[sal_reaj = 1.5 * sal]
E --FALSE--> H[sal_reaj = 1.1 * sal]
E --TRUE--> G[sal_reaj = 1.3 * sal]
G --> I([FIM])
F --> I
H --> J{{'Salário Reajustado = ', sal_reaj}}
J --> I
```

#### Pseudocódigo
```
1  ALGORITMO calReajuste
2  DECLARE  sal, sal_reaj: real, prof: caractere    // declarando inicialmente o salario atual e a profissão exercida, sendo variaveis!
3  INICIO
4  LEIA sal, prof      // comando responsavel para salvar a informação do passo anterior 
5  ESCOLHA
6   CASO prof == “Técnico”		// caso 1
7     sal_reaj ← 1.5 * sal                          // se a pessoa exercer a profissao de tecnico seu salario atual sera mutipplicado por 1.5 para obter o reajuste 
8   CASO prof = “Gerente”		// caso 2
9     sal_reaj ← 1.3 * sal                          // se a  profissao exercida for gerente ser salario atual sera reajustado sendo multiplicado por 1.3 
10  SENÃO
11    sal_reaj ← 1.1 * sal                          // caso a profissao n se enquadre em nenhuma das duas opções anteriores o salario sera multiplicado por 1.1 para ser reajustado
12 FIM_ESCOLHA
13 ESCREVA “Salário Reajustado = “, sal_reaj        // o salario reajustado sera dado na tela e fim do algoritmo
14 FIM
```

#### Teste
| sal | prof | prof == “Técnico” | prof = “Gerente” | sal_reaj | Saída |
| -- | -- | -- | -- | -- | -- |
| 1000 | Técnico | V | F | 1500 | “Salário Reajustado = 1500“ |
| 2000 | Gerente | F | V | 2600 | “Salário Reajustado = 2600“ |
| 9000 | Diretor | F | F | 9900 | “Salário Reajustado = 9900“ |

## Lista de exercícios 02

### Exercício 01 (2.5 pontos)
Calcule a média de quatro números inteiros dados.

#### Fluxograma (1.0 ponto)

```mermaid
flowchart TD
A([INICIO]) --> B{{Digite o seu primeiro numero}}
B --> C[/N1/]
C --> D{{Digite o seu segundo número}}
D --> E[/N2/]
E --> F{{Digite o seu terceiro número}}
F --> G[/N3/]
G --> H{{Digite o seu ultimo número}}
H --> I[/N4/]
I --> J["Med = (N1 + N2 + N3 + N4)/4"]
J --> K{{A média entre os números dados é Med}}
K --> L([FIM])
```

#### Pseudocódigo (1.0 ponto)

```
Algoritmo Media
DECLARE N1, N2, N3, N4: int      // declarando inicialmente as 4 variaveis N sendo numeros inteiros e positivos 
	Med: float
INICIO
ESCREVA "Digite o seu primeiro número"      
LEIA N1            // lendo a escolha da primeira nota N1 para que seja guardada a informação no sistema
ESCREVA "Digite o seu segundo número"
LEIA N2
ESCREVA "Digite o seu terceiro número"
LEIA N3
ESCREVA "Digite o seu ultimo número"
LEIA N4
Med = (N1 + N2 + N3 + N4)/4           // depois das 4 variaveis escolhidas deve somar as 4 notas e dividir o resultado por 4, para se obter a media  
ESCREVA "A média dos números dados é", Med       // resultante da conta anterior sera o valor da media obtida 
FIM_ALGORITMO
```

#### Teste de mesa (0.5 ponto)

|N1|N2|N3|N4|Med = (N1 + N2 + N3 + N4)/4|Saída| 
|--|--|--|--|--|--|
|10|8|20|6|11|A média dos números dados é Med|


### Exercício 02 (2.5 pontos)
Leia uma temperatura dada em Celsius (C) e imprima o equivalente em Fahrenheit (F). (Fórmula de conversão: F = (9/5) * C + 32)

#### Fluxograma (1.0 ponto)

```mermaid
flowchart TD
A([INICIO]) --> B{{Digite a temperatura em graus celcius}}
B --> C[/Ce/]
C --> D["Fa = (9/5) * Ce + 32"]
D --> E{{A temperatura covertida para graus fahrenheit é Fa}}
E --> F([FIM])
```

#### Pseudocódigo (1.0 ponto)

```
Algoritmo ConverteCelsiusFarenheit
DECLARE Ce, Fe: float    // declare inicialmente a temperutada desejada em celcius para ser transformada em fahrenheit
INICIO
ESCREVA "Digite a temperatura em graus celcius"      // depois de declarada a temperatura escreva no espaço pedido
LEIA Ce                   // leia a temperatura em celcius para guardar a informaçao no sistema 
Fa = (9/5) * Ce + 32      // para a temperatuda em celcius ser transformada em fahrenheit deve ser multiplicada por 9/5 e ser adicionado 32 ao resultado!
ESCREVA "A temperatura covertida para graus fahrenheit é", Fa     // tendo a temperatura convertida escreva o valor obtido para entregar a respota!
FIM_ALGORITMO
```

#### Teste de mesa (0.5 ponto)

|Ce|Fa = (9/5) * Ce + 32|Saída|
|--|--|--| 
|0|32|A temperatura covertida para graus fahrenheit é 32|

### Exercício 03 (2.5 pontos)
Receba dois números reais e um operador e efetue a operação correspondente com os valores recebidos (operandos). 
O algoritmo deve retornar o resultado da operação selecionada simulando todas as operações de uma calculadora simples.

#### Fluxograma (1.0 ponto)

```mermaid
flowchart TD
A([START]) --> B{{Intruções da calculadora: 1 = adição, 2 = subtração, 3 = multiplição, 4 = divisão}}
B-->C{{Digite o primeiro número da expressão}}
C-->D[/N1/]
D-->E{{Digite o operando com base nas intruções}}
E-->F[/Op/]
F-->G{Op >= 1 and Op <= 7}
G--FALSE-->H{{O número do operando precisa ser maior que um e menor que sete}}
H-->B
G--TRUE-->I{{Digite o segundo número da expressão}}
I-->J[/N2/]
J-->K{Op == 1}
K--FALSE-->L{Op == 2}
K--TRUE-->k(N1 + N2 = Rs)
k-->R
L--FALSE-->M{Op == 3}
L--TRUE-->l(N1 - N2 = Rs)
l-->R
M--FALSE-->N{Op == 4}
M--TRUE-->m(N1 * N2 = Rs)
m-->R
N--FALSE-->O{Op == 5}
N--TRUE-->n{N2 == 0}
n--FALSE-->n2(N1 / N2 = Rs)
n--TRUE-->n3{{ERROR: Impossívem dividir por zero}}
n2-->R
n3-->B
O--FALSE-->P{Op == 6}
O--TRUE-->o(N1 // N2 = Rs)
o-->R
P--FALSE-->q
P--TRUE-->p(N1 % N2 = Rs)
p-->R
q(N1 ** N2 = Rs)
q-->R{{O seu resultado foi Rs}}
R-->Z([END])
```

#### Pseudocódigo (1.0 ponto)

```
 Algoritimo Calculadora
 DECLARE N1,N2,Rs: float     declare inicialmente n1 e n2 sendo numeros inteiros 
	 Op: int
 INICIO
 ESCREVA "Intruções da calculadora: 1 = adição, 2 = subtração, 3 = multiplição, 4              
	  = divisão, 5 = divisão inteira, 6 = resto da divisão, 7 = exponenciação/radicação"     // escreva as instruções de uma calculadora comum 
 ESCREVA "Digite o primeiro número da expressão"
 LEIA N1           // escreva n1 como variavel inicial da expressão e leia para guardar a informação 
 ESCREVA "Digite o operando com base nas intruções"        // escreva o nummero da operação que deseja realizar de 1 a 7
 LEIA Op
 SE Op >= 1 e Op <= 7           // se o numero de escolha de expressão n estiver entre 1 e 7 sera pedido um numero valido
	ESCREVA "Digite o segundo número da expressão"    // apos escolher o primeiro numero n1 da expressao e qual expressão sera executada escolha a variavel n2 
	LEIA N2
	ESCOLHA
		CASO Op =  1         // caso de expressao 1 em que é executada uma soma das variaveis escolhidas 
			Rs = N1 + N2
		CASO Op =  2        // caso de expressão 2 em que é executada a subtração das variaveis declaradas
			Rs = N1 - N2
		CASO Op = 3        // caso de expressão 3 em que é executada a multiplicação das variaveis declaradas 
			Rs = N1 * N2
		CASO Op = 4       //  caso de expressão 4 em que é executada a divisão entre as variaveis declaradas sendo numeros inteiros 
		        ENQUANTO N2 == 0 FAÇA    // enquanto a variavel n2 for 0 devera trocar a variavel por um nunmero valido 
				ESCREVA "ERROR: impossível dividir por zero, digite um novo denominador"
				LEIA N2
			FIM_ENQUANTO
	FIM_ESCOLHA 
ESCREVA "O seu resultado foi", Rs     // escreva o resultado da operação feita pela calculadora 
FIM_ALGORÍTIMO
```

#### Teste de mesa (0.5 ponto)

|N1|Op|N2|Op == 1|Op == 2|Op == 3|Op == 4|N2 == 0|Op == 5|N2 == 0|Op == 6|Rs|Saída| 
|--|--|--|--|--|--|--|--|--|--|--|--|--|
|8|1|10|V|-|-|-|-|-|-|-|18|O seu resultado foi 18|
|20|2|20|F|V|-|-|-|-|-|-|0|O seu resultado foi 0|
|87|3|0|F|F|V|-|-|-|-|-|0|O seu resultado foi 0|
|0.2|4|0.1|F|F|F|V|F|-|-|-|2|O seu resultado foi 2|
|120|4|0|F|F|F|V|V|-|-|-|-|ERROR: impossível dividir por zero, digite um novo denominador|
|25|5|7|F|F|F|F|-|V|F|-|3|O seu resultado foi 3|
|37|5|0|F|F|F|F|-|V|V|-|-|ERROR: impossível dividir por zero, digite um novo denominador|
|31|6|2|F|F|F|F|-|F|-|V|1|O seu resultado é 1|
|2|7|5|F|F|F|F|-|F|-|F|32|O seu resultado é 32|


### Exercício 04 (2.5 pontos)
Elaborar um algoritmo que, dada a idade, classifique nas categorias: infantil A (5 - 7 anos), infantil B (8 -10 anos), juvenil A (11 - 13 anos), juvenil B (14 -17 anos) e adulto (maiores que 18 anos).

#### Fluxograma (1.0 ponto)

```mermaid
flowchart TD
A([INICIO]) --> B{{Digite a idade}}
B --> C[/Id/]
C --> D{Id < 5}
D --FALSE--> E{{Digite uma idade válida}}
E --> C
D --TRUE--> F{Id >= 5 e Id =<7}
F --FALSE--> G{Id >= 8 e Id <=10}
G --FALSE--> H{Id >= 11 e Id <= 13}
H --FALSE--> I{Id >= 14 e Id <= 18}
F --TRUE--> J{{Infantil A}}
G --TRUE--> K{{Infantil B}}
H --TRUE--> L{{Juvenil A}}
I --TRUE--> M{{Juvenil B}}
I --FALSE--> N{{Adulto}}
J --> Z([FIM])
K --> Z
L --> Z
M --> Z
N --> Z
```

#### Pseudocódigo (1.0 ponto)
```
Algoritmo ClassificaCategoria
DECLARE Id: int    // declare inicialmente a idade da pessoa , sendo um numero inteiro 
INICIO
ESCREVA "Digite a idade"    // espaço para digitar a idade
LEIA Id              // leia a idade para guardar a informação 
ENQUANTO Id < 5 FAÇA    
	ESCREVA "Digite uma idade válida"      // enquanto a idade for menor que 5 sera negada e pedida para digitar uma idade valida
	LEIA Id
ESCOLHA  
	CASO Id >= 5 e Id <= 7       // se a idade declarada for entre 5 e 7, sera enquadrado no grupo infantil A
		ESCREVA "Infantil A"
	CASO Id >= 8 e Id <=10      //se a idade declarada for entre 8 e 10, sera enquadrada no grupo infantil B
		ESCREVA "Infantil B"
	CASO Id >= 11 e Id <= 13    //se a idaede declarada for entre 11 e 13, sera enquadrada no grupo juvenil A
		ESCREVA "juvenil A"
	CASO Id >= 14 e Id <= 17    // se a idade declarada for entre 14 e 17, sera enquadrada no grupo Juvenil B
		ESCREVA "Juvenil B"
SENAO     // se nenhum dos grupos for incluidos pela a idade declarada significa q a idade declarada foi >= 18, então se enquadra no grupo Adulto
	ESCREVA "Adulto"
FIM_ESCOLHA 
FIM_ALGORITMO
```

#### Teste de mesa (0.5 ponto)


|Id|Id < 5|Id >= 5 e Id <= 7|Id >= 8 e Id <= 10|Id >= 11 e Id <= 13|Id >= 14 e Id <= 17|Saida|
|--|--|--|--|--|--|--|
|-5|V|-|-|-|-|Digite uma idade valida|
|5|F| V|-|-|-|Infantil A|
|9|F| F|V|-|-|Infantil B|
|11|F|F|F|V|-|Juvenil A|
|17|F|F|F|F|V|Juvenil B|
|24|F|F|F|F|F|Adulto|
