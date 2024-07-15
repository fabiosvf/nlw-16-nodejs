#### NLW #16 - Node.js
# 🚀 Projeto Plann.er

## Sobre
- Projeto Backend para planejamento de viagem, desenvolvido em Node.js com TypeScript

## Configurando o Ambiente de Desenvolvimento
- A IDE de Desenvolvimento será o **Visual Studio Code**, ou apenas, **VSCode**
- Instale as seguintes extensões do VS Code
  - ESLint
  - Prisma
- Configure o seguinte parâmetro no arquivo `settings.json`.
```
"editor.codeActionsOnSave": {
  "source.fixAll.eslint": "explicit"
}
```
  - _Esse parâmetro é uma configuração do `Eslint` para formatar o código automaticamente_
- Configure também o seguinte parâmetro no arquivo `settings.json`
```
"[prisma]": {
  "editor.formatOnSave": true
}
```
  - _Esse parâmetro é uma configuração do `Prisma` para formatar o codigo do modelo ORM_
- **Nota:** Para abrir o arquivo `settings.json` pressione `CTRL + P` em seguida digite `> settings.json`, clique no primeiro item da pesquisa.

## Configurando o Node.js
- Consulte o site do [`nodejs.org`](nodejs.org) para obter informações detalhadas.
- Instale a versão LTS que no momento está em `20.15.0`
- De preferencia utilize a instalação via `Package Manager`, e para o caso do Windows, utilizamos o Gerenciador de Pacotes [`Chocolatey`](https://chocolatey.org/)

## Iniciando o projeto
- Crie uma pasta para o projeto e acesse a pasta via terminal e digite o seguinte comando:
```
$ npm init -y
```
- Este comando irá iniciar o projeto com o arquivo `package.json` que é responsável por todas as configurações do projeto `Node`
- Em seguida vamos instalar o `TypeScript` e seu pacote de tipos como dependência de desenvolvimento. E para isso, digite:
```
$ npm i typescript @types/node -D
```
- Agora precisamos criar o arquivo `tsconfig.json` que é o arquivo de configuração do `TypeScript`. Então digite:
```
$ npx tsc --init
```
- Para obter as configurações padrão recomendadas, procure no google por:
```
tsconfig bases
```
- Acesse o repositorio encontrado, que é github.com/tsconfig/bases
- Nesse arquivo você vai localizar no README.md a versão Node 20, clique no link ao lado chamado `@tsconfig/node20` que direcionará para o site do `NPM`
- Copie todo o conteúdo do arquivo `tsconfig.json` sugerido e substitua o conteudo no arquivo do projeto
- E pra finalizar essa parte, como o `Node` por padrão não reconhece o `TypeScript`, a gente vai precisar instalar uma ferramenta como dependencia de desenvolvimento que ficará responsável por converter o código `TypeScript` em `JavaScript` nativo. Para isso digite:
```
$ npm i tsx -D
```
- Para fins de teste, crie a pasta `src` na raiz do projeto e em seguida o arquivo `server.ts` dentro dessa pasta e digite o código:
```ts
console.log('Hello World')
```
- E para executar esse código, digite no terminal o seguinte comando:
```
$ npx tsx src/server.ts
```
- Agora, caso queira que o tsx fique escultando o código, e execute automaticamente toda ver que identificar alterações no código, digite no terminal o seguinte comando:
```
$ npx tsx watch src/server.ts
```
- Para automatizar um pouco mais esse procedimento, adicione o seguinte parâmetro na sessão `scripts` do arquivo `package.json`:
```json
  "scripts": {
    "dev": "tsx watch src/server.ts"
  },
```
- E agora, pra executar essa rotina, digite o seguinte comando no terminal:
```
$ npm run dev
```

## Instalando o `Fastify`
- Primeiro vamos instalar o `Fastify` que é framework utilizado para subir um servidor que ficará escutando as requisições através de uma porta específica previamente configurada. Para instalar digite no terminal:
```
$ npm i fastify
```
