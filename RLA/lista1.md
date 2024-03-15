# UNIFOR
**Nome**: Maria Clara Paterno Maia <br>
**Disciplina**: Raciocínio lógico e algoritmo

## Lista de exercícios 01

### Exercício 1
Represente, em fluxograma e pseudocódigo, um algoritmo para deterinar se um número inteiro e positicvo é par ou ímpar.

#### Fluxograma

```mermaid
flowchart TB
A([INÍCIO]) --> B{{Digite um número: }}
B --> C[/num/] 
C --> D{num>=0}
D --N--> E{{O número deve ser positivo}}
E --> F((fim))
D --S--> G[resto= num % 2]
G--> H{resto = 0?}
H--N-->I{{O número é ímpar}}
H--S-->J{{O número é par}}
I-->F
J-->F
```
#### Pseudocódigo
```
ALGORITMO verifica_par_impar
DECLARE num, resto: INTEIRO
INICIO
ESCREVA "Digite um número: "
LEIA num
SE num>=0 ENTAO 
	resto <- num % 2
	SE resto == 0 ENTAO
		ESCREVA "O número é par"
	SENAO 
		ESCREVA "O número é ímpar"
FIM_SE
SENAO
	ESCREVA "O número deve ser positivo"
FIM_SE
FIM
```

#### Teste
| num | resto | num >= 0 | resto == 0 | Saída |
| -- |-- |-- |-- |-- |
|-1 | False |  |  | "O número deve ser positivo" |
| 0 | True | 0 | True | "O número é par"
| 10 | True | 0 | True | "O número é par"
| 11 | True | 1 | False | "O número é ímpar" 

### Exercício 2

#### FLUXOGRAMA
``` mermaid
flowchart TB
A([INÍCIO]) --> B{{Digite seu salário: }}
B --> C[/sal/]
C --> D{sal>500?}
D --S--> E[nsal = 1,10*sal]
D --N--> G[nsal = 1,20*sal]
E-->I[/nsal/]
G-->I
I --> F{{O novo salário é nsal}}
F-->H([FIM])
```

#### PSEUDOCÓDIGO
```
ALGORITMO par_ímpar
Declare sal, nsal: INTEIRO
INICIO
ESCREVA "Digite seu salário: "
LEIA sal
SE sal > 500 ENTAO	
	nsal= 1,10*sal
SENAO
	nsal=1,20*sal
FIM_SE
LEIA nsal
	ESCREVA " seu novo salário é" nsal. 
FIM
```
	
#### TESTE
