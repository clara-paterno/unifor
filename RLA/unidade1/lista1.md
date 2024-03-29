# UNIFOR
**Nome**: Maria Clara Paterno Maia <br>
**Disciplina**: Raciocínio lógico algorítmico

## Lista de exercícios 01

### Exercício 01 (1 ponto)
Represente, em fluxograma e pseudocódigo, um algoritmo para determinar se um número inteiro e positivo é par ou impar.

#### Fluxograma (0,25 ponto)

```mermaid
flowchart TB
A([INÍCIO]) --> B{{Digite um número: }}
B --> C[/n/] 
C --> D{n>=0}
D --FALSE--> E{{O número deve ser positivo}}
E --> F((fim))
D --TRUE--> G[r= num % 2]
G--> H{r == 0}
H--FALSE-->I{{O número é ímpar}}
H--TRUE-->J{{O número é par}}
I-->F
J-->F
```

#### Pseudocódigo (0,5 ponto)
```
ALGORTIMO verifica_par_impar
DECLARE n, r: INTEIRO
INICIO
ESCREVA "Digite um número: "
LEIA n
SE numero >= 0 ENTAO                 
	r <- n % 2               
	SE r == 0 ENTAO              
		ESCREVA "O número é par!"
	SENAO
	    ESCREVA "O número é impar!"
	FIM_SE
SENAO                                
	ESCREVA "O número deve ser postivo!"
FIM_SE
FIM
```

#### Teste de mesa (0,25 ponto)
| n  | n >= 0 | r | r == 0 |             Saída            |
| -- |   --   | --|    --  |            --                | 
|-1  |    F   |   |        | "O número deve ser positivo" |
| 0  |    V   | 0 |    V   |        "O número é par"      |
| 13 |    V   | 1 |    F   |       "O número é impar"     |
| 30 |    V   | 0 |    V   |       "O número é par"       |


## Exercício 02 (3 pontos)
Represente, em fluxograma e pseudocódigo, um algoritmo para calcular o novo salário de um funcionário. 
Sabe-se que os funcionários que recebem atualmente salário de até R$ 500 terão aumento de 20%; os demais terão aumento de 10%.

#### Fluxograma (1.0 ponto)

```mermaid
flowchart TB
A([INÍCIO]) --> B{{Digite seu salário: }}
B --> C[/sal/]
C --> D{sal>500}
D --TRUE--> E[nsal = 1,10 * sal]
D --FALSE--> G[nsal = 1,20 * sal]
E-->F{{O novo salário é, nsal}}
G--> F
F-->H([FIM])
```

#### Pseudocódigo (1.0 ponto)

```
ALGORITMO salário
DECLARE sal, nsal: INTEIROS
INICIO
ESCREVA "Digite seu salário: "
LEIA sal
SE sal > 500 ENTAO	
	nsal <- 1,10*sal
SENAO
	nsal <- 1,20*sal
FIM_SE
LEIA nsal
	ESCREVA "Seu novo salário é, nsal". 
FIM
```

#### Teste de mesa (1.0 ponto)
| sal | salário>500 |   nsal   |          Saída          |
| --  |    --       |    --    |           --            | 
| 400 |      F      | 1,20*400 | "O novo salário é 480"  |
| 600 |      V      | 1,1*600  | "O novo salário é 660"  |
| 1000|      V      | 1,1*1000 | "O novo salário é 1100" |
| 490 |      F      | 1,2*490  | "O novo salário é 588"  |


## Exercício 03 (3 pontos)
Represente, em fluxograma e pseudocódigo, um algoritmo para calcular a média aritmética entre duas notas de um aluno e mostrar sua situação, que pode ser aprovado ou reprovado.

#### Fluxograma (1 ponto)

```mermaid
flowchart TB
A([INÍCIO]) --> B{{Digite as notas: }}
B --> D[/n1, n2/] 
D --> E[M=n1+n2/2]
E-->F{M>=6}
F--TRUE-->G{{Aprovado}}
F--FALSE-->H{{Reprovado}}
G-->I([FIM])
H-->I
```

#### Pseudocódigo (1 ponto)

```
ALGORITMO_média
DECLARE n1, n2, M: INTEIROS
INICIO
ESCREVA "Digite as notas: "
LEIA n1, n2
M=(n1+n2)/2
SE M>=6
	ESCREVA "Aprovado"
SENAO
	ESCREVA "Reprovado"
FIM_SE
FIM
```

#### Teste de mesa (1 ponto)
|  n1 |  n2  | média | M>=6 |   Saída    |
| --  |  --  |  --   |  -- |     --      | 
|  7  |  10  |  8,5  |  V  | "Aprovado"  |
|  8  |   6  |   7   |  V  | "Aprovado"  |
|  5  |   4  |  4,5  |  F  | "Reprovado" |
|  7  |   9  |   8   |  V  | "Aprovado"  |


## Exercício 04 (3 pontos)
Represente, em fluxograma e pseudocódigo, um algoritmo que, a partir da idade do candidato(a), determinar se pode ou não tirar a CNH. 
Caso não atender a restrição de idade, calcular quantos anos faltam para o candidato estar apto.

#### Fluxograma (1.0 ponto)

```mermaid
flowchart TB
A([INÍCIO]) --> B{{Digite a sua idade: }}
B --> C[/I/] 
C --> D{I>=18}
D--TRUE--> E{{Pode tirar a CNH}}
D --FALSE--> F[I2=18-I]
F --> G{{Pode tirar a CNH daqui a, I, anos}}
E--> I([FIM])
G --> I
```

#### Pseudocódigo (1.0 ponto)

```
ALGORTIMO verifica_idade
DECLARE I, I2: INTEIRO
INICIO
ESCREVA "Digite a sua idade: "
LEIA I
SE I>= 18 ENTAO                  
	ESCREVA "Pode tirar a CNH"              
SENAO
I2 <- 18-I
	ESCREVA "Pode tirar a CNH daqui I2 anos"
FIM_SE
FIM

```

#### Teste de mesa (1.0 ponto)
| Idade | Idade >= 18 |  I2 |                Saída               |
|  --   |      --     |  -- |                  --                |  
|  18   |      V      |     |         "Pode tirar a CNH"         |
|  16   |      F      |  2  |  "Pode tirar a CNH daqui a 2 anos" |
|  13   |      F      |  5  |  "Pode tirar a CNH daqui a 5 anos" |
|  30   |      V      |     |         "Pode tirar a CNH"         |
