# Visão técnica

## Componentes

O pacote tem uma arquitetura deliberadamente pequena:

```text
package.json ── aponta main/exports ──> index.cjs ── exporta opções ──> Prettier no consumidor
```

- `package.json` define identidade, compatibilidade de módulos, arquivo publicado, scripts e dependências.
- `index.cjs` define o objeto de configuração compartilhada.
- `package-lock.json` e `bun.lock` registram resoluções de dependências para npm e Bun.
- `README.md`, `AGENTS.md`, `CLAUDE.md` e `docs/` explicam uso e manutenção.

Não existem fontes TypeScript, etapa de compilação, fixtures, suíte de testes de aplicação ou dependência de runtime declarada no estado atual.

## Fluxo de resolução

1. O consumidor instala Prettier e `@arapucajs/prettier`.
2. O consumidor referencia `@arapucajs/prettier` na configuração do Prettier.
3. O Prettier resolve o nome do pacote e carrega seu ponto de entrada CommonJS.
4. O objeto exportado fornece opções padrão; opções do projeto consumidor podem prevalecer pela resolução normal do Prettier.

O campo `type: module` do pacote não muda o formato do arquivo `.cjs`; `index.cjs` permanece CommonJS. Preservar essa extensão é parte do contrato de carregamento atual.

## Limites observados

- A integração com EdgeJS não está habilitada: a opção `plugins` está comentada e `prettier-plugin-edgejs` não consta em `dependencies`.
- O arquivo não limita quais tipos de arquivo são formatados; o alcance é determinado pelo Prettier no consumidor.
- `printWidth` expressa uma preferência de layout, não um corte absoluto de tamanho de linha.
- O script `test` não contém testes reais. A verificação disponível declarada é `lint`.
- `.github/workflows/ci.yml` verifica mensagens de commit e executa etapas condicionais de TypeScript e testes com Bun. Como o repositório não tem arquivos TypeScript nem suíte Bun declarada, essas etapas não validam atualmente o objeto de configuração.
- `.github/workflows/deploy.yml` publica em GitHub Packages e npm após uma release publicada; `.github/workflows/release.yml` executa Release Please. Esses fluxos dependem das permissões e secrets configurados no GitHub.

## Mudanças futuras

Se a configuração ganhar plugins, arquivos adicionais, formatos de módulo ou uma etapa de build, atualize esta arquitetura e as referências de pacote na mesma mudança. Verifique o conteúdo efetivo do tarball antes de ampliar afirmações sobre o que é publicado.
