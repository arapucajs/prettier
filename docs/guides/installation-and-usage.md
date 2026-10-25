# Instalação e uso

`@arapucajs/prettier` fornece as opções base do Prettier usadas pela equipe ArapucaJS. O projeto consumidor instala o formatador e o preset como dependências de desenvolvimento.

## Instalar

Com Bun:

```sh
bun add -D prettier @arapucajs/prettier
```

Com npm:

```sh
npm install --save-dev prettier @arapucajs/prettier
```

## Configurar

Adicione ao `package.json` do consumidor:

```json
{
  "prettier": "@arapucajs/prettier"
}
```

Também é possível usar um arquivo de configuração compatível com Prettier que aponte para o preset. O pacote publica `index.cjs` como CommonJS; mantenha uma forma de carregamento aceita pela versão do Prettier usada no projeto.

## Executar

O pacote não traz um executável próprio. Use a CLI do Prettier instalado no consumidor, por exemplo:

```sh
npx prettier --check .
npx prettier --write .
```

Com Bun, os comandos equivalentes podem ser executados por `bunx prettier --check .` e `bunx prettier --write .`.

## Sobrescrever opções

Opções locais do consumidor podem complementar ou substituir os padrões compartilhados na configuração do Prettier, conforme a precedência normal do Prettier. Mantenha as sobrescritas locais pequenas e registre o motivo quando houver divergência entre repositórios.

## EdgeJS

A mensagem histórica do README diz que o plugin EdgeJS é instalado e configurado, mas isso não corresponde ao estado atual do projeto: `prettier-plugin-edgejs` não está em `dependencies` e a configuração de plugin em `index.cjs` está comentada. Assim, templates Edge não têm suporte habilitado por este preset. Quem precisar formatá-los deve adicionar e configurar um plugin compatível no próprio projeto consumidor.

## Problemas comuns

- **O preset não é encontrado:** confirme que `@arapucajs/prettier` está instalado no mesmo projeto em que o Prettier é executado e que o nome no campo `prettier` está correto.
- **O Prettier não carrega o preset:** confirme a versão do Node/Prettier e use uma configuração CommonJS compatível com a resolução do ambiente.
- **Templates `.edge` não são formatados:** a integração EdgeJS não está ativa no pacote atual; instale/configure um plugin no consumidor ou proponha sua inclusão como mudança do preset.
