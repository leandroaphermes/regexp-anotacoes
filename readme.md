# RegExp

### Flags:
* **g** Acha mais de 1 ocorrência



### Ponto .
Ele ira fazer que qualquer caractere antes, entre ou depois dele pode ser qualquer caractere

**Exemplo:**  `"Vocês ou Você devera fazer algo".math(/.fazer alg./g)` <br>
**Resultado:** Vocês ou Você devera **fazer alg**o

---
### Interrogação ?
Ele ira fazer que o caractere anterior, pode ou não e existir

**Exemplo:**  `"Vocês ou Você devera fazer algo".math(/Vocês?/)` <br>
**Resultado:** **Vocês** ou **Você** devera fazer algo

----
### Chaves {}
Você pode determinar um que o caractere anterior deve ter uma sequencia de 1 a 5 caracteres {min,max} 

**Exemplo:** `"Você vai ter muuuuuito poder".math(/mu{1,5}ito/)` <br>
**Resultado:** Você vai ter **muuuuuito** poder

*Recomendado utilizar em situações declaradas como o minimo for 2 ou mais {2,max}*

----
### Asterisco *
Você pode determinar um que o caractere anterior deve ter uma sequencia ilimitada caracteres, Sem necessidade de o mesmo existir

**Exemplo:** `"Você vai ter muuuuuito poder".math(/mu*ito/)` <br>
**Resultado:** Você vai ter **muuuuuito** poder

----
### Mais *
Você pode determinar um que o caractere anterior deve ter uma sequencia ilimitada caracteres, Com necessidade de o mesmo existir pelo menos 1 vez

**Exemplo:** `"Você vai ter muuuuuito poder".math(/mu+ito/)` <br>
**Resultado:** Você vai ter **muuuuuito** poder


