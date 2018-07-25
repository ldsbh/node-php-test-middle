# Node

1\) Qual a diferença do operador `==` para o operador `===` em JavaScript?

[Resposta]

1.1) Dê 2 exemplos de quando os operadores produziriam resultados diferentes

```js
// Resposta
```

---

2\) Qual recurso javascript é mais recomendado para tratar chamadas asíncronas?

[Resposta]

2.1) Justifique

[Resposta]

---

3\) Existem threads em Node?

[Resposta]

3.1) Explique

[Resposta]

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

[Resposta]

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
[Resposta]
```

---

# PHP

1\) Qual a diferença do operador `==` para o operador `===` em PHP?

[Resposta]

1.1) Dê 2 exemplos de quando os operadores produziriam resultados diferentes

```php
// Resposta
```

---

2\) Qual a função do apache ou nginx em uma aplicação PHP?

[Resposta]

---

3\) Existem threads em PHP?

[Resposta]

3.1) Explique

[Resposta]

---

4\) Qual o resultado dos códigos a seguir?

4.1)
```php
class Test {
    const prop = 1000 + 337;
}

echo Test::prop;
```

[Resposta]

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

[Resposta]