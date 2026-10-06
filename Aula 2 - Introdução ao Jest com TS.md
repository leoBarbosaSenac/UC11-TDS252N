# Aula: Introdução ao Jest com TypeScript

## Testes de Software na Prática

Nesta aula nós vamos dar um passo muito importante no nosso aprendizado sobre testes de software.

Até agora nós estudamos conceitos como requisitos, requisitos funcionais, requisitos não funcionais, casos de teste e a importância de testar um sistema.

Agora vamos começar a automatizar nossos testes.

Para isso, vamos utilizar duas tecnologias:

- TypeScript
- Jest

Nós vamos começar literalmente do zero.

Durante esta aula, eu vou explicar cada comando, cada arquivo e cada parte do código.

Nosso objetivo será criar um pequeno projeto com quatro operações matemáticas:

- Soma
- Subtração
- Multiplicação
- Divisão

Depois, nós vamos criar testes automatizados para verificar se cada uma dessas funções está funcionando corretamente.

---

# 1. O que vamos aprender nesta aula?

Ao final desta aula nós deveremos conseguir:

1. Entender o que é o Jest.
2. Entender para que serve o Jest.
3. Entender como funciona um teste automatizado.
4. Criar um projeto Node.js.
5. Configurar TypeScript.
6. Instalar e configurar Jest.
7. Criar funções simples em TypeScript.
8. Criar testes para essas funções.
9. Executar os testes pelo terminal.
10. Interpretar quando um teste passa ou falha.

---

# 2. O que é Jest?

O Jest é uma ferramenta utilizada para criar e executar testes automatizados em projetos JavaScript e TypeScript.

Podemos pensar nele como um programa que executa nossos testes e verifica se o resultado obtido pelo código é igual ao resultado que nós esperávamos.

Por exemplo, sabemos que:

```text
2 + 2 = 4
```

Nós podemos criar uma função que faz essa soma.

Depois podemos pedir para o Jest verificar automaticamente se:

```text
somar(2, 2)
```

realmente retorna:

```text
4
```

Se retornar 4, o teste passa.

Se retornar qualquer outro valor, o teste falha.

---

# 3. Por que utilizar testes automatizados?

Imagine que nós estamos desenvolvendo um sistema grande.

Toda vez que alteramos alguma parte do código, precisaríamos testar novamente várias funcionalidades manualmente.

Em um sistema pequeno isso pode parecer simples.

Mas imagine um sistema com:

- 100 funções
- 500 funções
- 1.000 funções
- milhares de regras de negócio

Testar tudo manualmente seria demorado.

É nesse ponto que os testes automatizados ajudam.

Nós criamos os testes uma vez e podemos executá-los quantas vezes quisermos.

---

# 4. O que o Jest faz?

O Jest executa nossos arquivos de teste e compara:

```text
Resultado obtido
```

com:

```text
Resultado esperado
```

Se forem iguais, o teste passa.

Se forem diferentes, o teste falha.

Exemplo:

Esperamos:

```text
10
```

Mas nosso programa retorna:

```text
8
```

O Jest informa que existe um problema.

---

# 5. Antes de começar

Para acompanhar esta aula nós precisamos ter instalado no computador:

- Node.js
- Visual Studio Code
- Terminal ou Prompt de Comando

Também utilizaremos:

- TypeScript
- Jest
- ts-jest
- Tipagens do Jest

---

# 6. O que é Node.js?

Node.js permite executar JavaScript fora do navegador.

Quando instalamos o Node.js, também recebemos uma ferramenta chamada npm.

O npm será utilizado para instalar as bibliotecas necessárias para nosso projeto.

Para verificar se o Node.js está instalado, abra o terminal e digite:

```bash
node --version
```

Ou:

```bash
node -v
```

Se estiver instalado, aparecerá uma versão semelhante a:

```text
v22.0.0
```

A versão pode ser diferente no computador de vocês.

---

# 7. Verificando o npm

Agora vamos verificar se o npm está funcionando.

Digite:

```bash
npm --version
```

ou:

```bash
npm -v
```

Será exibido um número de versão.

Por exemplo:

```text
10.0.0
```

Isso significa que o npm está disponível.

---

# 8. Criando nosso projeto

Vamos criar uma pasta para nosso projeto.

Podemos utilizar o nome:

```text
calculadora-jest
```

Pelo terminal podemos executar:

```bash
mkdir calculadora-jest
```

O comando `mkdir` significa:

```text
make directory
```

Ou seja:

```text
criar diretório
```

Agora vamos entrar na pasta:

```bash
cd calculadora-jest
```

O comando `cd` significa:

```text
change directory
```

Ou seja:

```text
mudar de diretório
```

Agora estamos dentro da pasta do projeto.

---

# 9. Abrindo o projeto no Visual Studio Code

Se o comando `code` estiver configurado no computador, podemos digitar:

```bash
code .
```

O ponto representa a pasta atual.

Assim estamos dizendo:

```text
Abra esta pasta no Visual Studio Code.
```

Também podemos abrir o Visual Studio Code manualmente e selecionar a pasta do projeto.

---

# 10. Criando o projeto Node.js

Dentro da pasta do projeto, execute:

```bash
npm init -y
```

Esse comando cria um arquivo chamado:

```text
package.json
```

Vamos entender o comando.

## npm

É o gerenciador de pacotes do Node.js.

## init

Significa que queremos inicializar um novo projeto.

## -y

Significa que estamos aceitando automaticamente as configurações padrão.

Depois do comando, teremos:

```text
calculadora-jest
│
└── package.json
```

---

# 11. O que é package.json?

O arquivo `package.json` contém informações importantes sobre nosso projeto.

Ele pode armazenar:

- Nome do projeto
- Versão
- Scripts
- Dependências
- Bibliotecas instaladas

Um arquivo inicial poderá parecer com:

```json
{
  "name": "calculadora-jest",
  "version": "1.0.0",
  "main": "index.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1"
  }
}
```

Nós vamos alterar a parte dos scripts mais adiante.

---

# 12. Instalando o TypeScript

Agora vamos instalar o TypeScript.

Execute:

```bash
npm install --save-dev typescript
```

Vamos entender esse comando.

## npm install

Significa:

```text
Instale um pacote.
```

## typescript

É o pacote que queremos instalar.

## --save-dev

Significa que essa biblioteca será utilizada durante o desenvolvimento.

Ela não precisa fazer parte do sistema final em produção.

Também podemos utilizar a forma abreviada:

```bash
npm install -D typescript
```

O `-D` significa dependência de desenvolvimento.

---

# 13. Criando o arquivo de configuração do TypeScript

Agora execute:

```bash
npx tsc --init
```

Esse comando cria o arquivo:

```text
tsconfig.json
```

Vamos entender.

## npx

Permite executar ferramentas instaladas no projeto.

## tsc

É o compilador do TypeScript.

## --init

Cria o arquivo inicial de configuração.

---

# 14. O que é tsconfig.json?

O arquivo `tsconfig.json` configura o funcionamento do TypeScript.

Para nossa aula inicial, podemos utilizar uma configuração simples:

```json
{
  "compilerOptions": {
    "rootDir": "./src",
    "outDir": "./dist",
    "module": "nodenext",
    "target": "esnext",
    "types": ["node", "jest"],
    "strict": true,
    "skipLibCheck": true
  },
  "include": ["./src/**/*.ts"],
  "exclude": ["./node_modules", "./tests"]
}
```

Vamos entender rapidamente.

## target

```json
"target": "ES2020"
```

Define a versão de JavaScript utilizada como referência.

## module

```json
"module": "commonjs"
```

Define como os módulos serão organizados.

## strict

```json
"strict": true
```

Ativa verificações mais rigorosas do TypeScript.

Isso ajuda a encontrar problemas antes mesmo de executar o programa.

## esModuleInterop

Facilita a integração entre diferentes formatos de módulos.

## skipLibCheck

Evita verificações desnecessárias em arquivos de tipos das bibliotecas.

---

# 15. Instalando o Jest

Agora vamos instalar o Jest.

Execute:

```bash
npm install --save-dev jest
```

Ou:

```bash
npm install -D jest
```

O Jest será responsável por executar nossos testes.

---

# 16. Instalando suporte do Jest para TypeScript

O Jest trabalha originalmente muito bem com JavaScript.

Como nosso projeto utilizará TypeScript, precisamos instalar uma ferramenta chamada:

```text
ts-jest
```

Execute:

```bash
npm install --save-dev ts-jest
```

Ou:

```bash
npm install -D ts-jest
```

O `ts-jest` permite que o Jest execute arquivos TypeScript.

---

# 17. Instalando as tipagens do Jest

Agora execute:

```bash
npm install --save-dev @types/jest
```

Ou:

```bash
npm install -D @types/jest
```

Esse pacote fornece ao TypeScript informações sobre os comandos do Jest.

Por exemplo:

```typescript
describe()
```

```typescript
test()
```

```typescript
expect()
```

Sem as tipagens, o TypeScript poderá não reconhecer corretamente esses comandos.

---

# 18. Podemos instalar tudo de uma vez?

Sim.

Em vez de executar vários comandos separados, poderíamos usar:

```bash
npm install -D typescript jest ts-jest @types/jest
```

Mas nesta aula eu preferi mostrar separadamente para entendermos a função de cada pacote.

---

# 19. Criando a configuração do Jest

Agora execute:

```bash
npx ts-jest config:init
```

Esse comando normalmente cria o arquivo:

```text
jest.config.js
```

Dependendo da versão utilizada, a configuração poderá aparecer em outro formato.

Uma configuração simples pode ser:

```javascript
module.exports = {
  preset: "ts-jest",
  testEnvironment: "node"
};
```

O ponto mais importante é:

```javascript
preset: "ts-jest"
```

Isso informa ao Jest que estamos utilizando TypeScript.

---

# 20. Configurando o comando de teste

Agora vamos abrir o arquivo:

```text
package.json
```

Provavelmente teremos algo parecido com:

```json
"scripts": {
  "test": "echo \"Error: no test specified\" && exit 1"
}
```

Vamos substituir por:

```json
"scripts": {
  "test": "jest"
}
```

Agora, quando executarmos:

```bash
npm test
```

o npm executará:

```bash
jest
```

---

# 21. Estrutura que vamos utilizar

Vamos criar duas pastas:

```text
src
```

e:

```text
tests
```

Nossa estrutura ficará:

```text
calculadora-jest
│
├── src
│   └── calculadora.ts
│
├── tests
│   └── calculadora.test.ts
│
├── jest.config.js
├── package.json
└── tsconfig.json
```

---

# 22. Para que serve a pasta src?

A pasta `src` será utilizada para armazenar nosso código principal.

`src` vem de:

```text
source
```

Ou seja:

```text
código-fonte
```

Nela vamos colocar:

```text
calculadora.ts
```

---

# 23. Para que serve a pasta tests?

A pasta `tests` será utilizada para armazenar nossos testes.

Dentro dela criaremos:

```text
calculadora.test.ts
```

O trecho:

```text
.test.ts
```

ajuda o Jest a identificar que aquele arquivo contém testes.

---

# 24. Criando nossa calculadora

Dentro da pasta `src`, crie:

```text
calculadora.ts
```

Vamos começar com a função de soma.

```typescript
export function somar(a: number, b: number): number {
  return a + b;
}
```

Vamos entender.

## export

Significa que queremos permitir que essa função seja utilizada em outros arquivos.

## function

Estamos criando uma função.

## somar

É o nome da função.

## a: number

O parâmetro `a` deve ser um número.

## b: number

O parâmetro `b` também deve ser um número.

## : number

Depois dos parênteses informamos que o resultado da função também será um número.

---

# 25. Criando a função de subtração

Agora vamos adicionar:

```typescript
export function subtrair(a: number, b: number): number {
  return a - b;
}
```

Exemplo:

```typescript
subtrair(10, 4)
```

Resultado esperado:

```text
6
```

---

# 26. Criando a função de multiplicação

Agora:

```typescript
export function multiplicar(a: number, b: number): number {
  return a * b;
}
```

Exemplo:

```typescript
multiplicar(5, 3)
```

Resultado esperado:

```text
15
```

---

# 27. Criando a função de divisão

Agora vamos criar:

```typescript
export function dividir(a: number, b: number): number {
  return a / b;
}
```

Exemplo:

```typescript
dividir(10, 2)
```

Resultado esperado:

```text
5
```

---

# 28. Nosso arquivo completo

O arquivo:

```text
src/calculadora.ts
```

ficará assim:

```typescript
export function somar(a: number, b: number): number {
  return a + b;
}

export function subtrair(a: number, b: number): number {
  return a - b;
}

export function multiplicar(a: number, b: number): number {
  return a * b;
}

export function dividir(a: number, b: number): number {
  return a / b;
}
```

Nossa calculadora está pronta.

Agora precisamos testar.

---

# 29. Criando nosso primeiro teste

Dentro da pasta:

```text
tests
```

crie:

```text
calculadora.test.ts
```

Primeiro precisamos importar nossas funções:

```typescript
import {
  somar,
  subtrair,
  multiplicar,
  dividir
} from "../src/calculadora";
```

Agora podemos utilizar as funções dentro dos testes.

---

# 30. Nosso primeiro teste com Jest

Vamos testar a soma.

```typescript
test("deve somar 2 + 3 e retornar 5", () => {
  expect(somar(2, 3)).toBe(5);
});
```

Vamos entender cada parte.

---

# 31. O comando test()

O Jest possui uma função chamada:

```typescript
test()
```

Ela representa um teste.

Temos:

```typescript
test("deve somar 2 + 3 e retornar 5", () => {
});
```

A primeira informação é a descrição do teste.

É importante escrevermos uma descrição simples e objetiva.

---

# 32. O que é expect()?

Dentro do teste temos:

```typescript
expect()
```

O `expect` significa aproximadamente:

```text
Eu espero que...
```

No nosso exemplo:

```typescript
expect(somar(2, 3))
```

Estamos dizendo:

```text
Eu espero que o resultado de somar 2 e 3...
```

---

# 33. O que é toBe()?

Depois temos:

```typescript
.toBe(5)
```

Estamos dizendo:

```text
...seja exatamente 5.
```

Portanto:

```typescript
expect(somar(2, 3)).toBe(5);
```

pode ser lido como:

```text
Eu espero que somar 2 com 3 seja igual a 5.
```

---

# 34. Estrutura básica de um teste

Podemos memorizar:

```typescript
test("descrição", () => {
  expect(resultado).toBe(resultadoEsperado);
});
```

Essa será nossa estrutura inicial.

---

# 35. Testando a subtração

Agora vamos criar:

```typescript
test("deve subtrair 10 - 4 e retornar 6", () => {
  expect(subtrair(10, 4)).toBe(6);
});
```

---

# 36. Testando a multiplicação

```typescript
test("deve multiplicar 5 por 3 e retornar 15", () => {
  expect(multiplicar(5, 3)).toBe(15);
});
```

---

# 37. Testando a divisão

```typescript
test("deve dividir 10 por 2 e retornar 5", () => {
  expect(dividir(10, 2)).toBe(5);
});
```

---

# 38. Nosso primeiro arquivo de testes completo

O arquivo:

```text
tests/calculadora.test.ts
```

ficará assim:

```typescript
import {
  somar,
  subtrair,
  multiplicar,
  dividir
} from "../src/calculadora";

test("deve somar 2 + 3 e retornar 5", () => {
  expect(somar(2, 3)).toBe(5);
});

test("deve subtrair 10 - 4 e retornar 6", () => {
  expect(subtrair(10, 4)).toBe(6);
});

test("deve multiplicar 5 por 3 e retornar 15", () => {
  expect(multiplicar(5, 3)).toBe(15);
});

test("deve dividir 10 por 2 e retornar 5", () => {
  expect(dividir(10, 2)).toBe(5);
});
```

---

# 39. Executando nossos testes

Agora vamos abrir o terminal na pasta do projeto.

Execute:

```bash
npm test
```

O Jest procurará automaticamente nossos arquivos de teste.

Se tudo estiver correto, veremos uma saída semelhante a:

```text
PASS tests/calculadora.test.ts

✓ deve somar 2 + 3 e retornar 5
✓ deve subtrair 10 - 4 e retornar 6
✓ deve multiplicar 5 por 3 e retornar 15
✓ deve dividir 10 por 2 e retornar 5

Tests: 4 passed, 4 total
```

Isso significa que nossos quatro testes passaram.

---

# 40. O que significa PASS?

Quando o Jest mostra:

```text
PASS
```

significa que os testes daquele arquivo foram executados corretamente.

Nosso código retornou os resultados esperados.

---

# 41. Vamos fazer um teste falhar propositalmente

Agora vamos aprender algo importante.

Vamos alterar temporariamente este teste:

```typescript
test("deve somar 2 + 3 e retornar 5", () => {
  expect(somar(2, 3)).toBe(10);
});
```

Estamos dizendo que esperamos:

```text
10
```

Mas sabemos que:

```text
2 + 3 = 5
```

Execute novamente:

```bash
npm test
```

Agora o Jest deverá mostrar uma falha.

Algo semelhante a:

```text
Expected: 10
Received: 5
```

Ou seja:

```text
Esperado: 10
Recebido: 5
```

Isso é extremamente importante.

O Jest está nos mostrando exatamente onde o resultado foi diferente do esperado.

Depois do teste, volte para:

```typescript
expect(somar(2, 3)).toBe(5);
```

---

# 42. Organizando testes com describe()

Quando começamos a ter vários testes, podemos organizá-los utilizando:

```typescript
describe()
```

Por exemplo:

```typescript
describe("Testes da calculadora", () => {

  test("deve somar 2 + 3 e retornar 5", () => {
    expect(somar(2, 3)).toBe(5);
  });

});
```

O `describe` funciona como um grupo de testes.

Podemos pensar nele como uma pasta lógica.

---

# 43. Organizando por operação

Podemos fazer assim:

```typescript
describe("Testes da função somar", () => {

  test("deve somar 2 + 3 e retornar 5", () => {
    expect(somar(2, 3)).toBe(5);
  });

  test("deve somar 10 + 20 e retornar 30", () => {
    expect(somar(10, 20)).toBe(30);
  });

});
```

Agora os testes relacionados à soma ficam agrupados.

---

# 44. Criando vários testes

Vamos melhorar nosso arquivo.

```typescript
import {
  somar,
  subtrair,
  multiplicar,
  dividir
} from "../src/calculadora";

describe("Testes da Calculadora", () => {

  describe("Soma", () => {

    test("deve somar 2 + 3 e retornar 5", () => {
      expect(somar(2, 3)).toBe(5);
    });

    test("deve somar 10 + 20 e retornar 30", () => {
      expect(somar(10, 20)).toBe(30);
    });

  });

  describe("Subtração", () => {

    test("deve subtrair 10 - 4 e retornar 6", () => {
      expect(subtrair(10, 4)).toBe(6);
    });

    test("deve subtrair 20 - 5 e retornar 15", () => {
      expect(subtrair(20, 5)).toBe(15);
    });

  });

  describe("Multiplicação", () => {

    test("deve multiplicar 5 por 3 e retornar 15", () => {
      expect(multiplicar(5, 3)).toBe(15);
    });

    test("deve multiplicar 10 por 2 e retornar 20", () => {
      expect(multiplicar(10, 2)).toBe(20);
    });

  });

  describe("Divisão", () => {

    test("deve dividir 10 por 2 e retornar 5", () => {
      expect(dividir(10, 2)).toBe(5);
    });

    test("deve dividir 20 por 4 e retornar 5", () => {
      expect(dividir(20, 4)).toBe(5);
    });

  });

});
```

Agora temos oito testes automatizados.

---

# 45. Testando valores diferentes

Nós não precisamos testar apenas números positivos.

Podemos testar números negativos.

Exemplo:

```typescript
test("deve somar números negativos", () => {
  expect(somar(-2, -3)).toBe(-5);
});
```

Também podemos testar zero.

```typescript
test("deve somar zero", () => {
  expect(somar(10, 0)).toBe(10);
});
```

---

# 46. Testando multiplicação por zero

```typescript
test("deve multiplicar por zero", () => {
  expect(multiplicar(10, 0)).toBe(0);
});
```

Esse é um exemplo importante porque estamos testando um caso diferente dos anteriores.

---

# 47. E a divisão por zero?

Agora temos uma situação interessante.

O que acontece se executarmos:

```typescript
dividir(10, 0)
```

No JavaScript e TypeScript, isso retorna:

```text
Infinity
```

Mas em nossa calculadora podemos decidir que dividir por zero não será permitido.

Aqui aparece uma regra de negócio.

Podemos definir:

```text
Não permitir divisão por zero.
```

---

# 48. Melhorando nossa função dividir

Vamos alterar:

```typescript
export function dividir(a: number, b: number): number {
  return a / b;
}
```

para:

```typescript
export function dividir(a: number, b: number): number {

  if (b === 0) {
    throw new Error("Não é possível dividir por zero");
  }

  return a / b;
}
```

Agora nossa função verifica se o segundo número é zero.

Se for, ela lança um erro.

---

# 49. Testando erros com Jest

Agora podemos criar:

```typescript
test("não deve permitir divisão por zero", () => {
  expect(() => dividir(10, 0)).toThrow();
});
```

Estamos dizendo:

```text
Eu espero que dividir 10 por zero provoque um erro.
```

Podemos ser ainda mais específicos:

```typescript
test("não deve permitir divisão por zero", () => {
  expect(() => dividir(10, 0))
    .toThrow("Não é possível dividir por zero");
});
```

Agora estamos verificando também a mensagem do erro.

---

# 50. Código final da calculadora

Nosso arquivo:

```text
src/calculadora.ts
```

pode ficar assim:

```typescript
export function somar(a: number, b: number): number {
  return a + b;
}

export function subtrair(a: number, b: number): number {
  return a - b;
}

export function multiplicar(a: number, b: number): number {
  return a * b;
}

export function dividir(a: number, b: number): number {

  if (b === 0) {
    throw new Error("Não é possível dividir por zero");
  }

  return a / b;
}
```

---

# 51. Arquivo final de testes

Nosso:

```text
tests/calculadora.test.ts
```

poderá ficar assim:

```typescript
import {
  somar,
  subtrair,
  multiplicar,
  dividir
} from "../src/calculadora";

describe("Testes da Calculadora", () => {

  describe("Soma", () => {

    test("deve somar 2 + 3 e retornar 5", () => {
      expect(somar(2, 3)).toBe(5);
    });

    test("deve somar 10 + 20 e retornar 30", () => {
      expect(somar(10, 20)).toBe(30);
    });

    test("deve somar números negativos", () => {
      expect(somar(-2, -3)).toBe(-5);
    });

  });

  describe("Subtração", () => {

    test("deve subtrair 10 - 4 e retornar 6", () => {
      expect(subtrair(10, 4)).toBe(6);
    });

    test("deve subtrair 20 - 5 e retornar 15", () => {
      expect(subtrair(20, 5)).toBe(15);
    });

  });

  describe("Multiplicação", () => {

    test("deve multiplicar 5 por 3 e retornar 15", () => {
      expect(multiplicar(5, 3)).toBe(15);
    });

    test("deve multiplicar por zero", () => {
      expect(multiplicar(10, 0)).toBe(0);
    });

  });

  describe("Divisão", () => {

    test("deve dividir 10 por 2 e retornar 5", () => {
      expect(dividir(10, 2)).toBe(5);
    });

    test("deve dividir 20 por 4 e retornar 5", () => {
      expect(dividir(20, 4)).toBe(5);
    });

    test("não deve permitir divisão por zero", () => {
      expect(() => dividir(10, 0))
        .toThrow("Não é possível dividir por zero");
    });

  });

});
```

---

# 52. Executando novamente

Execute:

```bash
npm test
```

O Jest deverá executar todos os testes.

Se tudo estiver correto, veremos todos passando.

---

# 53. Executando o Jest em modo de observação

Existe um recurso muito interessante chamado:

```text
watch
```

Execute:

```bash
npm test -- --watch
```

Nesse modo o Jest fica observando mudanças no projeto.

Quando alteramos o código e salvamos, podemos executar novamente os testes rapidamente.

Também podemos criar um script.

No `package.json`:

```json
"scripts": {
  "test": "jest",
  "test:watch": "jest --watch"
}
```

Depois podemos executar:

```bash
npm run test:watch
```

---

# 54. O que aprendemos sobre test()

O comando:

```typescript
test()
```

cria um teste.

Exemplo:

```typescript
test("descrição", () => {
});
```

---

# 55. O que aprendemos sobre expect()

O comando:

```typescript
expect()
```

define aquilo que queremos verificar.

Exemplo:

```typescript
expect(somar(2, 2))
```

---

# 56. O que aprendemos sobre toBe()

O comando:

```typescript
toBe()
```

compara o resultado com o valor esperado.

Exemplo:

```typescript
expect(somar(2, 2)).toBe(4);
```

---

# 57. O que aprendemos sobre describe()

O comando:

```typescript
describe()
```

serve para agrupar testes relacionados.

Exemplo:

```typescript
describe("Soma", () => {

});
```

---

# 58. O que aprendemos sobre toThrow()?

O comando:

```typescript
toThrow()
```

serve para verificar se determinada execução gera um erro.

Exemplo:

```typescript
expect(() => dividir(10, 0)).toThrow();
```

---

# 59. O padrão AAA

Existe uma forma muito utilizada para organizar testes chamada:

```text
AAA
```

Isso significa:

```text
Arrange
Act
Assert
```

Em português podemos pensar em:

```text
Preparar
Executar
Verificar
```

---

# 60. Exemplo usando AAA

Vamos criar:

```typescript
test("deve somar dois números", () => {

  // Arrange
  const numero1 = 10;
  const numero2 = 20;

  // Act
  const resultado = somar(numero1, numero2);

  // Assert
  expect(resultado).toBe(30);

});
```

---

# 61. Arrange

Nesta parte nós preparamos os dados.

```typescript
const numero1 = 10;
const numero2 = 20;
```

---

# 62. Act

Agora executamos aquilo que queremos testar.

```typescript
const resultado = somar(numero1, numero2);
```

---

# 63. Assert

Finalmente verificamos o resultado.

```typescript
expect(resultado).toBe(30);
```

Esse padrão será muito útil conforme nossos testes forem ficando maiores.

---

# 64. Primeiro exercício para os alunos

Agora nós vamos criar novos testes.

Sem copiar os exemplos anteriores, criem testes para:

```text
100 + 50 = 150
```

```text
100 - 50 = 50
```

```text
10 × 10 = 100
```

```text
100 ÷ 10 = 10
```

Depois executem:

```bash
npm test
```

Todos os testes deverão passar.

---

# 65. Segundo exercício

Agora criem testes com números negativos.

Exemplos:

```text
-10 + 5
```

```text
-10 - 5
```

```text
-5 × 2
```

```text
-20 ÷ 4
```

Primeiro calculem manualmente o resultado esperado.

Depois criem o teste.

---

# 66. Terceiro exercício

Agora vamos testar o número zero.

Criem testes para:

```text
10 + 0
```

```text
10 - 0
```

```text
10 × 0
```

```text
0 ÷ 10
```

Depois executem todos os testes.

---

# 67. Desafio

Criem uma nova função chamada:

```typescript
media()
```

Ela deverá receber dois números e retornar a média.

Exemplo:

```text
10 e 20
```

Cálculo:

```text
(10 + 20) / 2
```

Resultado:

```text
15
```

A função poderá começar assim:

```typescript
export function media(a: number, b: number): number {

}
```

Depois criem pelo menos três testes.

---

# 68. Desafio extra

Criem uma função chamada:

```typescript
dobro()
```

Ela deverá retornar o dobro de um número.

Exemplo:

```text
dobro(5)
```

Resultado:

```text
10
```

Depois criem pelo menos três testes.

---

# 69. Estrutura final do projeto

Ao final da aula deveremos ter algo semelhante a:

```text
calculadora-jest
│
├── node_modules
│
├── src
│   └── calculadora.ts
│
├── tests
│   └── calculadora.test.ts
│
├── jest.config.js
├── package-lock.json
├── package.json
└── tsconfig.json
```

---

# 70. O que é node_modules?

A pasta:

```text
node_modules
```

é criada automaticamente pelo npm.

Ela contém as bibliotecas utilizadas pelo projeto.

Por exemplo:

- Jest
- TypeScript
- ts-jest
- outras dependências

Normalmente não devemos alterar essa pasta manualmente.

---

# 71. O que é package-lock.json?

O arquivo:

```text
package-lock.json
```

é criado automaticamente pelo npm.

Ele registra as versões exatas das dependências instaladas.

Isso ajuda para que diferentes computadores utilizem versões compatíveis das bibliotecas.

---

# 72. Criando o .gitignore

Se vamos publicar o projeto no GitHub, não precisamos enviar a pasta:

```text
node_modules
```

Ela pode possuir milhares de arquivos.

Por isso vamos criar:

```text
.gitignore
```

Dentro dele colocamos:

```gitignore
node_modules/
coverage/
dist/
```

Assim o Git ignora essas pastas.

---

# 73. Por que não enviamos node_modules?

Porque todas as dependências estão registradas no:

```text
package.json
```

Quando outra pessoa baixar nosso projeto, basta executar:

```bash
npm install
```

O npm instalará novamente todas as dependências necessárias.

---

# 74. Como outra pessoa executa nosso projeto?

Imagine que publicamos esse projeto no GitHub.

Outra pessoa pode clonar o repositório e executar:

```bash
npm install
```

Depois:

```bash
npm test
```

Pronto.

As dependências serão instaladas e os testes serão executados.

---

# 75. Fluxo completo que fizemos

Nós começamos criando a pasta:

```bash
mkdir calculadora-jest
```

Entramos nela:

```bash
cd calculadora-jest
```

Criamos o projeto:

```bash
npm init -y
```

Instalamos as dependências:

```bash
npm install -D typescript jest ts-jest @types/jest
```

Criamos o TypeScript:

```bash
npx tsc --init
```

Criamos a configuração do Jest:

```bash
npx ts-jest config:init
```

Depois criamos nossas funções.

Criamos nossos testes.

E executamos:

```bash
npm test
```

Esse é nosso primeiro projeto de testes automatizados com TypeScript e Jest.

---

# 76. Resumo dos principais comandos

## Criar projeto

```bash
npm init -y
```

## Instalar dependências

```bash
npm install -D typescript jest ts-jest @types/jest
```

## Criar tsconfig.json

```bash
npx tsc --init
```

## Criar configuração do Jest

```bash
npx ts-jest config:init
```

## Executar testes

```bash
npm test
```

## Executar em modo watch

```bash
npm test -- --watch
```

---

# 77. Resumo dos principais comandos do Jest

## test()

Cria um teste.

```typescript
test("descrição", () => {

});
```

## describe()

Agrupa testes.

```typescript
describe("grupo", () => {

});
```

## expect()

Define o valor que queremos verificar.

```typescript
expect(resultado)
```

## toBe()

Compara com o valor esperado.

```typescript
expect(resultado).toBe(10);
```

## toThrow()

Verifica se ocorreu um erro.

```typescript
expect(() => funcao()).toThrow();
```

---

# 78. Ligando esta aula com requisitos de teste

Na aula anterior nós estudamos requisitos.

Agora podemos relacionar os dois assuntos.

Imagine este requisito:

```text
A calculadora deverá somar dois números.
```

Podemos transformar isso em:

```typescript
test("deve somar dois números", () => {
  expect(somar(2, 3)).toBe(5);
});
```

Agora outro requisito:

```text
A calculadora não deverá permitir divisão por zero.
```

Transformamos em:

```typescript
test("não deve permitir divisão por zero", () => {
  expect(() => dividir(10, 0))
    .toThrow("Não é possível dividir por zero");
});
```

Ou seja:

```text
Requisito
↓
Código
↓
Teste
↓
Resultado
```

Isso será cada vez mais importante nas próximas aulas.

---

# 79. Perguntas para revisão

1. O que é Jest?

2. Para que utilizamos Jest?

3. O que é TypeScript?

4. Qual a função do npm?

5. Para que serve `npm init -y`?

6. Para que serve o arquivo `package.json`?

7. Para que serve o arquivo `tsconfig.json`?

8. Para que serve o arquivo `jest.config.js`?

9. O que faz o comando `npm test`?

10. Para que serve `test()`?

11. Para que serve `expect()`?

12. Para que serve `toBe()`?

13. Para que serve `describe()`?

14. Para que serve `toThrow()`?

15. O que significa quando o Jest apresenta `PASS`?

16. O que significa quando um teste apresenta `FAIL`?

17. O que significa o padrão AAA?

18. Por que não enviamos a pasta `node_modules` para o GitHub?

---

# 80. Atividade prática final

Agora vamos desenvolver um pequeno sistema utilizando **classes, objetos e testes automatizados com Jest**.

O projeto será um sistema simples para controlar uma **garagem de carros**.

A ideia é colocar em prática os conceitos de programação orientada a objetos que vocês já estudaram, enquanto utilizamos o Jest para verificar se as regras do sistema estão funcionando corretamente.

---

## 80.1 Criando o projeto

Criem uma nova pasta chamada:

```text
garagem-jest
```

Inicializem o projeto:

```bash
npm init -y
```

Instalem:

- TypeScript
- Jest
- ts-jest
- @types/jest

A estrutura inicial deverá ficar semelhante a:

```text
garagem-jest
│
├── src
│
├── tests
│
├── jest.config.js
├── package.json
└── tsconfig.json
```

---

## 80.2 Criando a classe Car

Dentro da pasta `src`, criem:

```text
Car.ts
```

A classe `Car` deverá representar um carro.

Ela deverá possuir, no mínimo, as seguintes propriedades:

```text
brand
model
year
```

Exemplo:

```typescript
const car = new Car("Toyota", "Corolla", 2025);
```

O aluno deverá decidir quais propriedades serão `private` e quais métodos serão necessários para acessar ou alterar os dados.

---

## 80.3 Criando a classe Garage

Agora criem:

```text
Garage.ts
```

A classe `Garage` deverá representar uma garagem capaz de armazenar vários carros.

Ela deverá possuir uma lista de carros.

Exemplo:

```typescript
const garage = new Garage();
```

A classe deverá possuir métodos para:

### Adicionar um carro

```text
addCar()
```

### Remover um carro

```text
removeCar()
```

### Consultar a quantidade de carros

```text
getCarCount()
```

### Procurar um carro pelo modelo

```text
findCarByModel()
```

Os nomes dos métodos e propriedades deverão estar em **inglês**.

---

## 80.4 Regras do sistema

A garagem deverá seguir algumas regras simples.

### Regra 1 — Adicionar carros

Ao adicionar um carro, ele deverá ser armazenado na garagem.

Exemplo:

```text
Toyota Corolla
Ford Mustang
Honda Civic
```

Depois de adicionar três carros:

```text
Quantidade de carros: 3
```

---

### Regra 2 — Remover carros

Ao remover um carro, ele não deverá mais fazer parte da garagem.

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

---

### Regra 3 — Procurar por modelo

O método `findCarByModel()` deverá procurar um carro pelo seu modelo.

Por exemplo:

```typescript
garage.findCarByModel("Corolla");
```

Se o carro existir, o método deverá retornar o objeto correspondente.

Caso contrário, deverá retornar:

```text
undefined
```

---

### Regra 4 — Não permitir carros duplicados

A garagem não deverá permitir dois carros com a mesma combinação de:

```text
brand + model + year
```

Por exemplo, não será permitido cadastrar duas vezes:

```text
Toyota Corolla 2025
```

Caso isso aconteça, o sistema deverá lançar um erro.

---

## 80.5 Criando os testes

Dentro da pasta:

```text
tests
```

criem:

```text
Garage.test.ts
```

Os testes deverão verificar o comportamento das classes.

Criem **pelo menos 10 testes**.

---

### Testes obrigatórios

#### 1. Criar um carro

Verifique se é possível criar corretamente um objeto da classe `Car`.

---

#### 2. Adicionar um carro

Crie uma garagem, adicione um carro e verifique se a quantidade de carros é:

```text
1
```

---

#### 3. Adicionar vários carros

Adicione pelo menos três carros e verifique se a quantidade retornada é:

```text
3
```

---

#### 4. Remover um carro

Adicione um carro, remova-o e verifique se a garagem ficou vazia.

---

#### 5. Procurar um carro existente

Adicione um carro e utilize:

```text
findCarByModel()
```

Verifique se o carro correto foi encontrado.

---

#### 6. Procurar um carro inexistente

Procure por um modelo que não foi cadastrado.

O resultado esperado deverá ser:

```text
undefined
```

---

#### 7. Não permitir carros duplicados

Tente adicionar duas vezes o mesmo carro.

O segundo cadastro deverá gerar um erro.

Utilize:

```typescript
toThrow()
```

para testar essa situação.

---

#### 8. Verificar a marca do carro encontrado

Procure um carro pelo modelo e verifique se a propriedade `brand` está correta.

---

#### 9. Verificar o ano do carro encontrado

Procure um carro pelo modelo e verifique se a propriedade `year` está correta.

---

#### 10. Remover um carro entre vários

Adicione três carros, remova apenas um deles e verifique se os outros dois continuam na garagem.

---

## 80.6 Utilizando o padrão AAA

Organizem os testes utilizando o padrão:

```text
Arrange
Act
Assert
```

Por exemplo:

```typescript
test("deve adicionar um carro à garagem", () => {

  // Arrange
  const garage = new Garage();
  const car = new Car("Toyota", "Corolla", 2025);

  // Act
  garage.addCar(car);

  // Assert
  expect(garage.getCarCount()).toBe(1);

});
```

Não é obrigatório utilizar exatamente esse código.

O objetivo é entender a separação entre:

```text
Preparar
↓
Executar
↓
Verificar
```

---

## 80.7 Estrutura esperada

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

## 80.8 Requisitos do exercício

O projeto deverá obrigatoriamente possuir:

- Uma classe `Car`
- Uma classe `Garage`
- Objetos criados a partir dessas classes
- Propriedades tipadas com TypeScript
- Métodos para manipulação dos objetos
- Uma lista de carros dentro da garagem
- Pelo menos 10 testes automatizados
- Uso de `test()`
- Uso de `expect()`
- Uso de `toBe()`
- Uso de `toThrow()`
- Uso do padrão AAA em pelo menos alguns testes
- Todos os testes executando corretamente com:

```bash
npm test
```

---

## 80.9 Desafio adicional

Depois que todos os testes obrigatórios estiverem funcionando, adicionem uma nova funcionalidade à garagem.

Uma possibilidade é criar:

```text
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

---

## 80.10 Executando os testes

Depois de terminar o projeto, execute:

```bash
npm test
```

Todos os testes deverão passar.

O objetivo não é apenas fazer o programa funcionar.

O objetivo é utilizar o **Jest para provar, por meio de testes automatizados, que as classes e suas regras estão funcionando corretamente**.

---

# 81. Conclusão

Nesta aula nós demos nosso primeiro passo prático com testes automatizados.

Aprendemos que o Jest é uma ferramenta que executa testes e compara o resultado obtido com aquilo que nós esperávamos.

Também aprendemos que o TypeScript nos ajuda a criar código com tipos bem definidos, o que reduz diversos erros durante o desenvolvimento.

Nós configuramos nosso projeto do zero, instalamos as dependências, criamos funções matemáticas e escrevemos nossos primeiros testes automatizados.

Nas próximas aulas, nós poderemos avançar para testes mais próximos de sistemas reais, utilizando:

- Objetos
- Classes
- Serviços
- Validações
- Cadastro de usuários
- Regras de negócio
- Mocks
- APIs

Mas a base continuará sendo a mesma:

```text
Preparar
Executar
Verificar
```

Ou, como vimos:

```text
Arrange
Act
Assert
```

Quanto melhor nós entendermos essa base, mais fácil será trabalhar com testes em projetos maiores.
