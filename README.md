# Guia Completo de Estudo: Computação e Programação (MATLAB) - Semanas 1 a 6

## Introdução e Visão Geral

Com base na análise rigorosa dos documentos fornecidos, este guia apresenta um plano de estudo estruturado e detalhado para dominar a matéria até à Semana 6 do curso de Computação e Programação em Engenharia Civil. O material abrange conceitos fundamentais de programação em MATLAB, desde o ambiente básico até estruturas de dados avançadas e manipulação de ficheiros.[1][2][3]

**Estrutura do Documento:** Este guia está organizado em seis secções principais, correspondentes às seis semanas de estudo, com explicações teóricas detalhadas, exemplos práticos extraídos dos documentos, e exercícios progressivos que culminam na preparação para a Ficha 2.[2][3][1]

## Semana 1: Fundamentos do MATLAB

### 1.1 Ambiente MATLAB e Conceitos Iniciais

**Definição de Algoritmo:** Um algoritmo é uma sequência de instruções a ser executadas mecanicamente para atingir um determinado objetivo. No contexto da programação, estas instruções são expressas numa linguagem de programação específica.[2]

**O que é MATLAB?** MATLAB (MATrix LABoratory) é uma linguagem de programação de alto nível que permite utilização interativa e desenvolvimento de programas, oferecendo funções pré-definidas para cálculos matemáticos e visualização de gráficos.[2]

**Workspace Base:** Espaço de armazenamento em memória onde são guardadas as variáveis criadas durante a execução de scripts ou na janela de comandos. As variáveis definidas no workspace base existem até serem explicitamente apagadas ou até terminar a sessão.[2]

### 1.2 Variáveis e Tipos de Dados

**Variável:** Um espaço de armazenamento criado na memória do computador, tendo um nome associado, e o propósito de guardar um qualquer valor de um determinado tipo (domínio).[2]

**Regras para Nomes de Variáveis:**
- Apenas letras sem diacríticos, dígitos e sinais de sublinhado (_)[2]
- Deve começar sempre por uma letra[2]
- MATLAB é case-sensitive (distingue maiúsculas de minúsculas)[2]

**Tipos de Dados Simples:**

| Tipo | Descrição | Exemplo |
|------|-----------|---------|
| double | Números reais (tipo por omissão) | `x = 3.14` |
| single | Números reais com menos precisão | `y = single(3.14)` |
| int8, int16, int32, int64 | Inteiros com sinal | `a = int32(-128)` |
| uint8, uint16, uint32, uint64 | Inteiros sem sinal | `b = uint8(255)` |
| char | Caracteres | `c = 'a'` |
| logical | Valores lógicos (true/false) | `flag = true` |

[Tabela baseada em informação de ][2]

**Limitações dos Tipos Numéricos:** Os tipos numéricos têm limitações associadas à impossibilidade dos computadores armazenarem infinitos valores. Por exemplo:[2]
- `int8` usa 8 bits para armazenar um inteiro com sinal: valores entre -128 e 127[2]
- `intmin(int8)` retorna -128[2]
- `intmax(int8)` retorna 127[2]

### 1.3 Instrução de Atribuição e Expressões

**Instrução de Atribuição:** Coloca dados numa varável, definindo ou alterando o seu valor.[2]

```matlab
% Sintaxe:
nome_de_variavel = expressao

% Exemplos:
meuNumero = 8        % Com eco (mostra o resultado)
meuNumero = 8;       % Sem eco (ponto e vírgula suprime a saída)
meuNumero = 7        % Altera o valor
```
[Exemplo de ][2]

**Expressão:** Uma combinação de valores literais, operadores, identificadores que possam ser avaliados, e parênteses curvos, à qual corresponde o valor resultante da sua avaliação.[2]

```matlab
% Exemplos de expressões:
meuNumero = 5
meuNumero = meuNumero + 1    % meuNumero passa a ser 6
2 * sin(1.4)                 % ans = 1.9709
```
[Exemplos de ][2]

### 1.4 Operadores e Precedência

**Operadores:** Funções com sintaxe de invocação especial que retornam valores.[2]

**Precedência de Operadores (da maior para a menor):**
1. Parênteses `()`
2. Potenciação `^`
3. Troca de sinal `-` (unário)
4. Multiplicação `*`, `/` e divisão `.*`, `./`
5. Adição `+` e subtração `-`
6. Operadores relacionais `<`, `>`, `<=`, `>=`, `==`, `~=`
7. Negação lógica `~`
8. E lógico `&`
9. Ou lógico `|`
10. Atribuição `=`

[Ordem baseada em ][2]

### 1.5 Funções Pré-definidas

**Chamada de Função:** Sintaxe para invocar uma função pré-definida (built-in function).[2]

```matlab
% Exemplos:
rem(13, 5)           % Resto da divisão: ans = 3
abs(-12.5)           % Valor absoluto: ans = 12.5000
fix(-12.5)           % Arredondamento para zero: ans = -12
floor(-12.5)         % Arredondamento para baixo: ans = -13
ceil(-12.5)          % Arredondamento para cima: ans = -12
round(-12.5)         % Arredondamento normal: ans = -13
```
[Exemplos de ][2]

**Funções de Arredondamento - Diferenças Cruciais:**

```matlab
% fix vs floor para positivos:
fix(3.5)             % = 3 (trunca para zero)
floor(3.5)           % = 3 (arredonda para baixo)

% fix vs floor para negativos:
fix(-3.2)            % = -3 (trunca para zero)
floor(-3.2)          % = -4 (arredonda para baixo)

% fix vs ceil:
fix(-3.2)            % = -3 (trunca para zero)
ceil(-3.2)           % = -3 (arredonda para cima)
```
[Exemplos baseados em ][3]

### 1.6 Conversões de Tipos

**Conversão Explícita:** Conversões entre tipos de dados simples são definidas explicitamente.[2]

```matlab
var1 = [1 11];
var2 = int32(var1);
whos
% Name    Size    Bytes  Class    Attributes
% var1    1x1     8      double
% var2    1x1     4      int32
```
[Exemplo de ][2]

**Conversão Implícita:** Quando aparecem valores de tipos diferentes numa expressão, MATLAB tenta converter automaticamente alguns valores.[2]

```matlab
2.5 + 5 / 3          % ans = 3.5000
char(100.7)          % ans = 'd' (arredonda e converte)
```
[Exemplos de ][2]

### 1.7 Expressões Lógicas e Predicados

**Expressão Lógica:** Expressão cuja avaliaç produz um valor lógico ou booleano.[2]

**Valores Lógicos:**
- `false` ou `logical(0)` - exibido como 0[2]
- `true` ou `logical(número_diferente_de_zero)` - exibido como 1[2]

```matlab
% Exemplos:
true
isnumeric(x)         % Predicado: verifica se x é numérico
isletter('1')        % false
isempty([])          % true
'a' < 'b'            % true (compara valores ASCII)
'B' < 'b'            % true (maiúsculas têm valores menores)
isnumeric('a')       % false
xor(false, 0)        % false (ou exclusivo)
```
[Exemplos de ][2]

### 1.8 Números Pseudo-aleatórios

**Definição:** Um número pseudo-aleatório é um número extraído de uma sequência cujas propriedades são idênticas às de uma sequência de números aleatórios.[2]

**Funções Principais:**

```matlab
% rand - reais entre 0 e 1 (distribuição uniforme):
rand                          % Gera um valor
rand * (30 - 20) + 20        % Gera entre 20 e 30
rand(2,3) * (30 - 20) + 20   % Gera matriz 2x3

% randi - inteiros (distribuição uniforme):
randi(6)                     % Inteiro entre 1 e 6
randi([1, 6])               % Equivalente ao anterior
randi([50, 100])            % Inteiro entre 50 e 100
randi([20, 30], 2, 3)       % Matriz 2x3 com valores entre 20 e 30

% randn - reais (distribuição normal):
randn                        % Média 0, desvio padrão 1

% rng - controlo da semente:
rng('shuffle')              % Reinicia usando o relógio
```
[Exemplos de ][2]

### 1.9 Códigos ASCII e Caracteres

**Representação Interna:** Cada caracter corresponde a um valor inteiro. Os primeiros 128 caracteres usam a tabela ASCII.[2]

```matlab
double('a')          % ans = 97
double('a 9')        % ans = [97 32 57]
char(97)             % ans = 'a'
char(['a' '9'] + 1)  % ans = 'b:' (incrementa valores ASCII)
```
[Exemplos de ][2]

**Ordem ASCII:** As maiúsculas vêm antes das minúsculas na tabela ASCII.[3]

```matlab
'A' < 'a'            % true ('A' = 65, 'a' = 97)
'B' < 'b'            % true
```

### Exercícios Práticos - Semana 1

**Problema 1 (de ):** Descubra a função pré-definida que permite obter o seno de um ângulo em graus. Teste se essa função devolve o valor 1 quando recebe o valor 90.[3]

```matlab
help elfun           % Lista funções matemáticas elementares
sind(90)             % ans = 1 (seno em graus)
```

**Problema 2 (de ):** Escreva as seguintes expressões em MATLAB:[3]

```matlab
% a) √23
sqrt(23)             % ans = 4.7958

% b) 4^3.2
4^3.2                % ans = 84.4485

% c) tan(π)
tan(pi)              % ans = -1.2246e-16 (aproximadamente 0)
```

**Problema 5 (de ):** Considere a função:[3]

\[ z = \frac{x^3 - (x-y)^3}{x^2 - (x-y)^2} \]

```matlab
x = 5;
y = 2;
z = (x^3 - (x-y)^3) / (x^2 - (x-y)^2);
% z = 31.0000
```

## Semana 2: Vectores e Matrizes (Arrays)

### 2.1 Conceito de Array

**Array:** Tipo de dados estruturado, pré-definido, que permite guardar vários valores, todos de um mesmo tipo, sendo estes acedidos através do uso de índices.[2]

**Características:**
- Cada valor é guardado num elemento[2]
- Elementos organizados em dimensões[2]
- Cada elemento identificado pela sua posição (índice) em cada dimensão[2]
- No MATLAB, os índices começam pelo valor 1[2]

**Vector:** Array com uma dimensão apenas.[2]
- **Vector linha:** Array com uma linha apenas (todos os elementos têm índice 1 na primeira dimensão)[2]
- **Vector coluna:** Array com uma coluna apenas[2]

**Matriz:** Array com duas ou mais dimensões.[2]

### 2.2 Crição de Vectores

**Vectores Linha - Sintaxes:**

```matlab
% Sintaxe específica para strings:
v1 = 'ol'                    % v1 = 'ol'

% Sintaxe geral usando concatenação:
v1 = ['o' 'l']              % v1 = 'ol'
v1 = ['o', 'l', 'á']        % v1 = 'olá'

% Vectores numéricos:
x = [3 -5 1]                % x = [3 -5 1]
x = [3, -5, 1]              % Equivalente (vírgulas opcionais)

% Verificação:
whos v1 x
% Name  Size  Bytes  Class      Attributes
% v1    1x3   6      char
% x     1x3   24     double
```
[Exemplos de ][2]

**Vectores Coluna - Operador de Transposição:**

```matlab
% Usando operador de transposição ('):
v2 = 'ol'                   % v2 coluna
v2 = ['o'; 'l']             % Usando ponto e vírgula
v2 = ['o' 'l']'             % Transpondo vector linha

whos v2
% Name  Size  Bytes  Class      Attributes
% v2    3x1   6      char
```
[Exemplos de ][2]

### 2.3 Operador Dois Pontos

**Funcionalidade:** Cria vectores linha com elementos de uma progresso aritmética.[2]

**Sintaxe:** `primeiro:incremento:limite`
- Se incremento for omitido, assume-se 1[2]
- O limite é incluído apenas se fizer parte da progresso[2]

```matlab
% Exemplos:
vec = 3:2:10            % vec = [3 5 7 9]

vec1 = 2:1.3:7          % vec1 = [2.0 3.3 4.6 5.9]

vec2 = 2:-1.3:-4        % vec2 = [2.0 0.7 -0.6 -1.9 -3.2]

vec3 = 2:7              % vec3 = [2 3 4 5 6 7]

% Para trás:
vec4 = 10:-2:1          % vec4 = [10 8 6 4 2]
```
[Exemplos de ][2]

### 2.4 Funções para Criar Vectores

**linspace - Divisão Uniforme de Intervalo:**

Sintaxe: `linspace(primeiro, último, número_de_valores)`

```matlab
% Criar 5 valores entre 2 e 4:
linspace(2, 4, 5)       % ans = [2.0 2.5 3.0 3.5 4.0]

% Útil para gráficos:
x = linspace(-pi, pi, 21);    % 21 pontos (20 intervalos)
y = sin(x);
```
[Exemplo de ][2]

**logspace - Divisão Logarítmica:**

Sintaxe: `logspace(exp_primeiro, exp_último, número_de_valores)`

```matlab
% Valores 10^2, valor_intermédio, 10^4:
logspace(2, 4, 3)       % ans = [100 1000 10000]
```
[Exemplo de ][2]

### 2.5 Concatenação de Vectores

**Operadores de Concatenação:** Parênteses rectos `[]` servem para concatenar (juntar) arrays.[2]

```matlab
% Com escalares e vectores:
vector = [2:4]                      % vector = [2 3 4]
vector2 = [4:7]                     % vector2 = [4 5 6 7]
v = [vector 10 vector2]            % v = [2 3 4 10 4 5 6 7]

% Concatenação vertical (criar vector coluna):
v_col = [1; 2; 3]                  % Vector coluna 3x1
```
[Exemplos de ][2]

### 2.6 Consulta e Modificação de Vectores

**Consulta de Vectores:**

```matlab
a = 'Bom dia.';
a(5)                    % ans = 'd'
a([7 1 5])             % ans = 'aBd'

x = 2:2:10;            % x = [2 4 6 8 10]
x(end-2:end)           % ans = [6 8 10] (end é palavra reservada)
x([1:3, end-1])        % ans = [2 4 6 8]
```
[Exemplos de ][2]

**Modificação de Vectores:**

```matlab
v = 3:10;              % v = [3 4 5 6 7 8 9 10]
v(1:3) = [];           % Apaga elementos (array vazio)
                       % v = [6 7 8 9 10]

v(3:end) = v(2:-1:1);  % Número de elementos igual
                       % v = [6 7 7 6]

v([1 1]) = [0];        % v = [0 7 6]
```
[Exemplos de ][2]

### 2.7 Crião e Manipulação de Matrizes

**Criação Direta:**

```matlab
% Usando espaços e ponto-e-vírgula:
m = [1 2 3; 4 5 6]     
% m = [1 2 3
%      4 5 6]

% Equivalente:
m = [1, 2, 3; 4, 5, 6]

% Verificação:
whos m
% Name  Size  Bytes  Class      Attributes
% m     2x3   48     double
```
[Exemplo de ][2]

**Funções para Criar Matrizes:**

```matlab
% Matriz de zeros:
m1 = zeros(2,3)        % m1 = [0 0 0; 0 0 0]

% Matriz de uns:
m2 = ones(3,2)         % m2 = [1 1; 1 1; 1 1]

% Matriz aleatória:
m3 = rand(2,3)         % Reais entre 0 e 1
m4 = randi([1, 10], 2, 4)  % Inteiros entre 1 e 10
```
[Exemplos de ][2]

**Consulta e Modificação de Matrizes:**

```matlab
m2 = ones(3,2);
m2(2,:) = [-5 -45.6]   % ':' significa "todos"
% m2 = [1.0  1.0
%       -5.0 -45.6
%       1.0  1.0]

m3 = randn(2,3);
m3(:,end) = []         % Apaga última coluna (sempre linhas ou colunas completas)
```
[Exemplos de ][2]

### 2.8 Tamanho de Arrays

**Funções length e size:**

```matlab
v = 1:5;
length(v)              % ans = 5 (maior dimensão)

m = rand(2,3);
maiorTamanho = length(m)         % = 3
[nLinhas, nColunas] = size(m);   % nLinhas = 2, nColunas = 3
```
[Exemplos de ][2]

### 2.9 Funções para Arrays

**Funções Estatísticas Básicas:**

```matlab
vec = [4 -2 5 11];

min(vec)               % ans = -2
max(vec)               % ans = 11
sum(vec)               % ans = 18
prod(vec)              % ans = -440
cumsum(vec)            % ans = [4 2 7 18] (somas acumuladas)
cumprod(vec)           % ans = [4 -8 -40 -440] (produtos acumulados)
```
[Exemplos de ][2]

**Operações em Matrizes (por colunas):**

```matlab
mat = randi([1, 10], 2, 4);
% mat = [10  5  8  2
%        1   4  8  5]

sum(mat)               % ans = [11 9 16 7] (soma por colunas)
cumsum(mat)            % ans = [10 5  8  2
                       %        11 9 16  7] (acumulação por colunas)

min(min(mat))          % ans = 1 (mínimo de toda a matriz)
sum(sum(mat))          % ans = 43 (soma de todos os elementos)
```
[Exemplos de ][2]

### 2.10 Operações com Arrays

**Operações Array-Escalar (elemento a elemento):**

```matlab
[4 0 11] + 3          % ans = [7 3 14]
zeros(1,3) + 5        % ans = [5 5 5]
[4 0 11].^2          % ans = [16 0 121] (operador ponto necessário)
```
[Exemplos de ][2]

**Operações Elemento a Elemento (.* ./ .^):**

Arrays A e B devem ter as mesmas dimensões.[2]

```matlab
v1 = [2 2 2];
v2 = [2 3 4];
resultado = v1 .* v2   % ans = [4 6 8] (multiplicação elemento a elemento)
```
[Exemplo de ][2]

**Multiplicação Matricial (álgebra linear):**

```matlab
v = ones(1,3);         % v = [1 1 1]
m = 2*ones(3,2);       % m = [2 2; 2 2; 2 2]
resultado = v * m      % ans = [6 6] (multiplicação matricial)
```
[Exemplo de ][2]

### 2.11 Vectores Lógicos e Indexação

**Vectores Lógicos:**

```matlab
vec = [44 3 2 9 11 6];
vlog = vec >= 6;       % vlog = [1 0 0 1 1 1] (valores lógicos)
vec(vlog)              % ans = [44 9 11 6] (filtragem por condição)

% Equivalente:
vec(vec >= 6)          % ans = [44 9 11 6]
```
[Exemplos de ][2]

### 2.12 Funções Lógicas

```matlab
v1 = [1 2 3 4];
v2 = [1 0 3 4];

v1 == v2               % ans = [1 0 1 1]
all(v1 == v2)          % ans = 0 (false - nem todos são iguais)
any(v1 == v2)          % ans = 1 (true - algum é igual)

v1 = [14 23 31 44];
v2 = [14 0 31 44];
find(v1 == v2)         % ans = [1 3 4] (índices dos elementos iguais)
isequal(v1, v2)        % ans = logical(0) (arrays não são iguais)
```
[Exemplos de ][2]

### Exercícios Práticos - Semana 2

**Problema 1 (de ):** Crie os seguintes vectores:[3]

```matlab
% a) -5 -4 -3 -2 -1
v_a = -5:-1
v_a_alt = linspace(-5, -1, 5)

% b) 5 7 9
v_b = 5:2:9

% c) 8 6 4
v_c = 8:-2:4
```

**Problema 2 (de ):** Expressão para elementos em posições ímpares:[3]

```matlab
v = [10 20 30 40 50 60];
v(1:2:end)             % ans = [10 30 50]

% Apagar elementos pares:
v(2:2:end) = [];       % v = [10 30 50]
```

**Problema 5 (de ):** Criar vectores x e y para gráfico:[3]

```matlab
x = linspace(-pi, pi, 21);    % 21 valores (número ímpar)
y = sin(x);
plot(x, y)
```

**Problema 8 (de ):** Vector com operações:[3]

```matlab
v = randi([-10, 5], 1, 5);

% a) Subtrair 3 unidades:
v - 3

% b) Contagem de positivos:
sum(v > 0)

% c) Valor absoluto:
abs(v)

% d) Valor máximo:
max(v)

% e) Somatório dos positivos:
sum(v(v > 0))
```

## Semana 3: Scripts, Funções e Entrada/Saída

### 3.1 Scripts

**Ficheiro-M:** Ficheiro de texto simples com extensão .m, tem como finalidade armazenar código escrito em MATLAB.[2]

**Script:** Ficheiro-M contendo uma sequência de instruções (statements).[2]

**Principais Instruções em MATLAB:**
- Atribuição[2]
- Invocação de algoritmos a operar sem retorno (por efeito colateral)[2]
- Selecção ou condicional[2]
- Repetição ou de iteração, ou de ciclo[2]

**Comentários:** Explicação escrita em língua natural pelo programador junto do código. Fundamentais para a compreensão do código.[2]

```matlab
% Exemplo: script1.m
% Este script calcula a área de um rectângulo.
clc                % Limpa o ecrã
clear              % Apaga todas as variáveis do base workspace

largura = 7.5;     % Define a largura
comprimento = 8.6;  % Define o comprimento
area = largura * comprimento;    % Calcula a área
```
[Exemplo de ][2]

### 3.2 Entrada/Saída Interativa

**Função input:** Usa a janela de comandos para pedir dados ao utilizador.[2]

```matlab
% Entrada numérica:
varnum = input('Que idade tem? ');    % Obtém escalar numérico

% Entrada de string:
varstr = input('Qual o seu nome? ', 's');    % 's' força string
```
[Exemplos de ][2]

**Função disp:** Mostra dados ao utilizador, sem especificar formato.[2]

```matlab
disp('Olá Mundo!');
m = [1 2; 3 4];
disp(m);
disp(['Um byte guarda ' num2str(2^8) ' valores']);
```
[Exemplos de ][2]

**Função fprintf:** Permite especificar formato de saída.[2]

```matlab
fprintf('Olá Mundo!\n');

nome = 'Maria';
idade = 20;
fprintf('A %s tem %d anos.\n', nome, idade);

fprintf('Um real com duas casas decimais: %.2f.\n', pi);
% Saída: Um real com duas casas decimais: 3.14.
```
[Exemplos de ][2]

**Especificadores de Formato Principais:**
- `%d` - inteiro decimal
- `%f` - real (ponto flutuante)
- `%.2f` - real com 2 casas decimais
- `%s` - string
- `\n` - nova linha
- `\t` - tabulação

### 3.3 Grficos 2D

**Função plot:** Usada para gerar gráficos em sistemas de eixos cartesianos 2D. Traça linhas definidas por pontos.[2]

**Argumentos de Entrada:**
1. Vector com valores das abcissas dos pontos[2]
2. Vector paralelo com valores das ordenadas dos pontos[2]

```matlab
% Exemplo: grafico2D.m
clc
clear

horas = 0:24;
temp = [14, 14, 15, 16, 17, 18, 19, 21, 21, 24, 23, 24, ...
        25, 27, 28, 26, 26, 24, 22, 21, 18, 16, 15, 15, 14];

plot(horas, temp, '-square');    % Linha com marcadores quadrados
axis([0 24 0 40]);               % Define limites dos eixos
xlabel('Hora');
ylabel('Temperatura');
title('Temperatura média horária ao longo do dia');
```
[Exemplo de ][2]

### 3.4 Entrada/Saída com Ficheiros (save e load)

**Funções save e load:** Para guardar e recuperar valores de variáveis entre memória primária e secundária.[2]

```matlab
% Guardar variáveis:
tempmin = [8.2, 9.0, 9.9, 11.1, 13.0, 15.6, 17.4, 17.7, ...
           17.0, 14.6, 11.2, 8.9];
tempmax = [14.5, 15.6, 17.6, 19.1, 21.7, 24.8, 27.4, 27.9, ...
           26.4, 22.4, 17.8, 14.8];
precip = [109.6, 110.8, 68.9, 64.0, 38.6, 21.2, 4.8, 5.7, ...
          25.7, 80.3, 113.5, 107.6];

save meteo.dat tempmin tempmax -ascii        % Guardar em texto ASCII
save meteo.dat precip -ascii -append         % Adicionar mais dados

% Carregar variáveis:
load meteo.dat -ascii                        % Carrega para matriz 'meteo'
```
[Exemplo de ][2]

### 3.5 Funções - Definição Básica

**Funo:** Algoritmo encapsulado por uma interface, executado num workspace criado para o efeito e destruído no final da execução.[2]

**Estrutura:**
- **Cabealho:** Define o nome e a interface da funo[2]
- **Corpo:** Conjunto de instruções que implementam o algoritmo[2]
- O nome da função deve coincidir com o nome do ficheiro-M[2]

**Esqueleto Básico:**

```matlab
function [outputargs] = Untitled(inputargs)
% UNTITLED Summary of this function goes here
%   Detailed explanation goes here
end
```
[Esqueleto de ][2]

**Exemplo Simples:**

```matlab
% farearectangulo.m
function area = farearectangulo(largura, comprimento)
% farearectangulo - Área de um rectângulo a partir dos lados.
%   Um exemplo muito simples com a definio de uma funo que 
%   recebe dois valores numéricos, correspondentes à largura e 
%   ao comprimento de um rectângulo, e que retorna (devolve) 
%   o valor correspondente à área desse rectângulo.

area = largura * comprimento;
end
```
[Exemplo de ][2]

**Utilização:**

```matlab
l = 3.4;
c = 4.3;
a = farearectangulo(l, c);    % a = 14.6200
```
[Exemplo de ][2]

### 3.6 Variáveis Locais e Âmbito

**Variável Local:** Variável definida dentro de uma função, só acessível nessa função, desde a sua criação até ao fim da função.[2]

**mbito (Scope):** Conjunto das regiões de código dentro das quais um identificador pode ser usado.[2]

**Regras de Âmbito:**
- Variável definida num script ou na janela de comandos: acessível em qualquer script ou na janela de comandos[2]
- Identificador definido numa função: âmbito local (desde a definição até ao fim da função)[2]
- Parâmetro de função: em âmbito desde o início do corpo da função[2]
- Em geral, numa função não se pode usar identificador de variável definida fora dessa função[2]

```matlab
% farearectangulo2.m
function area = farearectangulo2(x1, y1, x2, y2)
% farearectangulo2 - Área de um rectângulo a partir dos cantos.

    largura = abs(x2 - x1);      % Variável local
    comprimento = abs(y2 - y1);  % Variável local
    area = largura * comprimento;
end
```
[Exemplo de ][2]

### 3.7 Tempo de Vida de Variáveis

**Tempo de Vida:** Período durante o qual o valor da variável pode ser usado.[2]

- Variável no workspace base: existe até ser apagada explícita/implicitamente, ou até terminar a sessão[2]
- Variável definida numa função: existe enquanto não terminar a execução dessa função[2]

### 3.8 Teste de Funções

**Importância:** Testar funções é fundamental para garantir correção.[2]

```matlab
% testafarearectangulo.m
% Testa a função farearectangulo.

clc, clear

larg = input('Introduza o valor da largura: ');
comp = input('Introduza o valor do comprimento: ');

fprintf('A área do rectângulo = %.2f (%.2f x %.2f).\n', ...
        farearectangulo(larg, comp), larg, comp);
```
[Exemplo de ][2]

### Exercícios Práticos - Semana 3

**Problema 1 (de ):** Função meiasDuzias:[3]

```matlab
% meiasDuzias.m
function mat = meiasDuzias(nLinhas, nColunas)
% meiasDuzias - Cria matriz de 6's com dimensões especificadas.
%   Recebe dois inteiros positivos e devolve matriz com o número 
%   de linhas e colunas especificado, com todos os elementos = 6.

mat = 6 * ones(nLinhas, nColunas);
end
```

**Problema 2 (de ):** Predicado divisivelPor5:[3]

```matlab
% divisivelPor5.m
function resultado = divisivelPor5(numero)
% divisivelPor5 - Verifica se número é divisível por 5.
%   Recebe inteiro e retorna true se divisível por 5, false caso contrário.
%   Não utiliza instruções de selecção.

resultado = (rem(numero, 5) == 0);    % Operação relacional retorna logical
end
```

**Problema 3 (de ):** Elemento aleatório de vector:[3]

```matlab
% elementoAleatorio.m
function elem = elementoAleatorio(vec)
% elementoAleatorio - Retorna elemento aleatório de um vector.

    indice = randi([1, length(vec)]);
    elem = vec(indice);
end
```

**Problema 4 (de ):** Função calculaCusto:[3]

```matlab
% calculaCusto.m
function custo = calculaCusto(n)
% calculaCusto - Calcula custo de produção de n unidades.
%   Fórmula: C(n) = 5n^2 + 44n + 11

custo = 5 * n^2 + 44 * n + 11;
end

% progCalculaCusto.m (script)
% Programa para calcular custo de produção.

clc, clear

n = input('Introduza o número de unidades: ');
custo = calculaCusto(n);
fprintf('O custo para produzir %d unidades é %.2f €.\n', n, custo);
```

## Semana 4: Instruções de Selecção e Iteração

### 4.1 Controlo de Fluxo

**Definição:** Controlo de fluxo de execução refere-se às instruções que determinam a ordem de execução das instruções num programa. Principais tipos: sequência, selecção, iteração.[2]

### 4.2 Instrução if

**Instrução de Selecção if:** Permite condicionar a execução de um conjunto de instruções de acordo com a avaliaço de uma condição (expressão lógica).[2]

```matlab
% Exemplo básico:
if x > y
    temp = x;
    x = y;
    y = temp;
end
```
[Exemplo de ][2]

**Variante if-else:**

```matlab
% Cara ou coroa:
if rand > 0.5
    disp('Cara');
else
    disp('Coroa');
end
```
[Exemplo de ][2]

**Variante if-elseif-else:**

```matlab
% Que naipe?
x = rand;
if x < 1/4
    disp('Espadas');
elseif x < 0.5         % Se x < 1/4, esta cláusula já não é verificada
    disp('Copas');
elseif x < 3/4
    disp('Ouros');
else
    disp('Paus');
end
```
[Exemplo de ][2]

**Alternativa sem elseif (mais confuso):**

```matlab
x = rand;
if x < 1/4
    disp('Espadas');
else
    if x < 0.5
        disp('Copas');
    else
        if x < 3/4
            disp('Ouros');
        else
            disp('Paus');
        end
    end
end
```
[Exemplo de ][2]

### 4.3 Instrução switch

**Instrução switch:** Oferece sintaxe compacta para definir vários blocos de instruções de execução alternativa.[2]

```matlab
% Exemplo:
x = randi(4);
switch x                 % Aqui poderia estar uma expressão
    case 1               % Aqui: case {1, 2} para múltiplos valores
        disp('Espadas');
    case 2
        disp('Copas');
    case 3
        disp('Ouros');
    otherwise            % Equivale ao else
        disp('Paus');
end
```
[Exemplo de ][2]

**Equivalência com if:**

```matlab
x = randi(4);
if x == 1
    disp('Espadas');
elseif x == 2
    disp('Copas');
elseif x == 3
    disp('Ouros');
else
    disp('Paus');
end
```
[Exemplo de ][2]

### 4.4 Funo menu

**Funo menu:** Cria interface gráfica para o utilizador escolher uma opção.[2]

```matlab
% signos.m (exemplo simplificado de [2])
clc, clear

signo = menu('Horóscopo', 'Aquário', 'Peixes', 'Carneiro');
inicio = 'Irá receber uma prenda entre ';

switch signo
    case 1
        disp([inicio '21/01 e 19/02.']);
    case 2
        disp([inicio '20/02 e 20/03.']);
    case 3
        disp([inicio '21/03 e 20/04.']);
    otherwise
        disp('Poderá não receber prendas.');
end
```

### 4.5 Instrução for

**Instruo for:** Permite repetir a execução de um bloco de instruções. O controlo é feito recorrendo a uma variável de iteração e um vector linha de valores.[2]

```matlab
% Exemplo - Contagem decrescente:
for i = 3:-1:1
    disp(i);
end
disp('Partida!');
```
[Exemplo de ][2]

**Processamento de Vectores:**

```matlab
% Método 1 - Acesso por índices:
v = [10 20 30];
disp('Os valores de v são:');
for i = 1:length(v)       % Varre todos os índices
    disp(v(i));           % Processa cada elemento
end

% Método 2 - Acesso direto (mais rápido):
disp('Repito, os valores de v são:');
for valor = v             % Varre todos os valores
    disp(valor);          % Processa cada valor
end
```
[Exemplos de ][2]

### 4.6 Inicialização e Pré-alocação

**Inicializao:** Atribuir valor pela primeira vez a uma varivel.[2]

**Inicializao de Ciclo:** Inicializar variáveis antes do ciclo para que funcione corretamente na primeira iteração. Os valores escolhidos devem ser criteriosamente escolhidos.[2]

**Pr-alocação:** Inicializar o array antes do ciclo já com o tamanho necessário no final. Evita mudanças de tamanho durante a execução, melhorando o desempenho.[2]

**Exemplo com Inicialização:**

```matlab
% somatorio.m
function soma = somatorio(inicio, fim)
% somatorio - Soma os inteiros no intervalo dado.

    if inicio > fim          % Se inicio > fim, troca os limites
        temp = inicio;
        inicio = fim;
        fim = temp;
    end
    
    soma = 0;               % Inicialização crucial
    for i = inicio:fim
        soma = soma + i;
    end
end
```
[Exemplo de ][2]

**Exemplo com Pré-alocação:**

```matlab
% somasacumuladas.m
function somas = somasacumuladas(inicio, fim)
% somasacumuladas - Somas acumuladas para o vector [inicio:fim].

    somas = zeros(size(inicio:fim));   % Pr-alocação de memória
    
    if isempty(somas)
        somas = [];
    else
        somas(1) = inicio;              % Inicialização
        for i = 1:(fim-inicio)
            somas(i+1) = somas(i) + (inicio + i);
        end
    end
end
```
[Exemplo de ][2]

### 4.7 Validação de Dados e Retorno

**Validação de Dados:** Verificar se os dados entrados são válidos.[2]

**Estratégias:**
- **Entrada interativa:** Pedir os dados de novo[2]
- **Entrada via interface de função:** Retornar array vazio `[]` (prática habitual do MATLAB)[2]

### 4.8 Ciclos Embebidos

**Ciclos Embebidos:** Um ciclo pode ser definido dentro de outro ciclo.[2]

```matlab
% Exemplo - Emparelhar elementos:
disp('Valor de i   Valor de j');
for i = 1:2:10        % [1 3 5 7 9]
    for j = 1:3:10    % [1 4 7 10]
        fprintf('%10d %d\n', i, j);
    end
    fprintf('\n');
end
```
[Exemplo de ][2]

**Processamento de Matrizes:**

```matlab
% Assume-se que a matriz m existe
[nL, nC] = size(m);

disp('Os valores de m são:');
for i = 1:nL          % Varre todas as linhas
    disp(['Linha ' num2str(i)]);
    for j = 1:nC      % Varre todas as colunas da linha atual
        fprintf('%f ', m(i,j));
    end
    fprintf('\n');
end
```
[Exemplo de ][2]

**Exemplo - Soma de Colunas:**

```matlab
% somacolunas.m
function somatorios = somacolunas(matriz)
% somacolunas - Somatórios das colunas da matriz recebida.

    [nLinhas, nColunas] = size(matriz);
    somatorios = zeros(1, nColunas);    % Inicialização e pr-alocação
    
    for j = 1:nColunas                  % Varre as colunas
        for i = 1:nLinhas               % Varre as linhas da coluna atual
            somatorios(j) = somatorios(j) + matriz(i,j);
        end
    end
end
```
[Exemplo de ][2]

### 4.9 Instrução while

**Instrução while:** Permite repetir a execução de um bloco de instruções enquanto uma condição for verdadeira. Usada quando não é possível conhecer à partida o número de iterações.[2]

```matlab
% Exemplo - Jogo de adivinhar:
pintas = input('Vou lançar um dado. Quantas pintas sairão? ');
while pintas ~= randi(6)
    pintas = input('Falhou. Novo lançamento. Tente de novo. ');
end
disp('Parabéns. Acertou.');
```
[Exemplo de ][2]

**Validação de Dados de Entrada:**

```matlab
% Forçar introdução de inteiro:
entrada = input('Introduza um inteiro: ');
inteiro = int32(entrada);

while entrada ~= inteiro
    entrada = input('Erro! Introduza um inteiro: ');
    inteiro = int32(entrada);
end

fprintf('O número introduzido foi %d.\n', entrada);
```
[Exemplo de ][2]

### 4.10 Vectorização

**Vectorizao:** Substituir instruções de ciclo por operadores de escalares, operadores de arrays, e funções pré-definidas que recebam arrays.[2]

```matlab
% Exemplo - Pretende-se [0^(1/2), 0.5^(1/2), 1^(1/2), ..., 20^(1/2)]:

% Sem vectorização:
i = 0;
for valor = 0:0.5:20
    i = i + 1;
    vec(i) = sqrt(valor);
end

% Com vectorização:
vec = 0:0.5:20;
vec = sqrt(vec);
```
[Exemplo de ][2]

### Exercícios Práticos - Semana 4

**Problema 1 (de ):** Função calculaCateto com validação:[3]

```matlab
% calculaCateto.m
function cateto = calculaCateto(cateto1, hipotenusa)
% calculaCateto - Calcula cateto usando teorema de Pitágoras.

    if cateto1 <= 0 || hipotenusa <= 0
        cateto = [];    % Retorna vazio para dados inválidos
    else
        cateto = sqrt(hipotenusa^2 - cateto1^2);
    end
end

% Script de teste:
clc, clear

cat1 = input('Introduza o valor de um cateto: ');
hip = input('Introduza o valor da hipotenusa: ');

cat2 = calculaCateto(cat1, hip);

if isempty(cat2)
    disp('Erro: valores devem ser positivos.');
else
    fprintf('O outro cateto vale %.2f\n', cat2);
end
```

**Problema 1 (de  - Iteração):** Pedir raio positivo:[3]

```matlab
% Script para pedir raio positivo:
clc, clear

raio = input('Introduza o valor do raio (positivo): ');

while raio <= 0
    disp('Erro: o raio deve ser positivo!');
    raio = input('Introduza o valor do raio (positivo): ');
end

area = pi * raio^2;
fprintf('A área do círculo é %.2f\n', area);
```

**Problema 2 (de  - Iteração):** Aproximação de 1/e:[3]

```matlab
% Script para aproximar 1/e:
clc, clear

n = 1;
diferenca = abs((1 - 1/n)^n - 1/exp(1));

while diferenca >= 0.0001
    n = n + 1;
    diferenca = abs((1 - 1/n)^n - 1/exp(1));
end

fprintf('1/e pré-definido: %.4f\n', 1/exp(1));
fprintf('Aproximação encontrada: %.4f\n', (1 - 1/n)^n);
fprintf('Valor de n necessário: %d\n', n);
```

**Problema 3 (de  - Iteração):** Mostrar elementos de vector:[3]

```matlab
% mostraElementos.m
function mostraElementos(vec)
% mostraElementos - Mostra elementos de vector com frases.

    for i = 1:length(vec)
        fprintf('O elemento %d é %.2f.\n', i, vec(i));
    end
end
```

## Semana 5: Programação Modular, Strings e Gráficos

### 5.1 Programação em Larga Escala

**Decomposição Top-Down:** Abordagem modular onde problemas são sucessivamente decompostos em problemas mais simples.[2]

**Programa Modular:** Programa cuja solução é decomposta em módulos, cada um implementado como uma função. O script que chama estas funções é designado por programa principal.[2]

**Estrutura Típica:**
- Programas em MATLAB são combinações de scripts e funções definidas pelo utilizador[2]
- Começam a ser executados por um script (script principal)[2]
- Scripts podem ser substituídos por funções sem argumentos (vantagem: variáveis locais)[2]

### 5.2 Retorno Múltiplo

**Definição de Função com Retorno Múltiplo:**

```matlab
% retornadoisvalores.m
function [dobro, quadrado] = retornadoisvalores(entrada)
% retornadoisvalores - Dobro e quadrado do argumento de entrada.

    dobro = entrada * entrada;
    quadrado = entrada .^ entrada;    % Operação elemento a elemento
end
```
[Exemplo de ][2]

**Invocação:**

```matlab
[var1, var2] = retornadoisvalores([2 0.5 4]);
% ou:
[var1 var2] = retornadoisvalores([2 0.5 4]);

% var1 = [4.0000  6.2500  9.0000  12.2500  16.0000]
% var2 = [4.0000  6.2500  9.0000  12.2500  16.0000]
```
[Exemplo de ][2]

**Exemplo com Dois Parâmetros de Entrada e Saída:**

```matlab
% areaperimetrorectangulo.m
function [area, perimetro] = areaperimetrorectangulo(largura, comprimento)
% areaperimetrorectangulo - Área e perímetro de um rectângulo.

    area = largura * comprimento;
    perimetro = 2 * largura + 2 * comprimento;
end
```
[Exemplo de ][2]

### 5.3 Funções Locais (Subfunções)

**Funo Local ou Subfunção:** Função definida num ficheiro-M após a definição de uma primeira função (função principal). Só pode ser utilizada no ficheiro onde está definida (mbito limitado ao ficheiro).[2]

```matlab
% calculosrectangulo2.m
function calculosrectangulo2
    [comp, larg] = ledados2;
    [area, perimetro] = areaperimetrorectangulo(larg, comp);
    mostraresultado2(area, perimetro);
end

function [comprimento, largura] = ledados2
    largura = input('Qual a largura do rectângulo? ');
    comprimento = input('Qual o comprimento do rectângulo? ');
end

function mostraresultado2(area, perim)
    fprintf('Área = %g; Perímetro = %g\n', area, perim);
end
```
[Exemplo de ][2]

### 5.4 Programas com Menu

**Estrutura Típica de Programa com Menu:**

```matlab
% calculosrectangulomenu.m
% Script para ilustrar a utilização da função menu.

clear, clc

b = 0; 
h = 0;    % Para o caso de haver opção 2 sem opção 1

opcao = mostramenu;    % Mostra o menu e obtém uma escolha

while opcao ~= 3       % A opção 3 é para sair
    switch opcao
        case 1         % Introduz os dados
            [b, h] = ledados;
        case 2         % Faz os cálculos e mostra o resultado
            [area, perimetro] = areaperimetrorectangulo(b, h);
            mostraresultado(area, perimetro);
    end
    opcao = mostramenu;
end

disp('Adeus!');
```
[Exemplo de ][2]

**Função mostramenu:**

```matlab
% mostramenu.m
function resposta = mostramenu
% mostramenu - Menu para o input do script calculosrectangulomenu.

    resposta = menu('Escolha uma opção', 'Introduzir Dados', ...
                    'Calcular e mostrar resultados', 'Sair do programa');
    
    % Ciclo para forçar o utilizador a introduzir uma opção:
    while resposta == 0
        disp('Por favor escolha uma opção.');
        resposta = menu('Escolha uma opção', 'Introduzir Dados', ...
                        'Calcular e mostrar resultados', 'Sair do programa');
    end
end
```
[Exemplo de ][2]

### 5.5 Manipulação de Strings

**String:** Vector linha cujos elementos são caracteres (tipo char). Literais string são representados entre plicas.[2]

**Criação de Strings:**

```matlab
saudacao = 'Bom dia!';

% Casos particulares:
stringvazio = '';                % String vazio
stringcomplica = 'Uma plica''';  % Duplicar plica para incluí-la

whos saudacao
% Name        Size    Bytes  Class    Attributes
% saudacao    1x8     16     char
```
[Exemplos de ][2]

**Caracteres Especiais:**

```matlab
umasolinha = ['Um' char(10) 'Dois'];    % char(10) = newline
% umasolinha = 'Um
%               Dois'
```
[Exemplo de ][2]

**Funções para Criar Strings:**

```matlab
% input:
nome = input('Como se chama? ', 's');

% sprintf:
msg = sprintf('%s, hoje é dia %s', nome, date);

% Conversão numérico -> string:
s = int2str([33.5, 44.4]);    % s = '34  44' (arredonda primeiro)
ans = num2str(12.345, '%.1f');  % ans = '12.3'

% Conversão string -> numérico:
m = str2num('33.31 22; 12, 54.56');
% m = [33.31 22.00
%      12.00 54.56]
```
[Exemplos de ][2]

**Manipulação de Strings:**

```matlab
% Concatenação:
frase = 'repito';
frase2 = [frase(1:7) ' e ' frase];    % 'repito e repito outra vez'

% Remoção de espaços:
s = sprintf(' 123 ');
sd = deblank(s);      % Remove do fim: '123'
st = strtrim(s);      % Remove dos extremos: '123'

% Conversão maiúsculas/minúsculas:
s = 'Olá. Bom dia.';
sM = upper(s);        % 'OLÁ. BOM DIA.'
sm = lower(s);        % 'olá. bom dia.'

% Comparação:
s1 = 'Olá';
s2 = 'OLÁ';
strcmp(s1, s2)        % 0 (false - são diferentes)
strncmp(s1, s2, 1)    % 1 (true - primeiro caracter igual)
strcmpi(s1, s2)       % 1 (true - ignora maiúsculas/minúsculas)

% Substituição:
strrep(strrep('um, vinte e um', 'um', '1'), 'vinte e ', '2');
% ans = '1, 21'

% Procura:
strfind('um, vinte e um, trinta e um', 'um')
% ans = [1 13 26]

% Decomposição:
[inicio, resto] = strtok('12,3 4', ', ');
% inicio = '1'
% resto = ',3 4'
```
[Exemplos de ][2]

**Predicados para Strings:**

```matlab
s = 'a 1 b 2';
ischar(s)             % 1 (true)
isspace(s)            % [0 1 0 1 0 1 0] (identifica espaços)
isletter(s)           % [1 0 0 0 1 0 0] (identifica letras)
```
[Exemplo de ][2]

### 5.6 Grficos Avançados

**Configuração Detalhada:**

```matlab
% Exemplo completo:
x = linspace(0, pi, 101);    % 101 pontos (número ímpar)
y = sin(x);

plot(x, y, '-square');       % Linha contínua com marcadores quadrados
axis([0 pi 0 1]);            % [xmin xmax ymin ymax]
xlabel('Hora');
ylabel('Temperatura');
title('Temperatura média horária');
legend('Temperatura', 'Location', 'best');
grid on;
```

**Múltiplos Gráficos:**

```matlab
% Gráficos separados:
x1 = linspace(0, pi, 11);
y1 = sin(x1);

figure;    % Nova janela
plot(x1, y1);
title('11 pontos');

x2 = linspace(0, pi, 101);
y2 = sin(x2);

figure;
plot(x2, y2);
title('101 pontos');
```

### 5.7 Erros de Programação (Bugs)

**Tipos de Erros:**

1. **Erros de Sintaxe:** Quando o interpretador não consegue traduzir o código fonte. No MATLAB, a execução aborta.[2]

```matlab
5 = a    % Erro: expressão à esquerda não é alvo válido
```

2. **Erros de Execução (Runtime Errors):** Quando o computador não consegue executar o código, apesar de ter sido traduzido.[2]

```matlab
v = [1.23, 2.34, 3.45];
for i = 1:4              % Deveria ser 1:length(v)
    disp(v(i));
end
% Erro: Attempted to access v(4); index out of bounds
```
[Exemplo de ][2]

3. **Erros de Semntica ou Lógica:** Execução decorre sem problemas, mas resultados estão errados. MATLAB não detecta.[2]

```matlab
receita = 30152.04;
despesa = 19976.11;
lucro = despesa - receita;    % Deveria ser receita - despesa
```
[Exemplo de ][2]

4. **Erros de Aproximação:** Tipo especial de erros semânticos que podem nunca ser detectados.[2]

```matlab
sin(pi)              % ans = 1.2246e-16 (deveria ser 0)
0.6 - 0.5 - 0.1      % ans = 2.7756e-17 (deveria ser 0)
```
[Exemplos de ][2]

### 5.8 Depuração de Erros (Debugging)

**Técnicas de Depuração:**

1. **Monitorizão (Tracing):**
   - Usando comando `echo` para mostrar execução[2]
   - Incluindo impressões temporárias no código[2]

2. **Execução com Breakpoints:**
   - Interface gráfica do MATLAB[2]
   - Comandos `dbstop`, `dbcont`, `dbquit`[2]

3. **Function Stubs:** Versões simplificadas das funções[2]

4. **Clulas de Código:** Divisão do script em secções testáveis[2]

### Exercícios Práticos - Semana 5

**Problema 1 (de ):** Função converte:[3]

```matlab
% converte.m
function m = converte(frase)
% converte - Extrai letras iniciais de cada palavra.

    palavra = frase;
    m = '';
    
    while ~isempty(palavra)
        [palavra, resto] = strtok(palavra);
        if ~isempty(palavra)
            m = [m palavra(1)];
        end
        palavra = resto;
    end
end

% Teste:
% frase = 'Maria acha importante ler';
% m = converte(frase)
% m = 'Mail'
```

**Problema 2 (de ):** Função para obter inteiro positivo:[3]

```matlab
% obtemInteiroPositivo.m
function valor = obtemInteiroPositivo
% obtemInteiroPositivo - Obtém inteiro positivo do utilizador.
%   Garante que o utilizador introduz inteiro maior que zero.

    valor = input('Introduza um inteiro maior que zero: ');
    
    while valor <= 0 || valor ~= fix(valor)
        disp('Erro: deve ser inteiro maior que zero!');
        valor = input('Introduza um inteiro maior que zero: ');
    end
end
```

**Problema 3 (de ):** Função para gráfico de empréstimo:[3]

```matlab
% evolucaoEmprestimo.m
function evolucaoEmprestimo(capital, taxa, duracaoMax)
% evolucaoEmprestimo - Mostra evolução de valor a pagar.
%   V = E * (1 + t)^n

    anos = 1:duracaoMax;
    valores = capital * (1 + taxa).^anos;
    
    plot(anos, valores, '-o');
    xlabel('Duração do empréstimo (anos)');
    ylabel('Valor acumulado (€)');
    title('Evolução do valor a pagar');
    grid on;
end
```

## Semana 6: Estruturas de Dados e Ficheiros

### 6.1 Tipos de Estruturas de Dados

**Dados Estruturados:** Variáveis que armazenam mais de um valor. Tipos principais em MATLAB:[2]

| Tipo | Descrição | Acesso |
|------|-----------|--------|
| Array | Valores de um só tipo | Indexação numérica |
| Array de células (cell) | Valores de qualquer tipo | Indexação numérica |
| Estrutura (struct) | Valores de qualquer tipo | Identificadores (campos) |

[Tabela baseada em ][2]

### 6.2 Arrays de Células

**Array de Células:** Array cujos elementos são todos do tipo especial `cell` (célula). Uma célula pode conter valores de qualquer tipo.[2]

**Criação - Concatenação de Contedo:**

```matlab
% Usando chavetas {}:
mcel = {[1:2:10], 'Olá Mundo!'; [12], true};
% mcel = 
%   [1x5 double]    'Olá Mundo!'
%   [12]            [1]

whos mcel
% Name  Size  Bytes  Class    Attributes
% mcel  2x2   517    cell
```
[Exemplo de ][2]

**Acesso ao Contedo:**

```matlab
% Criação:
vcel = cell(1,3);      % Cria 3 células vazias

% Atribuição (usando chavetas):
vcel{1} = [1:2:10];    % Coloca double dentro da célula
vcel{2} = 'a';         % Coloca char dentro da célula
vcel{3} = true;
% vcel = 
%   [1x5 double]    'a'    [1]

% Acesso (retorna sempre vector linha):
[x1 x2] = mcel{:,1};
% x1 = [1 3 5 7 9]
% x2 = 12

% Combinação de notações:
mcel{1,1}(2:3)         % ans = [3 5]
```
[Exemplos de ][2]

**Arrays de Células enquanto Arrays:**

```matlab
mcel = {[1:2:10], 'Olá Mundo!'; [12], true};
vcel = mcel(1,:);      % Copia primeira linha (células, não conteúdo)

vcel{3} = 'Tudo bem?';
% vcel = 
%   [1x5 double]    'Olá Mundo!'    'Tudo bem?'

vcel{1} = vcel{2};
% vcel = 
%   'Olá Mundo!'    'Olá Mundo!'    'Tudo bem?'
```
[Exemplos de ][2]

**Arrays de Células de Strings:**

```matlab
% Criação:
palavrasCell = {'Olá Mundo', 'Era uma vez', 'Aleluia'};

% Ordenação:
sort(palavrasCell)
% ans = 'Aleluia'    'Era uma vez'    'Olá Mundo'
```
[Exemplo de ][2]

### 6.3 Estruturas (struct)

**Estrutura:** Tipo de dados que permite armazenar numa só varivel vários elementos (campos), cada um com seu nome e valor. Diferentes campos podem ter valores de diferentes tipos.[2]

**Sintaxe Ponto:** `nome_da_variavel_struct.nome_do_campo`[2]

**Criao:**

```matlab
% Método 1 - Função struct:
aluno1 = struct('nome', 'Ana Luísa', 'numero', 70123, ...
                'datanasc', '2-Mar-1994');
% aluno1 = 
%     nome: 'Ana Luísa'
%   numero: 70123
% datanasc: '2-Mar-1994'

whos aluno1
% Name     Size  Bytes  Class     Attributes
% aluno1   1x1   574    struct

% Método 2 - Atribuindo valor a um campo:
aluno2.nome = 'Carlos';
aluno2.datanasc = '17-Ago-1994';
aluno2.numero = 70321;
```
[Exemplos de ][2]

**Manipulação de Estruturas:**

```matlab
% Visualizar conteúdo:
disp(aluno1);
disp(aluno1.nome);

% Remover campo:
aluno1A = rmfield(aluno1, 'datanasc');    % Cria nova struct
% aluno1A = 
%     nome: 'Ana Luísa'
%   numero: 70123

aluno1 = rmfield(aluno1, 'numero');       % Altera a struct original

% Predicados:
isstruct(aluno1)            % 1 (true - é struct)
isfield(aluno1, 'numero')   % 1 (true - tem o campo)

% Obter nomes de campos:
fieldnames(aluno1)
% ans = 
%     'nome'
%     'datanasc'
```
[Exemplos de ][2]

### 6.4 Arrays de Estruturas

**Criação com repmat:**

```matlab
% Criar 30 elementos idênticos:
turma1 = repmat(struct('nome', 'Vazio', 'numero', 0, ...
                       'datanasc', 'Dia-Mês-Ano'), 1, 30);
% turma1 = 
%   1x30 struct array with fields:
%     nome
%     numero
%     datanasc
```
[Exemplo de ][2]

**Acesso:**

```matlab
aluno = struct('nome', 'Vazio', 'numero', 0, 'datanasc', 'Dia-Mês-Ano');
turma1 = repmat(aluno, 1, 30);

turma1(end).nome = 'José Maria';

disp(turma1(30));
% nome: 'José Maria'
% numero: 0
% datanasc: 'Dia-Mês-Ano'
```
[Exemplo de ][2]

### 6.5 Entrada/Saída com Ficheiros de Texto

**Abertura e Fecho de Ligações:**

```matlab
% fopen - Abertura:
ligleitura = fopen('naoexisto.txt', 'r');    % Para leitura
% ligleitura = -1 (erro - ficheiro não existe)

ligleitura = fopen('euexisto.txt');          % Alternativa para leitura
% ligleitura = 3 (identificador da ligação)

ligescrita = fopen('saida.txt', 'w');        % Para escrita
ligadicionar = fopen('saida2.txt', 'a');     % Para adicionar

% fclose - Fecho:
fid = fopen('dados.dat');
fecho = fclose(fid);
% fecho = 0 (sucesso) ou -1 (erro)

fcloseall;    % Fecha todas as ligações abertas
```
[Exemplos de ][2]

**Leitura Linha a Linha:**

Pseudo-código genérico:[2]
```
Tenta abrir o ficheiro (estabelecer uma ligação de leitura)
Se o ficheiro foi aberto
    Enquanto não for alcançado o fim do ficheiro
        Lê uma linha para dentro de uma variável string
        Extrai valores a partir do contedo dessa varivel
        Processa esses valores
    Fecha a ligação
Senão
    Age em conformidade (depende de haver ou não interactividade)
```

**Exemplo - Contar Linhas:**

```matlab
% contalinhas.m
function k = contalinhas(nomef)
% contalinhas - Número de linhas num ficheiro, ou -1 se não abre.

    fid = fopen(nomef);
    
    if fid ~= -1
        k = 0;
        while ~feof(fid)
            k = k + 1;
            fgetl(fid);    % Em geral: linha = fgetl(fid);
        end
        fclose(fid);
    else
        k = -1;
    end
end
```
[Exemplo de ][2]

**Leitura Formatada com fscanf:**

```matlab
% notas.dat contém:
% 70987, 14.1
% 72111, 16.5
% 70988, 15.6

fid = fopen('notas.dat');

% Ler tudo para vector coluna:
dados = fscanf(fid, '%d,%f');
% dados = [70987; 14.1; 72111; 16.5; 70988; 15.6]

% Ler tudo para matriz 2xN:
dados = fscanf(fid, '%d,%f', [2 Inf]);
% dados = [70987  72111  70988
%          14.1   16.5   15.6]

fclose(fid);
```
[Exemplos de ][2]

**Leitura Formatada com textscan:**

```matlab
fid = fopen('notas.dat');

% Ler tudo para cell array:
dados = textscan(fid, '%d,%f');
% dados = {[3x1 int32], [3x1 double]}

% Ler todo o formato 1 vez:
dados = textscan(fid, '%d,%f', 1);
% dados = {70987, 14.1}

fclose(fid);
```
[Exemplos de ][2]

**Escrita Formatada com fprintf:**

```matlab
fin = fopen('notas.dat');
dados = textscan(fin, '%d,%f');
fclose(fin);

fout = fopen('notas2.dat', 'w');
for i = 1:length(dados{1})
    fprintf(fout, '%d, %.1f\n', dados{1}(i), dados{2}(i));
end
fclose(fout);
```
[Exemplo de ][2]

### 6.6 Ficheiros .mat (Binários)

**Comandos save e load:**

```matlab
% Criar variáveis:
a = 1;
b = 2;
c = 3;

% Guardar todas as variáveis:
save dados                    % Cria dados.mat

% Verificar conteúdo:
who -file dados
% Your variables are: a b c

% Guardar variáveis específicas:
s1 = 'teste1';
save dados s1                 % Cria dados.mat só com s1

% Adicionar ou substituir:
s2 = 'teste2';
save dados -append s1 s2      % Acrescenta/substitui s1 e s2

% Carregar:
clear
load dados s1 s2              % Carrega s1 e s2 para o workspace

% Carregar tudo:
clear
load dados                    % Carrega todas as variáveis
```
[Exemplos de ][2]

### Exercícios Práticos - Semana 6

**Problema 1 (de ):** Gerador de frases aleatórias:[3]

```matlab
% Script para gerar frases aleatórias:
clc, clear

nomes = {'Maria', 'João', 'Carlota'};
verbos = {'come', 'gosta de'};
substantivos = {'caracóis', 'peixes-aranha', 'minhocas'};

% Escolher aleatoriamente:
nome_esc = nomes{randi(length(nomes))};
verbo_esc = verbos{randi(length(verbos))};
subst_esc = substantivos{randi(length(substantivos))};

fprintf('%s %s %s.\n', nome_esc, verbo_esc, subst_esc);
```

**Problema 2 (de ):** Número complexo com estrutura:[3]

```matlab
% numComplexoEstrutura.m
clc, clear

numComplexo.real = input('Introduza a parte real: ');
numComplexo.imag = input('Introduza a parte imaginária: ');

fprintf('O número complexo é %.1f + i%.1f\n', ...
        numComplexo.real, numComplexo.imag);
```

**Problema 3 (de ):** Modularização com funções:[3]

```matlab
% numComplexoModular.m (script)
clc, clear
nc = obtemNumeroComplexo;
mostraNumeroComplexo(nc);

% obtemNumeroComplexo.m (função)
function nc = obtemNumeroComplexo
    nc.real = input('Introduza a parte real: ');
    nc.imag = input('Introduza a parte imaginária: ');
end

% mostraNumeroComplexo.m (função)
function mostraNumeroComplexo(nc)
    fprintf('O número complexo é %.1f + i%.1f\n', nc.real, nc.imag);
end
```

**Problema 2 (de  - Ficheiros):** Ler e processar ficheiro:[3]

```matlab
% lerPacientesPesos.m
clc, clear

fid = fopen('pacientesPesos.dat');

if fid == -1
    disp('Erro: não foi possível abrir o ficheiro.');
else
    somaPesos = 0;
    nPacientes = 0;
    
    while ~feof(fid)
        linha = fgetl(fid);
        if ~ischar(linha)
            break;    % Fim do ficheiro
        end
        
        % Decomposição:
        [primeiroNome, resto] = strtok(linha);
        [ultimoNome, resto] = strtok(resto);
        peso = str2num(strtrim(resto));
        
        fprintf('%s, %s %.1f\n', ultimoNome, primeiroNome, peso);
        
        somaPesos = somaPesos + peso;
        nPacientes = nPacientes + 1;
    end
    
    fprintf('\nPeso médio: %.1f kg\n', somaPesos / nPacientes);
    fclose(fid);
end
```

## Preparação para a Ficha 2

### Análise da Ficha 2 - Tipo

**Enunciado (de ):**[1]

Desenvolva uma função `Func` e uma subfunção `Sub`.

**Sub:** 
- Recebe um número
- Devolve (retorna) um número
- Valor devolvido = 1/3 do valor recebido se este for > 100
- Caso contrário = 1/2 do valor recebido

**Func:**
- Recebe um inteiro superior a zero e um real
- Devolve um vector linha com reais
- Invoca Sub tantas vezes quanto o inteiro recebido
- Na primeira invocação passa o real recebido
- Em cada invocação seguinte passa o valor devolvido por Sub na invocação anterior
- Devolve vector com todos os valores provenientes de Sub, ordenados do último para o primeiro (ordem inversa)

**Nota:** Não deve utilizar funções de entrada ou de saída (fprintf, disp, input).[1]

### Solução Passo-a-Passo

**Passo 1 - Compreender os Requisitos:**

1. **Subfunção Sub:**
   - Input: número (real ou inteiro)
   - Output: número
   - Lógica condicional baseada em valor > 100

2. **Função Principal Func:**
   - Inputs: inteiro positivo (n), real (valor_inicial)
   - Output: vector linha de reais
   - Iteração: n chamadas a Sub
   - Armazenamento: valores retornados por Sub
   - Inversão: ordenação reversa do vector

**Passo 2 - Implementação da Subfunção:**

```matlab
function resultado = Sub(numero)
% Sub - Calcula resultado baseado no valor recebido.
%   Se numero > 100: retorna numero/3
%   Caso contrário: retorna numero/2

    if numero > 100
        resultado = numero / 3;
    else
        resultado = numero / 2;
    end
end
```

**Passo 3 - Implementação da Função Principal:**

```matlab
function vetor = Func(n, valorInicial)
% Func - Processa valor através de n iterações de Sub.
%   Recebe inteiro positivo n e real valorInicial.
%   Retorna vector linha com valores processados em ordem inversa.

    % Pr-alocação do vector (boa prática):
    vetor = zeros(1, n);
    
    % Primeira iteração:
    valorAtual = valorInicial;
    vetor(1) = Sub(valorAtual);
    
    % Iterações seguintes:
    for i = 2:n
        valorAtual = vetor(i-1);    % Usa valor anterior
        vetor(i) = Sub(valorAtual);
    end
    
    % Inverter ordem:
    vetor = vetor(end:-1:1);
    
    % Subfunção Sub (função local):
    function resultado = Sub(numero)
        if numero > 100
            resultado = numero / 3;
        else
            resultado = numero / 2;
        end
    end
end
```

**Passo 4 - Teste da Solução:**

```matlab
% Teste 1:
resultado1 = Func(3, 150);
% Iteração 1: Sub(150) = 150/3 = 50
% Iteração 2: Sub(50) = 50/2 = 25
% Iteração 3: Sub(25) = 25/2 = 12.5
% Vector original: [50, 25, 12.5]
% Vector invertido: [12.5, 25, 50]

% Teste 2:
resultado2 = Func(4, 200);
% Iteração 1: Sub(200) = 200/3 = 66.6667
% Iteração 2: Sub(66.6667) = 66.6667/2 = 33.3333
% Iteração 3: Sub(33.3333) = 33.3333/2 = 16.6667
% Iteração 4: Sub(16.6667) = 16.6667/2 = 8.3333
% Vector invertido: [8.3333, 16.6667, 33.3333, 66.6667]

% Teste 3:
resultado3 = Func(1, 50);
% Iteração 1: Sub(50) = 50/2 = 25
% Vector: [25]
```

### Conceitos-Chave da Ficha 2

**Conceitos Testados:**
1. **Funções locais (subfunções):** Sub definida dentro de Func[1][2]
2. **Instruções de selecção:** if-else para lógica condicional[2]
3. **Iteração:** for loop para n chamadas[2]
4. **Vectores:** criação, pr-alocação, manipulação[2]
5. **Inversão de ordem:** usando indexação `end:-1:1`[2]
6. **Encapsulamento:** sem I/O dentro da função[1]

### Dicas para o Exame

**1. Leitura Cuidadosa:**
- Ler enunciado múltiplas vezes
- Identificar todas as restrições (ex: "não usar fprintf")[1]
- Distinguir entre função principal e subfunções[2]

**2. Estruturação:**
- Começar pela subfunção mais simples
- Depois implementar função principal
- Testar cada componente separadamente

**3. Boas Práticas:**
- Comentários claros explicando a lógica[2]
- Pr-alocação de vectores quando tamanho conhecido[2]
- Nomes de variáveis descritivos
- Inicialização apropriada de variáveis[2]

**4. Validação:**
- Testar com valores limites (ex: n=1, valor > 100, valor ≤ 100)
- Verificar casos extremos
- Confirmar que vector está na ordem correta

**5. Tempo de Gestão:**
- Não perder tempo com I/O se não pedido
- Focar na lógica central
- Deixar tempo para verificação final

## Resumo dos Conceitos Fundamentais por Semana

### Semana 1 - Conceitos Base
- Variáveis e tipos de dados (double, int, char, logical)[2]
- Operadores e precedência[2]
- Funções pré-definidas (sin, abs, fix, floor, ceil, round)[2]
- Expressões lógicas e predicados[2]
- Números pseudo-aleatórios (rand, randi, randn)[2]
- Códigos ASCII[2]

### Semana 2 - Arrays
- Vectores (linha e coluna)[2]
- Operador dois pontos[2]
- Funções linspace e logspace[2]
- Matrizes (criação, consulta, modificação)[2]
- Funções para arrays (min, max, sum, prod, cumsum)[2]
- Operações elemento a elemento (.*  ./  .^)[2]
- Vectores lógicos e indexação lógica[2]

### Semana 3 - Scripts e Funções
- Scripts (ficheiros-M)[2]
- Entrada/saída interativa (input, disp, fprintf)[2]
- Gráficos 2D (plot)[2]
- Ficheiros (save, load)[2]
- Definição de funções[2]
- Variáveis locais e âmbito[2]
- Tempo de vida de variáveis[2]

### Semana 4 - Controlo de Fluxo
- Instruções de selecção (if, if-else, if-elseif-else)[2]
- Instrução switch[2]
- Função menu[2]
- Instrução for[2]
- Inicialização e pré-alocação[2]
- Ciclos embebidos[2]
- Instrução while[2]
- Vectorização[2]

### Semana 5 - Programação Modular
- Decomposição top-down[2]
- Retorno múltiplo[2]
- Funções locais (subfunções)[2]
- Programas com menu[2]
- Manipulação de strings[2]
- Erros de programação (sintaxe, execução, semântica)[2]
- Depuração (debugging)[2]

### Semana 6 - Estruturas de Dados
- Arrays de células (cell)[2]
- Estruturas (struct)[2]
- Arrays de estruturas[2]
- Entrada/saída com ficheiros de texto[2]
- Leitura linha a linha (fgetl, fgets)[2]
- Leitura formatada (fscanf, textscan)[2]
- Escrita formatada (fprintf)[2]
- Ficheiros .mat (save, load)[2]

## Fontes Citadas

 ficha2_tipo.pdf - Enunciado da Ficha 2 - Tipo[1]
 Aulas-Teoricas.pdf - Material teórico completo do curso (Capítulos 1-9)[2]
 Problemas-25-26.pdf - Problemas práticos das aulas (Semanas 1-6)[3]

[1](https://ppl-ai-file-upload.s3.amazonaws.com/web/direct-files/attachments/145419413/a7bd84df-491d-4ced-98aa-ca36828ebccb/ficha2_tipo.pdf)
[2](https://ppl-ai-file-upload.s3.amazonaws.com/web/direct-files/attachments/145419413/051573cd-4fa2-4c37-bb4c-32928eeb418d/Aulas-Teoricas.pdf)
[3](https://ppl-ai-file-upload.s3.amazonaws.com/web/direct-files/attachments/145419413/b720d96e-c043-44b4-bc5f-7650cf747a2c/Problemas-25-26.pdf)
