# Node

1\) Qual a diferença do operador `==` para o operador `===` em JavaScript?

 `==` operador de igualdade que não leva em consideração o tipo da variável
 `===` operador de igualdade que considera o tipo

1.1) Dê 2 exemplos de quando os operadores produziriam resultados diferentes

```js
'1' == 1 é verdadeiro
'1' === 1 é falso
```

---

2\) Qual recurso javascript é mais recomendado para tratar chamadas asíncronas?

Promisses

2.1) Justifique

Se um erro ocorre em uma requisição asíncrona não é possível capturar o erro, com as promisses é possível encapsular possibilitando maneiras de organizar os callbacks.

---

3\) Existem threads em Node?

Sim

3.1) Explique

Node.js é uma única linguagem encadeada que, em segundo plano, usa vários encadeamentos para executar código assíncrono.

O Node.js não é bloqueado, o que significa que todas as funções (callbacks) são delegadas ao loop de eventos e são (ou podem ser) executadas por threads diferentes. Isso é tratado pelo tempo de execução do Node.js

---

4\) Qual o resultado dos códigos a seguir?

4.1)
```js
function getUserByName(name) {
    return Promise.resolve({id: 1, name: name})
}

function getUserPhones(userId) {
    return Promise.resolve(['(31) 90900800', '(31) 08009090'])
}

getUserByName('jonh doe')
    .then(user => { 
        getUserPhones(user.id)
    })
    .then(user => console.log(user))
```

Indefinido, colocando return na frente de getUserPhones o resultado é:
[ '(31) 90900800', '(31) 08009090' ]

4.2)
```js
function getData(id) {
    return new Promise((resolve, reject) => {
        if (!id) {
            return reject(new Error('invalid'))
        }

        resolve({ foo: 'bar' })
    })
}

getData()
    .then(() => {
        console.log('first')
    }, () => {
        console.log('second')
    })
    .catch(() => {
        console.log('third')
    })
```

```
Retorna second.
Valor id é indefinido.
```

---

# PHP

1\) Qual a diferença do operador `==` para o operador `===` em PHP?

Assim como ocorreu em js o php não é uma linguagem fortemente tipada. == comopara os valores e === além de comparar os valores, compara os tipos das variáveis.

1.1) Dê 2 exemplos de quando os operadores produziriam resultados diferentes

```php
'1' != 1 resulta em falso
'1' !== resulta em verdadeiro
```

---

2\) Qual a função do apache ou nginx em uma aplicação PHP?

Nginx é um servidor web, assim como o Apache também o é.
Ngins funciona também Proxy reverso, Proxy balanceador de carga, com um performance muito maior se comparado com outros servidores WEB como o APACHE. É um servidor de alta performance e um servidor proxy para IMAP/POP3. 

---

3\) Existem threads em PHP?

PHP suporta as User Level Thread (ULT)  

3.1) Explique

O suporte a threads é feito através de um módulo (extensão). No caso do PHP, o módulo pthreads é o módulo responsável pelo suporte a threads. Ele é um módulo Pecl, portanto possui boa performance.

---

4\) Qual o resultado dos códigos a seguir?

4.1)
```php
class Test {
    const prop = 1000 + 337;
}

echo Test::prop;
```

Retorna 1337.

4.2)
```js
class A {
    public static function foo() {
        return 'bar';
    }

    public static function test() {
        echo self::foo();
    }
}

class B extends A {
    public static function foo() {
        return 'baz';
    }
}

B::test();
```

Retorna bar.
O método test retorna método foo na classe A, ele utiliza self.
