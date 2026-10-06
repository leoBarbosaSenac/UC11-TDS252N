# 🧪 TypeScript + Jest

## 1. Criar o projeto

```bash
npm init -y
```

Inicializa um projeto Node.js.

---

## 2. Instalar TypeScript e Jest

```bash
npm install -D typescript jest ts-jest @types/jest
```

Instala:

* `typescript` — TypeScript
* `jest` — testes automatizados
* `ts-jest` — integração Jest + TypeScript
* `@types/jest` — tipos do Jest

---

## 3. Configurar o Jest

```bash
npx ts-jest config:init
```

Cria o arquivo:

```text
jest.config.js
```

---

## 4. Criar o `tsconfig.json`

```bash
npx tsc --init
```

Utilize esta configuração:

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

---

# 📁 Estrutura

```text
projeto/
├── src/
├── tests/
├── jest.config.js
├── package.json
└── tsconfig.json
```

---

# 🧪 Comandos do Jest

### Executar todos os testes

```bash
npx jest
```

### Executar mostrando detalhes

```bash
npx jest --verbose
```

### Executar automaticamente ao alterar arquivos

```bash
npx jest --watch
```

---

# 🔎 Principais comandos de teste

### `describe()`

Agrupa testes.

```typescript
describe("Pessoa", () => {

})
```

### `test()`

Cria um teste.

```typescript
test("deve criar uma pessoa", () => {

})
```

### `it()`

Outra forma de criar um teste.

```typescript
it("deve criar uma pessoa", () => {

})
```

### `expect()`

Define o resultado esperado.

```typescript
expect(resultado).toBe(valor)
```

---

# ✅ Principais Matchers

```typescript
expect(valor).toBe(valor)
expect(valor).not.toBe(valor)

expect(objeto).toEqual(objeto)

expect(valor).toBeTruthy()
expect(valor).toBeFalsy()

expect(valor).toBeNull()
expect(valor).toBeUndefined()

expect(array).toContain(valor)
expect(array).toHaveLength(3)

expect(numero).toBeGreaterThan(10)
expect(numero).toBeGreaterThanOrEqual(10)

expect(numero).toBeLessThan(10)
expect(numero).toBeLessThanOrEqual(10)

expect(() => metodo()).toThrow()
expect(() => metodo()).toThrow("mensagem")
```

---

# ⚙️ TypeScript

### Compilar

```bash
npx tsc
```

### Verificar erros sem gerar arquivos

```bash
npx tsc --noEmit
```

---

# 📦 Scripts recomendados

No `package.json`:

```json
"scripts": {
  "test": "jest",
  "test:watch": "jest --watch"
}
```

Executar:

```bash
npm test
```

ou:

```bash
npm run test:watch
```
