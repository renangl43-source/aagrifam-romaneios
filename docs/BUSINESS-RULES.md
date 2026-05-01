# Regras de Negócio

Este documento resume as regras adotadas no protótipo estático do sistema de romaneios.

| Área | Regra aplicada |
|---|---|
| Login | Acesso demonstrativo com usuário `admin@aagrifam.local` e senha `123456`. |
| Cadastros | Os registros são salvos localmente no navegador do usuário. |
| Romaneios | Cada romaneio deve possuir número, data, produtor, cliente e pelo menos um item. |
| Cálculo | O total do item corresponde a `quantidade × valor unitário`; o total do romaneio soma todos os itens. |
| Impressão | A impressão usa o recurso nativo do navegador e pode ser salva em PDF. |
| Relatórios | Os totais são calculados com base nos romaneios salvos no navegador. |

## Limitação da versão atual

Por utilizar `localStorage`, os dados não são compartilhados entre computadores ou usuários. Para operação definitiva, é necessário backend com banco de dados centralizado.
