# Matemática e computação numérica com Octave

## Vetores

Um vetor é um conjunto unidimensional e finito de elementos homogêneos.

*Podem ser definidos mediante a disposição de elementos entre colchetes,
separados por espaços:*

``` octave
v1 = [1 2 3 4 5]; 
disp(v1); 
```


       1   2   3   4   5

*Ou podem ser definidos mediante a disposição de elementos entre
colchetes, separados por vírgula:*

``` octave
v2 = [1, 2, 3, 4, 5]; 
disp(v2); 
```


       1   2   3   4   5

*Nas duas maneiras anteriormente citadas, o vetor será disposto
horizontalmente.
Caso queira dispô-lo verticalmente, separe os elementos com ponto e
vírgula:*

``` octave
v3 = [1; 2; 3; 4; 5]; 
disp(v3); 
```


       1
       2
       3
       4
       5

*Ou insira o sinal para retornar a transposta do vetor, após o colchete
de fechamento:*

``` octave
v4 = [1 2 3 4 5]'; 
disp(v4); 
```


       1
       2
       3
       4
       5

### Funções integradas

O Octave fornece uma função integrada para a criação de vetores, com N
elementos, situados entre x1 e x2:

``` octave
v = linspace(0,1,5) 
```


    v =

            0   0.2500   0.5000   0.7500   1.0000

## Matrizes

Matriz é um conjunto de elementos finitos e homogêneos de duas ou mais
dimensões.

``` octave
m1 = [1, 2, 3; 4, 5, 6; 7, 8, 9]
```

    m1 =

       1   2   3
       4   5   6
       7   8   9

Imagine matrizes multidimensionais como folhas sobrepostas. Para criar
uma matriz de 3 ou mais dimensões, basta adicionar uma nova folha ou
página.

``` octave
m1(:,:,2) = [10 11 12; 13 14 15; 16 17 18]
```


    m1 =

    ans(:,:,1) =

       1   2   3
       4   5   6
       7   8   9

    ans(:,:,2) =

       10   11   12
       13   14   15
       16   17   18

``` octave
m1(:,:,3) = [19 20 21; 22 23 24; 25 26 27]
```


    m1 =

    ans(:,:,1) =

       1   2   3
       4   5   6
       7   8   9

    ans(:,:,2) =

       10   11   12
       13   14   15
       16   17   18

    ans(:,:,3) =

       19   20   21
       22   23   24
       25   26   27

### Funções integradas

O Octave fornece um conjunto de funções integradas para a criação de
matrizes:

``` octave
z = zeros(5,5)
```


    z =

       0   0   0   0   0
       0   0   0   0   0
       0   0   0   0   0
       0   0   0   0   0
       0   0   0   0   0

``` octave
o = ones(5,5)
```


    o =

       1   1   1   1   1
       1   1   1   1   1
       1   1   1   1   1
       1   1   1   1   1
       1   1   1   1   1

``` octave
y = eye(5)
```


    y =

    Diagonal Matrix

       1   0   0   0   0
       0   1   0   0   0
       0   0   1   0   0
       0   0   0   1   0
       0   0   0   0   1

``` octave
r = rand(5)
```


    r =

       0.385047   0.292366   0.028219   0.867233   0.409900
       0.125048   0.873449   0.488807   0.276377   0.342604
       0.139062   0.945247   0.904489   0.865696   0.638804
       0.323826   0.212009   0.948337   0.938377   0.690524
       0.532686   0.883843   0.193867   0.308395   0.908661

``` octave
d = diag(1:5)
```


    d =

    Diagonal Matrix

       1   0   0   0   0
       0   2   0   0   0
       0   0   3   0   0
       0   0   0   4   0
       0   0   0   0   5

### Operações com matrizes

``` octave
y(5,:) = [1 2 3 4 5]
```


    y =

       1   0   0   0   0
       0   1   0   0   0
       0   0   1   0   0
       0   0   0   1   0
       1   2   3   4   5

``` octave
y1 = y + 1
```


    y1 =

       2   1   1   1   1
       1   2   1   1   1
       1   1   2   1   1
       1   1   1   2   1
       2   3   4   5   6

``` octave
y2 = y * 2
```


    y2 =

        2    0    0    0    0
        0    2    0    0    0
        0    0    2    0    0
        0    0    0    2    0
        2    4    6    8   10

``` octave
y3 = y .* 2
```


    y3 =

        2    0    0    0    0
        0    2    0    0    0
        0    0    2    0    0
        0    0    0    2    0
        2    4    6    8   10

``` octave
y4 = y ^ 2
```


    y4 =

        1    0    0    0    0
        0    1    0    0    0
        0    0    1    0    0
        0    0    0    1    0
        6   12   18   24   25

``` octave
y5 = y .^ 2
```


    y5 =

        1    0    0    0    0
        0    1    0    0    0
        0    0    1    0    0
        0    0    0    1    0
        1    4    9   16   25

``` octave
R = reshape([1:12], 3,4)
```


    R =

        1    4    7   10
        2    5    8   11
        3    6    9   12

``` octave
S = [2, 1, 4, 3; 1, 2, 3, 4; 4, 3, 2, 1]
```


    S =

       2   1   4   3
       1   2   3   4
       4   3   2   1

``` octave
A = reshape([R], 4,3)
```


    A =

        1    5    9
        2    6   10
        3    7   11
        4    8   12

``` octave
T = A * S
```


    T =

       43   38   37   32
       50   44   46   40
       57   50   55   48
       64   56   64   56

``` octave
U = S * A
```


    U =

        28    68   108
        30    70   110
        20    60   100

### Concatenação de matrizes

**Vertical**

``` octave
concat_y = vertcat(R, S)
```


    concat_y =

        1    4    7   10
        2    5    8   11
        3    6    9   12
        2    1    4    3
        1    2    3    4
        4    3    2    1

**Horizontal**

``` octave
concat_x = horzcat(R, S)
```


    concat_x =

        1    4    7   10    2    1    4    3
        2    5    8   11    1    2    3    4
        3    6    9   12    4    3    2    1

### Arranjo de matrizes

``` octave
R
lr = fliplr (R) 
```


    R =

        1    4    7   10
        2    5    8   11
        3    6    9   12

    lr =

       10    7    4    1
       11    8    5    2
       12    9    6    3

``` octave
S
ud = flipud (S)
```


    S =

       2   1   4   3
       1   2   3   4
       4   3   2   1

    ud =

       4   3   2   1
       1   2   3   4
       2   1   4   3

``` octave
rot90(R)
rot90(S, -2)
```


    ans =

       10   11   12
        7    8    9
        4    5    6
        1    2    3

    ans =

       1   2   3   4
       4   3   2   1
       3   4   1   2

### Broadcasting

Normalmente, as operações com matrizes são elemento a elemento; logo,
funcionam apenas com matrizes de mesmo tamanho. Entretanto, a partir da
versão 3.6.0, Octave permite operações com matrizes de tamanhos
diferentes, através do mecanismo de transformação denominado
*broadcasting*.

``` octave
b = [1 2 3;
     4 5 6;
     7 8 9];

p = [10 20 30];

q = b + q
```
       q =

          11   22   33
          14   25   36
          17   28   39

    
### Indexação

``` octave
% Criamos uma matriz tridimensional
I = reshape (1:8, 2, 2, 2) 

% Selecionamos o quarto elemento da segunda folha
I(2,4)
```


    I =

    ans(:,:,1) =

       1   3
       2   4

    ans(:,:,2) =

       5   7
       6   8

    ans = 8

### Fatiamento

``` octave
z
f1 = z(:,1:2)
f2 = z(:,2:end)
```


    z =

       0   0   0   0   0
       0   0   0   0   0
       0   0   0   0   0
       0   0   0   0   0
       0   0   0   0   0

    f1 =

       0   0
       0   0
       0   0
       0   0
       0   0

    f2 =

       0   0   0   0
       0   0   0   0
       0   0   0   0
       0   0   0   0
       0   0   0   0

## Intervalos

Intervalos são vetores cujos elementos são separados por
espaços.<br>
Podemos definir sequências númericas da seguinte
maneira:<br>
*a) atribuindo os valores das extremidades do
intervalo, inclusivos, separados por dois pontos;*

``` octave
a = 0:11;
disp(a)
```


        0    1    2    3    4    5    6    7    8    9   10   11

``` octave
size(a)
```


    ans =

        1   12

``` octave
a1 = reshape(a,3,4)
```


    a1 =

        0    3    6    9
        1    4    7   10
        2    5    8   11

**Observação**: nesse caso, temos uma sucessão numérica semelhante a uma
progressão de razão igual a 1.

*b) atribuindo explicitamente o valor da razão, entre o termo inicial e
final da sequência,
separados por dois pontos:*

``` octave
b = 0 : 2 : 10;
disp(b)
```


        0    2    4    6    8   10

``` octave
x = 0:0.1:0.5;
disp(x)
```


             0    0.1000    0.2000    0.3000    0.4000    0.5000

``` octave
y = [0:0.1:0.5];
disp(y)
```


            0   0.1000   0.2000   0.3000   0.4000   0.5000

### Funções integradas

A função booleana *isvector()* retorna 1 para *True* e 0 para *False*.

``` octave
isvector(a)
```


    ans = 1

A função *uintX()* converte a variável para o tipo de dados *uint*
(*unsigned integer type*), com o valor mínimo igual a 0, e o valor
máximo definido por *X*, armazenado com 8, 16, 32 ou 64 *bits*:

``` octave
z = uint8(a);
z
whos a z
```


    z =

       0   1   2   3   4   5   6   7   8   9  10  11

    Variables visible from the current scope:

    variables in scope: top scope

       Attr Name        Size                     Bytes  Class
       ==== ====        ====                     =====  ===== 
            a           1x12                        24  double
            z           1x12                        12  uint8

    Total is 24 elements using 36 bytes

``` octave
m = uint16(a);
whos a z m
```


    Variables visible from the current scope:

    variables in scope: top scope

       Attr Name        Size                     Bytes  Class
       ==== ====        ====                     =====  ===== 
            a           1x12                        24  double
            z           1x12                        12  uint8
            m           1x12                        24  uint16

    Total is 36 elements using 60 bytes
