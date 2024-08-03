---
jupyter:
  kernelspec:
    display_name: Octave
    language: octave
    name: octave
  language_info:
    file_extension: .m
    help_links:
    - text: GNU Octave
      url: "https://www.gnu.org/software/octave/support.html"
    - text: Octave Kernel
      url: "https://github.com/Calysto/octave_kernel"
    - text: MetaKernel Magics
      url: "https://metakernel.readthedocs.io/en/latest/source/README.html"
    mimetype: text/x-octave
    name: octave
    version: 6.4.0
  nbformat: 4
  nbformat_minor: 5
---

::: {#c5aad8a9-1c20-48aa-9bf2-cf0a21dfc5a7 .cell .markdown}
# Matemática e computação numérica com Octave
:::

::: {#adb0ab87-9801-4ca5-808e-b06a99a9bf4a .cell .markdown}
## Vetores
:::

::: {#6b76451f-cdfc-4db8-8d04-60813ffab77d .cell .markdown}
Um vetor é um conjunto unidimensional e finito de elementos homogêneos.
:::

::: {#ad1d962c-0577-43f4-93ec-fdb11544ce50 .cell .markdown}
*Podem ser definidos mediante a disposição de elementos entre colchetes,
separados por espaços:*
:::

::: {#290f1986-6829-4ba4-bfbe-95c7e6129ed6 .cell .code execution_count="58"}
``` octave
v1 = [1 2 3 4 5]; 
disp(v1); 
```

::: {.output .stream .stdout}
       1   2   3   4   5
:::
:::

::: {#0fa36df7-612f-4385-ae6c-d916558f4335 .cell .markdown}
*Ou podem ser definidos mediante a disposição de elementos entre
colchetes, separados por vírgula:*
:::

::: {#583a0ae9-9178-457c-8884-7a669c70df1b .cell .code execution_count="59"}
``` octave
v2 = [1, 2, 3, 4, 5]; 
disp(v2); 
```

::: {.output .stream .stdout}
       1   2   3   4   5
:::
:::

::: {#c07868e8-5b78-4bef-9b4d-866cbe5c567a .cell .markdown}
*Nas duas maneiras anteriormente citadas, o vetor será disposto
horizontalmente.
Caso queira dispô-lo verticalmente, separe os elementos com ponto e
vírgula:*
:::

::: {#cc2270b9-f707-406e-ab2e-27b5d1f75c7f .cell .code execution_count="60"}
``` octave
v3 = [1; 2; 3; 4; 5]; 
disp(v3); 
```

::: {.output .stream .stdout}
       1
       2
       3
       4
       5
:::
:::

::: {#35d87203-4a53-406a-9abb-891b9d582606 .cell .markdown}
*Ou insira o sinal para retornar a transposta do vetor, após o colchete
de fechamento:*
:::

::: {#fc5c4195-82a6-46e4-af34-afe4da899446 .cell .code execution_count="61"}
``` octave
v4 = [1 2 3 4 5]'; 
disp(v4); 
```

::: {.output .stream .stdout}
       1
       2
       3
       4
       5
:::
:::

::: {#f667adaf-f10c-47a5-9927-590d05417360 .cell .markdown}
### Funções integradas
:::

::: {#8205ec16-c562-48e4-95e2-bf8052f1f6b4 .cell .markdown}
O Octave fornece uma função integrada para a criação de vetores, com N
elementos, situados entre x1 e x2:
:::

::: {#169b90f7-70a9-42bb-9943-b3bc1beed7a7 .cell .code execution_count="62"}
``` octave
v = linspace(0,1,5) 
```

::: {.output .stream .stdout}
    v =

            0   0.2500   0.5000   0.7500   1.0000
:::
:::

::: {#7816ab4c-cbda-41cf-a684-62695d17c5ff .cell .markdown}
## Matrizes
:::

::: {#012cd821-68d3-4d40-9c2b-28f8a3fa5d4b .cell .markdown}
Matriz é um conjunto de elementos finitos e homogêneos de duas ou mais
dimensões.
:::

::: {#07ebb337-d54c-410a-be17-70184b0cad77 .cell .code execution_count="63"}
``` octave
m1 = [1, 2, 3; 4, 5, 6; 7, 8, 9]
```

::: {.output .stream .stdout}
    m1 =

       1   2   3
       4   5   6
       7   8   9
:::
:::

::: {#4ad8478a-cdf0-4f9a-adee-fd0674b8da66 .cell .markdown}
Imagine matrizes multidimensionais como folhas sobrepostas. Para criar
uma matriz de 3 ou mais dimensões, basta adicionar uma nova folha ou
página.
:::

::: {#e481ad2b-5954-4dbd-821d-ac1c9aa4f7b3 .cell .code execution_count="64"}
``` octave
m1(:,:,2) = [10 11 12; 13 14 15; 16 17 18]
```

::: {.output .stream .stdout}
    m1 =

    ans(:,:,1) =

       1   2   3
       4   5   6
       7   8   9

    ans(:,:,2) =

       10   11   12
       13   14   15
       16   17   18
:::
:::

::: {#6df4d357-ccb1-4deb-ae8e-c057bd8aad00 .cell .code execution_count="65"}
``` octave
m1(:,:,3) = [19 20 21; 22 23 24; 25 26 27]
```

::: {.output .stream .stdout}
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
:::
:::

::: {#681a7443-180e-4522-89d5-b83879a5c46d .cell .markdown}
### Funções integradas {#funções-integradas}
:::

::: {#8d74b536-1cea-4b10-abad-6f088853b044 .cell .markdown}
O Octave fornece um conjunto de funções integradas para a criação de
matrizes:
:::

::: {#c8b43d2d-d5c3-4f03-8e51-89d5d25e2c06 .cell .code execution_count="66"}
``` octave
z = zeros(5,5)
```

::: {.output .stream .stdout}
    z =

       0   0   0   0   0
       0   0   0   0   0
       0   0   0   0   0
       0   0   0   0   0
       0   0   0   0   0
:::
:::

::: {#31519e51-a4cd-44f2-bf65-88d77c23dc53 .cell .code execution_count="67"}
``` octave
o = ones(5,5)
```

::: {.output .stream .stdout}
    o =

       1   1   1   1   1
       1   1   1   1   1
       1   1   1   1   1
       1   1   1   1   1
       1   1   1   1   1
:::
:::

::: {#5b973f2f-4b73-4e15-a557-186c4025dfbd .cell .code execution_count="68"}
``` octave
y = eye(5)
```

::: {.output .stream .stdout}
    y =

    Diagonal Matrix

       1   0   0   0   0
       0   1   0   0   0
       0   0   1   0   0
       0   0   0   1   0
       0   0   0   0   1
:::
:::

::: {#f20c38f5-248f-4ca2-831a-0c0160b68f58 .cell .code execution_count="69"}
``` octave
r = rand(5)
```

::: {.output .stream .stdout}
    r =

       0.385047   0.292366   0.028219   0.867233   0.409900
       0.125048   0.873449   0.488807   0.276377   0.342604
       0.139062   0.945247   0.904489   0.865696   0.638804
       0.323826   0.212009   0.948337   0.938377   0.690524
       0.532686   0.883843   0.193867   0.308395   0.908661
:::
:::

::: {#7188d732-056d-4941-9c3d-b4267646af1c .cell .code execution_count="70"}
``` octave
d = diag(1:5)
```

::: {.output .stream .stdout}
    d =

    Diagonal Matrix

       1   0   0   0   0
       0   2   0   0   0
       0   0   3   0   0
       0   0   0   4   0
       0   0   0   0   5
:::
:::

::: {#9c3cda27-a9dd-4ee5-b8d6-1b60feed0183 .cell .markdown}
### Operações com matrizes
:::

::: {#b4fdec55-4bf2-4406-b9b7-5c0c72d99c4c .cell .code execution_count="71"}
``` octave
y(5,:) = [1 2 3 4 5]
```

::: {.output .stream .stdout}
    y =

       1   0   0   0   0
       0   1   0   0   0
       0   0   1   0   0
       0   0   0   1   0
       1   2   3   4   5
:::
:::

::: {#769fa324-b897-44b3-a921-82910955cc07 .cell .code execution_count="72"}
``` octave
y1 = y + 1
```

::: {.output .stream .stdout}
    y1 =

       2   1   1   1   1
       1   2   1   1   1
       1   1   2   1   1
       1   1   1   2   1
       2   3   4   5   6
:::
:::

::: {#fd0142e3-9df7-4231-9329-069e161f3f61 .cell .code execution_count="73"}
``` octave
y2 = y * 2
```

::: {.output .stream .stdout}
    y2 =

        2    0    0    0    0
        0    2    0    0    0
        0    0    2    0    0
        0    0    0    2    0
        2    4    6    8   10
:::
:::

::: {#63dea5f9-8bb8-4fc8-9454-19f536a41fa0 .cell .code execution_count="74"}
``` octave
y3 = y .* 2
```

::: {.output .stream .stdout}
    y3 =

        2    0    0    0    0
        0    2    0    0    0
        0    0    2    0    0
        0    0    0    2    0
        2    4    6    8   10
:::
:::

::: {#bd95fad5-7e37-4b63-9451-b7ee90842e0c .cell .code execution_count="75"}
``` octave
y4 = y ^ 2
```

::: {.output .stream .stdout}
    y4 =

        1    0    0    0    0
        0    1    0    0    0
        0    0    1    0    0
        0    0    0    1    0
        6   12   18   24   25
:::
:::

::: {#1579551f-9a4e-4a01-b1c9-832a7256bb6a .cell .code execution_count="76" scrolled="true"}
``` octave
y5 = y .^ 2
```

::: {.output .stream .stdout}
    y5 =

        1    0    0    0    0
        0    1    0    0    0
        0    0    1    0    0
        0    0    0    1    0
        1    4    9   16   25
:::
:::

::: {#b4b9158e-f6fa-4eb5-91c2-abe1d0e3b7d8 .cell .code execution_count="77"}
``` octave
R = reshape([1:12], 3,4)
```

::: {.output .stream .stdout}
    R =

        1    4    7   10
        2    5    8   11
        3    6    9   12
:::
:::

::: {#1ecf5a6c-f231-4871-b69b-5a47256bc950 .cell .code execution_count="78"}
``` octave
S = [2, 1, 4, 3; 1, 2, 3, 4; 4, 3, 2, 1]
```

::: {.output .stream .stdout}
    S =

       2   1   4   3
       1   2   3   4
       4   3   2   1
:::
:::

::: {#43530b44-2a55-4dc7-b64d-4ed4a2d234d5 .cell .code execution_count="79"}
``` octave
A = reshape([R], 4,3)
```

::: {.output .stream .stdout}
    A =

        1    5    9
        2    6   10
        3    7   11
        4    8   12
:::
:::

::: {#4e7cffc6-f7f4-4ec4-9894-fb8a154e17b5 .cell .code execution_count="80"}
``` octave
T = A * S
```

::: {.output .stream .stdout}
    T =

       43   38   37   32
       50   44   46   40
       57   50   55   48
       64   56   64   56
:::
:::

::: {#4c31b47d-504a-4bae-8031-581526094a37 .cell .code execution_count="81"}
``` octave
U = S * A
```

::: {.output .stream .stdout}
    U =

        28    68   108
        30    70   110
        20    60   100
:::
:::

::: {#8e6067a4-7e8d-4f39-8e5b-7665e6959a20 .cell .markdown}
### Concatenação de matrizes
:::

::: {#d33f24f7-e8be-4897-b4b9-baf13df9d79e .cell .markdown}
**Vertical**
:::

::: {#0554d2b0-ac5a-47a5-a2e7-ef47d3ff6a8b .cell .code execution_count="82"}
``` octave
concat_y = vertcat(R, S)
```

::: {.output .stream .stdout}
    concat_y =

        1    4    7   10
        2    5    8   11
        3    6    9   12
        2    1    4    3
        1    2    3    4
        4    3    2    1
:::
:::

::: {#3c1949d1-23cf-4f37-9236-c5b549c3fe66 .cell .markdown}
**Horizontal**
:::

::: {#7f3db79a-6e7d-4816-af45-295c38426433 .cell .code execution_count="83"}
``` octave
concat_x = horzcat(R, S)
```

::: {.output .stream .stdout}
    concat_x =

        1    4    7   10    2    1    4    3
        2    5    8   11    1    2    3    4
        3    6    9   12    4    3    2    1
:::
:::

::: {#e75f74f9-f4c9-4ea6-9886-e7618bf3bfb8 .cell .markdown}
### Arranjo de matrizes
:::

::: {#c01c3176-5df2-4dfb-854a-faab89027db2 .cell .code execution_count="84"}
``` octave
R
lr = fliplr (R) 
```

::: {.output .stream .stdout}
    R =

        1    4    7   10
        2    5    8   11
        3    6    9   12

    lr =

       10    7    4    1
       11    8    5    2
       12    9    6    3
:::
:::

::: {#cf50e1bc-b8f8-4e60-853b-d704d67ee343 .cell .code execution_count="85"}
``` octave
S
ud = flipud (S)
```

::: {.output .stream .stdout}
    S =

       2   1   4   3
       1   2   3   4
       4   3   2   1

    ud =

       4   3   2   1
       1   2   3   4
       2   1   4   3
:::
:::

::: {#15dfcabf-0515-4c74-8520-3a708354e4d7 .cell .code execution_count="86"}
``` octave
rot90(R)
rot90(S, -2)
```

::: {.output .stream .stdout}
    ans =

       10   11   12
        7    8    9
        4    5    6
        1    2    3

    ans =

       1   2   3   4
       4   3   2   1
       3   4   1   2
:::
:::

::: {#1943475f-8d49-4d80-be0a-192914511c8b .cell .markdown}
### Broadcasting
:::

::: {#f67b1237-d79c-4426-8e15-e0b08eda80b8 .cell .markdown}
Normalmente, as operações com matrizes são elemento a elemento; logo,
funcionam apenas com matrizes de mesmo tamanho. Entretanto, a partir da
versão 3.6.0, Octave permite operações com matrizes de tamanhos
diferentes, através do mecanismo de transformaçã denominado
*broadcasting*.
:::

::: {#6170092e-493a-47fc-858e-e90734b28f5d .cell .code execution_count="87"}
``` octave
b = [1 2 3;
     4 5 6;
     7 8 9];

p = [10 20 30];

q = x + y
```

::: {.output .stream .stdout}
    error: operator +: nonconformant arguments (op1 is 1x6, op2 is 5x5)
:::
:::

::: {#a2a5a775-c427-4f99-b00c-01e5973a245f .cell .markdown}
### Indexação
:::

::: {#7bbe2bb5-6f68-49c3-8483-edc47518ff20 .cell .code execution_count="88"}
``` octave
% Criamos uma matriz tridimensional
I = reshape (1:8, 2, 2, 2) 

% Selecionamos o quarto elemento da segunda folha
I(2,4)
```

::: {.output .stream .stdout}
    I =

    ans(:,:,1) =

       1   3
       2   4

    ans(:,:,2) =

       5   7
       6   8

    ans = 8
:::
:::

::: {#c174e6a7-805d-46e2-8e51-a43ef6475d99 .cell .markdown}
### Fatiamento
:::

::: {#483c5ff0-7fd4-4040-952e-9f24f4a81a35 .cell .code execution_count="89"}
``` octave
z
f1 = z(:,1:2)
f2 = z(:,2:end)
```

::: {.output .stream .stdout}
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
:::
:::

::: {#13c751e8-11be-4651-a196-3c0f35ac01b3 .cell .markdown}
## Intervalos
:::

::: {#bdc6c315-ef00-407e-99d1-a1c89a824139 .cell .markdown}
Intervalos são vetores cujos elementos são separados por
espaços.`<br>`{=html} Podemos definir sequências númericas da seguinte
maneira:`<br>`{=html} *a) atribuindo os valores das extremidades do
intervalo, inclusivos, separados por dois pontos;*
:::

::: {#a05bfbc7-ccde-4e29-be40-5bf82f8f927f .cell .code execution_count="90"}
``` octave
a = 0:11;
disp(a)
```

::: {.output .stream .stdout}
        0    1    2    3    4    5    6    7    8    9   10   11
:::
:::

::: {#a2a23913-d1f1-42cc-9964-d124fc0c4832 .cell .code execution_count="91"}
``` octave
size(a)
```

::: {.output .stream .stdout}
    ans =

        1   12
:::
:::

::: {#a4bd1227-61cd-4460-8b37-d227c2249049 .cell .code execution_count="92"}
``` octave
a1 = reshape(a,3,4)
```

::: {.output .stream .stdout}
    a1 =

        0    3    6    9
        1    4    7   10
        2    5    8   11
:::
:::

::: {#3f87cc9c-ed8c-4c3b-aa09-2a73b3469339 .cell .markdown}
**Observação**: nesse caso, temos uma sucessão numérica semelhante a uma
progressão de razão igual a 1.
:::

::: {#15b144c3-00f8-41ee-a466-e75c72729175 .cell .markdown}
*b) atribuindo explicitamente o valor da razão, entre o termo inicial e
final da sequência,
separados por dois pontos:*
:::

::: {#f29e985e-76bd-43b1-b722-9ebfe5262cea .cell .code execution_count="94"}
``` octave
b = 0 : 2 : 10;
disp(b)
```

::: {.output .stream .stdout}
        0    2    4    6    8   10
:::
:::

::: {#4345f518-256b-4ad1-a2fd-75da1b2e54f6 .cell .code execution_count="95"}
``` octave
x = 0:0.1:0.5;
disp(x)
```

::: {.output .stream .stdout}
             0    0.1000    0.2000    0.3000    0.4000    0.5000
:::
:::

::: {#a166c8c6-be6f-4ab6-b2d9-cf964eeba06d .cell .code execution_count="96"}
``` octave
y = [0:0.1:0.5];
disp(y)
```

::: {.output .stream .stdout}
            0   0.1000   0.2000   0.3000   0.4000   0.5000
:::
:::

::: {#4cbbf7b1-5931-4026-a368-b03bf22eab05 .cell .markdown}
### Funções integradas {#funções-integradas}
:::

::: {#123edf8b-1c67-464d-b2bd-48f340c31605 .cell .markdown}
A função booleana *isvector()* retorna 1 para *True* e 0 para *False*.
:::

::: {#5fc7a462-5076-42a8-9102-b1436d17a145 .cell .code execution_count="97"}
``` octave
isvector(a)
```

::: {.output .stream .stdout}
    ans = 1
:::
:::

::: {#7f3e8480-542d-4048-b51a-1fc1237d93d8 .cell .markdown}
A função *uintX()* converte a variável para o tipo de dados *uint*
(*unsigned integer type*), com o valor mínimo igual a 0, e o valor
máximo definido por *X*, armazenado com 8, 16, 32 ou 64 *bits*:
:::

::: {#0767b146-036e-48e4-a70c-5062efebd6bd .cell .code execution_count="98"}
``` octave
z = uint8(a);
z
whos a z
```

::: {.output .stream .stdout}
    z =

       0   1   2   3   4   5   6   7   8   9  10  11

    Variables visible from the current scope:

    variables in scope: top scope

       Attr Name        Size                     Bytes  Class
       ==== ====        ====                     =====  ===== 
            a           1x12                        24  double
            z           1x12                        12  uint8

    Total is 24 elements using 36 bytes
:::
:::

::: {#c5afa6f1-375d-4dc5-977c-5c324d6ac790 .cell .code execution_count="99"}
``` octave
m = uint16(a);
whos a z m
```

::: {.output .stream .stdout}
    Variables visible from the current scope:

    variables in scope: top scope

       Attr Name        Size                     Bytes  Class
       ==== ====        ====                     =====  ===== 
            a           1x12                        24  double
            z           1x12                        12  uint8
            m           1x12                        24  uint16

    Total is 36 elements using 60 bytes
:::
:::
