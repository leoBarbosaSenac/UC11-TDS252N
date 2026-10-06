# Tutorial: Configurando um projeto TypeScript

Este tutorial apresenta uma configuração básica de um projeto **TypeScript com Node.js**, utilizando o `tsc` para compilação e o `tsx` para executar arquivos TypeScript diretamente.

## 1. Iniciar o projeto

Crie uma pasta para o projeto, abra o terminal dentro dela e execute:

```bash
npm init -y
```

Isso cria o arquivo `package.json`, responsável pelas configurações e dependências do projeto.

## 2. Instalar o TypeScript

Instale o TypeScript como uma dependência de desenvolvimento:

```bash
npm install typescript@^6 -D
```

O `-D` indica que o TypeScript será instalado como uma **devDependency**.

## 3. Criar o `tsconfig.json`

Gere o arquivo de configuração do TypeScript:

```bash
npx tsc --init
```

Depois, substitua todo o conteúdo do `tsconfig.json` por:

```json
{
  "compilerOptions": {
    "target": "ES2020",
    "module": "CommonJS",
    "rootDir": "./src",
    "outDir": "./dist",

    "strict": true,
    "esModuleInterop": true
  },
  "include": ["src/**/*.ts"],
  "exclude": ["node_modules", "dist"]
}
```

### O que essas configurações fazem?

| Configuração | Função |
|---|---|
| `target` | Define a versão do JavaScript gerado. |
| `module` | Define o sistema de módulos utilizado pelo projeto. |
| `rootDir` | Indica onde ficam os arquivos TypeScript. |
| `outDir` | Indica onde serão colocados os arquivos JavaScript compilados. |
| `strict` | Ativa verificações mais rigorosas do TypeScript. |
| `esModuleInterop` | Facilita a utilização de módulos CommonJS e ES Modules. |
| `include` | Define quais arquivos `.ts` serão considerados pelo compilador. |
| `exclude` | Define arquivos e pastas que devem ser ignorados. |

## 4. Criar a pasta `src`

Crie uma pasta chamada `src` na raiz do projeto:

```text
meu-projeto/
├── node_modules/
├── src/
├── package.json
├── package-lock.json
└── tsconfig.json
```

Dentro dela, crie o arquivo `Main.ts`:

```text
meu-projeto/
├── node_modules/
├── src/
│   └── Main.ts
├── package.json
├── package-lock.json
└── tsconfig.json
```

Você pode testar com:

```typescript
console.log("Olá, TypeScript!");
```

## 5. Instalar o TSX

O `tsx` permite executar arquivos TypeScript diretamente, sem precisar compilá-los manualmente antes:

```bash
npm install tsx -D
```

## 6. Instalar o Jest

O **Jest** é um framework utilizado para criar e executar testes automatizados.

Instale-o como dependência de desenvolvimento:

```bash
npm install --save-dev jest
```

O `--save-dev` indica que o Jest será utilizado durante o desenvolvimento do projeto.

## 7. Executar o código

Como o arquivo `Main.ts` está dentro da pasta `src`, execute:

```bash
npx tsx src/Main.ts
```

O resultado será:

```text
Olá, TypeScript!
```

