# RegExp

## Flags:
* **g** Acha 1 ou mais ocorrências
* **m** Continua percorrendo mesmo com quebra de linha


## Meta Caracter

### Começar `^`
Este parametro é para iniciar a seleção a partir do começo da string

**Exemplo:** `"Olá Mundo. Olá a todos".math(/^Olá/)`  <br>
**Resultado:** **Olá** Mundo. Olá a todos


### Terminar `$`
Este parametro é para começar a seleção a partir do final da string

**Exemplo:** `"Olá pessoas, Olá pessoas".math(/pessoas$/)`  <br>
**Resultado:** Olá pessoas, Olá **pessoas**


### Terminar `$`
Este parametro é para começar a seleção a partir do final da string

**Exemplo:** `"Olá pessoas, Olá pessoas".math(/pessoas$/)`  <br>
**Resultado:** Olá pessoas, Olá **pessoas**


### Limite de palavra `\b`
Especifica um limite de uma palavra. Indicando no começo, meio a palavra exata e no fim

**Exemplo:**  `"dialogo dia melodia diafragma dialeto radial bom-dia".math(/\bdia/g)` <br>
**Resultado:** **dia**logo **dia** melodia **dia**fragma **dia**leto radial bom-**dia**

**Exemplo:**  `"dialogo dia melodia diafragma dialeto radial bom-dia".math(/dia\b/g)` <br>
**Resultado:** dialogo **dia** melo**dia** diafragma dialeto radial bom-**dia**

**Exemplo:**  `"dialogo dia melodia diafragma dialeto radial bom-dia".math(/\bdia\b/g)` <br>
**Resultado:** dialogo **dia** melodia diafragma dialeto radial bom-**dia**

*vai capturar padrão especificado no inicio, final ou palavra exata, isso significa que é válido apenas para letras, números e o underline `([A-Za-z0-9_])`*


### Ponto `.`
Ele ira fazer que qualquer caractere antes, entre ou depois dele pode ser qualquer caractere

**Exemplo:**  `"Vocês ou Você devera fazer algo".math(/.fazer alg./g)` <br>
**Resultado:** Vocês ou Você devera **fazer alg**o


### Interrogação `?`
Ele ira fazer que o caractere anterior, pode ou não e existir

**Exemplo:**  `"Vocês ou Você devera fazer algo".math(/Vocês?/g)` <br>
**Resultado:** **Vocês** ou **Você** devera fazer algo





----
## Quantificadores

### Chaves `{}`
Você pode determinar um que o caractere anterior deve ter uma sequencia de 1 a 5 caracteres {min,max} 

**Exemplo:** `"Você vai ter muuuuuito poder".math(/mu{1,5}ito/g)` <br>
**Resultado:** Você vai ter **muuuuuito** poder

*Recomendado utilizar em situações declaradas como o minimo for 2 ou mais {2,max}*


### Asterisco `*`
Você pode determinar um que o caractere anterior deve ter uma sequencia ilimitada caracteres, Sem necessidade de o mesmo existir

**Exemplo:** `"Você vai ter muuuuuito poder".math(/mu*ito/g)` <br>
**Resultado:** Você vai ter **muuuuuito** poder


### Mais `+`
Você pode determinar um que o caractere anterior deve ter uma sequencia ilimitada caracteres, Com necessidade de o mesmo existir pelo menos 1 vez

**Exemplo:** `"Você vai ter muuuuuito poder".math(/mu+ito/g)` <br>
**Resultado:** Você vai ter **muuuuuito** poder


### Preguiçoso "Lazy" `*?`
Determina que o RegExp não tente força a continuação da expressão. Para usar você deve usar depois do caractere de quantificador `* + {1,2}` **?**

**Exemplo:** `"Você Você Você Você".math(/cê.*?/g)` <br>
**Resultado:** Vo**cê** Vo**cê** Vo**cê** Vo**cê**

*Usado para que o resultado fique separado em cada seleção*







----
## Conjuntos ou Grupo

### Conjunto `[]`
Usado para fazer conjuntos de caracteres para tal seleção

**Exemplo:**  `"Meu abacaxi ta sem gosto".math(/[acg]/g)`
**Resultado** Meu **a**b**aca**xi t**a** sem **g**osto

*Seleciona todos os caracteres que contem no conjunto. Pode ser utilizado o `[a-z]` para caracteres minusculos de `a` há `z`*


### Grupo `()`
Usado para fazer grupos para conjuntos ou com logicos para tal seleção

### Referenciar Grupos ja criados anteriormente  `\n`






----
## Logicos


### Ou `|`
Usado para selecionar um\|outro valor na seleção

**Exemplo:** `"Primeiro dedo, Segundo dedo, Terceiro dedo, ou mais dedos".math(/(Primeiro|Terceiro)\sdedo/)` <br>

**Resultado:** **Primeiro dedo**, Segundo dedo, Terceiro dedo, ou mais dedos <br>
**Resultado2:** Primeiro dedos, Segundo dedo, **Terceiro dedo**, ou mais dedos

*No resultado Seleciona o primeiro dedo ou o terceiro dedo. Lembrando que no segundo resultado o primeiro dedo recebeu o plural para dizer que n tinha na seleção*


### Negação `^`
Usado para negar algo dentro de um conjunto de caracteres

**Exemplo:**  `"Meu abacaxi ta sem gosto".math(/[^acg]/g)` <br>
**Resultado:** **Meu** a**b**aca**xi t**a **sem** g**osto**


### Se Positivo `?=`
Usado para verificar depois da seleção tem o conteudo expecificado, se o tal valor faz parte da seleção

**Exemplo:** `"Estou acordado, Estou dormindo, Estou sem sono".math(/Estou(?=\sacordado)/g)` <br>
**Resultado:** **Estou** acordado, Estou dormindo, Estou sem sono

*No resultado ele selecionou o `estou` que a palavra seguinte deve conter ` acordado`*


### Se Negativo `?!`
Usado para verificar depois da seleção se não tem o conteudo expecificado, se o tal valor não faz parte da seleção

**Exemplo:** `"Estou acordado, Estou dormindo, Estou sem sono".math(/Estou(?!\sacordado)/g)` <br>
**Resultado:** Estou acordado, **Estou** dormindo, **Estou** sem sono

*No resultado ele selecionou o `estou` que a palavra seguinte não conter ` acordado`*