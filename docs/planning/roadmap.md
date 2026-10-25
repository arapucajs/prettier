# Plano de evolução

Este documento registra trabalho de qualidade observado no repositório. Não anuncia funcionalidades futuras como compromissos ou funcionalidades já disponíveis.

## Prioridades sugeridas

1. **Definir a política para EdgeJS.** Decidir se o preset deve instalar/carregar o plugin ou se o consumidor o adiciona. Se for incluído, verificar compatibilidade entre a versão do Prettier e do plugin, comportamento de carregamento automático e impacto no pacote publicado.
2. **Adicionar validação de configuração.** Criar uma verificação que importe/carregue `index.cjs` com a versão suportada do Prettier e detecte opções inválidas ou incompatíveis.
3. **Substituir o placeholder de testes.** Adicionar casos verificáveis para os valores exportados e um teste de formatação representativo, depois ajustar `npm test` e o hook `pre-commit` para executar validação útil.
4. **Declarar compatibilidade.** Definir e documentar versões suportadas de Node e Prettier no manifesto, após testar essas versões.
5. **Validar publicação e CI.** Manter `docs/architecture/overview.md` alinhado aos workflows existentes e verificar no GitHub a configuração de permissões/secrets quando houver mudanças nesses fluxos.

## Critérios de conclusão

- O comportamento público está coberto por validação executável.
- README, referências e instruções de agentes refletem configuração, versões e comandos reais.
- npm e Bun resolvem os mesmos requisitos declarados, com lockfiles atualizados.
- O conteúdo publicado inclui os arquivos documentados.
- Plugins externos são testados junto da versão de Prettier pretendida.

## Fora do escopo atual

Não há decisão registrada para migrar para TypeScript, acrescentar uma CLI ou habilitar EdgeJS automaticamente. Essas mudanças exigem uma escolha explícita de manutenção e compatibilidade antes de serem consideradas entregues.
