# Atividade prática avaliativa — Garagem de Carros com Jest

**Esta é uma atividade avaliativa.**

Agora vamos desenvolver um pequeno sistema utilizando **classes, objetos e testes automatizados com Jest**.

O projeto será um sistema simples para controlar uma **garagem de carros**.

A proposta é colocar em prática os conceitos de programação orientada a objetos estudados em aula, utilizando o Jest para verificar se as regras do sistema estão funcionando corretamente.

---

## 1. Criando o projeto

Criem uma nova pasta chamada:

```bash
garagem-jest
```

Inicializem o projeto:

```bash
npm init -y
```

Instalem as dependências necessárias:

- TypeScript
- Jest
- ts-jest
- @types/jest

A estrutura inicial deverá ficar semelhante a:

```text
garagem-jest
│
├── src
├── tests
├── jest.config.js
├── package.json
└── tsconfig.json
```

---

## 2. Criando a classe Car

Dentro da pasta `src`, criem o arquivo:

```text
Car.ts
```

A classe `Car` deverá representar um carro e possuir, no mínimo, as seguintes propriedades:

- `brand`: marca do carro.
- `model`: modelo do carro.
- `year`: ano do carro.
- `stored`: indica se o carro está armazenado na garagem.

Exemplo de criação:

```typescript
const car = new Car("Toyota", "Corolla", 2025);
```

O atributo `stored` deverá ser inicializado como `false`, indicando que o carro ainda não está armazenado na garagem.

Decidam quais propriedades serão `private` e quais métodos serão necessários para acessar ou alterar os dados.

### 2.1. Método para alterar o atributo stored

A classe deverá possuir um método que permita alterar o atributo `stored`.

Por exemplo:

```typescript
car.setStored(true);
```

Depois dessa chamada, o carro deverá estar marcado como armazenado.

Também deverá ser possível alterar novamente o estado:

```typescript
car.setStored(false);
```

Nesse caso, o carro deixará de estar marcado como armazenado.

O método `setStored()` é uma sugestão de nome. O importante é permitir a alteração do atributo respeitando o encapsulamento.

A classe também deverá possuir um método que permita consultar o valor atual de `stored`, sem acessar diretamente uma propriedade privada.

---

## 3. Criando a classe Garage

Dentro da pasta `src`, criem o arquivo:

```text
Garage.ts
```

A classe `Garage` deverá representar uma garagem capaz de armazenar vários carros.

Ela deverá possuir uma lista de carros.

Exemplo:

```typescript
const garage = new Garage();
```

A classe deverá possuir métodos para realizar as seguintes operações.

### 3.1. Adicionar um carro

```typescript
addCar()
```

O método deverá adicionar um carro à garagem e atualizar seu atributo `stored` para `true`.

### 3.2. Remover um carro

```typescript
removeCar()
```

O método deverá remover o carro da garagem e atualizar seu atributo `stored` para `false`.

### 3.3. Consultar a quantidade de carros

```typescript
getCarCount()
```

Deverá retornar a quantidade de carros armazenados na garagem.

### 3.4. Procurar um carro pelo modelo

```typescript
findCarByModel()
```

Deverá procurar um carro pelo modelo informado.

Os nomes das propriedades e dos métodos deverão estar em **inglês**.

---

## 4. Regras do sistema

A garagem deverá seguir as regras descritas a seguir.

### 4.1. Adicionar carros

Ao adicionar um carro, ele deverá ser armazenado na garagem e seu atributo `stored` deverá ser alterado para `true`.

Exemplo:

```text
Toyota Corolla
Ford Mustang
Honda Civic
```

Depois de adicionar os três carros, a quantidade deverá ser:

```text
Quantidade de carros: 3
```

Todos os três carros deverão apresentar `stored` igual a `true`.

### 4.2. Remover carros

Ao remover um carro, ele não deverá mais fazer parte da garagem, e seu atributo `stored` deverá ser alterado para `false`.

Se existirem:

```text
Toyota Corolla
Ford Mustang
Honda Civic
```

e removermos o `Ford Mustang`, deverão permanecer:

```text
Toyota Corolla
Honda Civic
```

O objeto correspondente ao Ford Mustang deverá apresentar `stored` igual a `false`.

Os outros dois carros deverão continuar com `stored` igual a `true`.

### 4.3. Procurar por modelo

O método `findCarByModel()` deverá procurar um carro pelo seu modelo.

Exemplo:

```typescript
garage.findCarByModel("Corolla");
```

Se o carro existir, o método deverá retornar o objeto correspondente.

Caso contrário, deverá retornar:

```typescript
undefined
```

### 4.4. Não permitir carros duplicados

A garagem não deverá permitir dois carros com a mesma combinação de:

```text
brand + model + year
```

Por exemplo, não será permitido cadastrar duas vezes:

```text
Toyota Corolla 2025
```

Caso isso aconteça, o sistema deverá lançar um erro.

### 4.5. Controlar o estado stored

O atributo `stored` deverá representar corretamente se o carro está armazenado na garagem.

- Ao criar um carro, `stored` deverá começar como `false`.
- Ao adicionar o carro à garagem, `stored` deverá passar para `true`.
- Ao remover o carro da garagem, `stored` deverá passar para `false`.
- O método de alteração deverá permitir modificar o estado do atributo.

O atributo deverá ser controlado por métodos, respeitando o encapsulamento.

---

## 5. Criando os testes

Dentro da pasta `tests`, criem o arquivo:

```text
Garage.test.ts
```

Os testes deverão verificar o comportamento das classes.

Criem **pelo menos 12 testes automatizados**, incluindo os testes obrigatórios abaixo.

### 5.1. Testes obrigatórios

**Teste 1 — Criar um carro**

Verifiquem se é possível criar corretamente um objeto da classe `Car`.

**Teste 2 — Verificar o estado inicial de stored**

Criem um carro e verifiquem se `stored` começa como `false`.

**Teste 3 — Alterar stored para true**

Utilizem o método de alteração para definir o atributo como `true` e verifiquem o resultado.

**Teste 4 — Alterar stored para false**

Alterem o atributo para `true` e, em seguida, para `false`. Verifiquem se o valor foi atualizado corretamente.

**Teste 5 — Adicionar um carro**

Criem uma garagem, adicionem um carro e verifiquem se a quantidade de carros é `1`.

**Teste 6 — Verificar stored após adicionar**

Adicionem um carro à garagem e verifiquem se seu atributo `stored` passou para `true`.

**Teste 7 — Adicionar vários carros**

Adicionem pelo menos três carros e verifiquem se a quantidade retornada é `3`.

**Teste 8 — Remover um carro**

Adicionem um carro, removam-no e verifiquem se a garagem ficou vazia.

**Teste 9 — Verificar stored após remover**

Adicionem um carro, removam-no e verifiquem se seu atributo `stored` passou para `false`.

**Teste 10 — Procurar um carro existente**

Adicionem um carro e utilizem `findCarByModel()` para verificar se o objeto correto foi encontrado.

**Teste 11 — Procurar um carro inexistente**

Procurem por um modelo que não foi cadastrado. O resultado esperado deverá ser `undefined`.

**Teste 12 — Não permitir carros duplicados**

Tentem adicionar duas vezes um carro com a mesma marca, modelo e ano. O segundo cadastro deverá gerar um erro.

Utilizem `toThrow()` para testar essa situação.

**Teste 13 — Verificar a marca do carro encontrado**

Procurem um carro pelo modelo e verifiquem se a propriedade `brand` está correta.

**Teste 14 — Verificar o ano do carro encontrado**

Procurem um carro pelo modelo e verifiquem se a propriedade `year` está correta.

**Teste 15 — Remover um carro entre vários**

Adicionem três carros, removam apenas um deles e verifiquem se os outros dois continuam na garagem.

**Teste 16 — Verificar os estados após remover um carro**

Adicionem três carros e removam um deles. Verifiquem se o carro removido apresenta `stored` igual a `false` e se os outros dois continuam com `stored` igual a `true`.

---

## 6. Utilizando o padrão AAA

Organizem os testes utilizando o padrão:

```text
Arrange
Act
Assert
```

Esse padrão divide os testes em três etapas:

- **Arrange:** preparar os objetos e os dados necessários.
- **Act:** executar a ação que será testada.
- **Assert:** verificar se o resultado corresponde ao esperado.

Exemplo:

```typescript
test("deve adicionar um carro à garagem", () => {
  // Arrange
  const garage = new Garage();
  const car = new Car("Toyota", "Corolla", 2025);

  // Act
  garage.addCar(car);

  // Assert
  expect(garage.getCarCount()).toBe(1);
  expect(car.getStored()).toBe(true);
});
```

O método `getStored()` é apenas uma sugestão de nome para consultar o atributo. Implementem um método que permita verificar o estado de `stored` sem acessar diretamente uma propriedade privada.

Não é obrigatório utilizar exatamente esse código. O objetivo é entender a separação entre preparar, executar e verificar.

---

## 7. Estrutura esperada

Ao final do exercício, o projeto deverá possuir uma estrutura semelhante a:

```text
garagem-jest
│
├── src
│   ├── Car.ts
│   └── Garage.ts
│
├── tests
│   └── Garage.test.ts
│
├── jest.config.js
├── package.json
├── package-lock.json
└── tsconfig.json
```

---

## 8. Requisitos do exercício

O projeto deverá obrigatoriamente possuir:

- Uma classe `Car`.
- Uma classe `Garage`.
- Objetos criados a partir dessas classes.
- Propriedades tipadas com TypeScript.
- Os atributos `brand`, `model`, `year` e `stored` na classe `Car`.
- Um método para alterar o atributo `stored`.
- Um método para consultar o estado de `stored`.
- Uma lista de carros dentro da garagem.
- Métodos para adicionar, remover, contar e procurar carros.
- Atualização de `stored` ao adicionar e remover carros.
- Proibição de carros duplicados com a mesma marca, modelo e ano.
- Pelo menos 12 testes automatizados.
- Uso de `test()`.
- Uso de `expect()`.
- Uso de `toBe()`.
- Uso de `toThrow()`.
- Uso do padrão AAA em pelo menos alguns testes.
- Todos os testes executando corretamente com:

```bash
npm test
```

---

## 9. Desafio adicional

Depois que todos os testes obrigatórios estiverem funcionando, adicionem uma nova funcionalidade à garagem.

Uma possibilidade é criar o método:

```typescript
getCarsByBrand()
```

Esse método deverá retornar todos os carros de determinada marca.

Exemplo:

```text
Toyota Corolla
Toyota Yaris
Ford Mustang
Honda Civic
```

Ao procurar por:

```typescript
garage.getCarsByBrand("Toyota");
```

o resultado deverá conter:

```text
Toyota Corolla
Toyota Yaris
```

Criem também **pelo menos dois testes** para essa nova funcionalidade.

Outra possibilidade é adicionar um método que retorne apenas os carros atualmente armazenados na garagem, considerando o atributo `stored`.

---

## 10. Executando os testes

Depois de terminar o projeto, executem:

```bash
npm test
```

Todos os testes deverão passar.

O objetivo não é apenas fazer o programa funcionar. O objetivo é utilizar o **Jest para verificar, por meio de testes automatizados, que as classes e suas regras estão funcionando corretamente**.

---

## 11. Conclusão

Nesta atividade, vamos praticar a criação de classes e objetos com TypeScript e verificar o funcionamento do sistema com testes automatizados.

Também vamos reforçar conceitos importantes de programação orientada a objetos:

- **Classes e objetos:** representar carros e a garagem.
- **Encapsulamento:** controlar o acesso às propriedades por meio de métodos.
- **Métodos:** implementar as operações do sistema.
- **Atributos de estado:** utilizar `stored` para indicar se um carro está armazenado.
- **Testes automatizados:** verificar se as regras de negócio estão funcionando.
- **Padrão AAA:** organizar os testes em preparação, execução e verificação.

A base dos nossos testes continuará sendo:

```text
Arrange
   ↓
Act
   ↓
Assert
```

Ou seja:

**Preparar → Executar → Verificar**

O objetivo é construir um sistema simples, organizado e testado, garantindo que cada operação produza o comportamento esperado.
