# Arquitetura do AAGRIFAM Romaneios

A versão atual é uma aplicação estática composta por um único arquivo principal, `src/index.html`, contendo HTML, CSS e JavaScript. A persistência ocorre no navegador por meio de `localStorage`, o que permite validar o fluxo operacional sem servidor.

## Modelo lógico

| Entidade | Finalidade |
|---|---|
| `produtores` | Cadastro de produtores ou vendedores vinculados aos romaneios. |
| `clientes` | Cadastro das instituições compradoras. |
| `grupos` | Classificação de alimentos e limites semanais. |
| `produtos` | Produtos, unidades, lotes e preços. |
| `romaneios` | Documento de entrega com produtor, cliente, itens e valor total. |

## Evolução recomendada

Para produção, recomenda-se migrar a persistência para banco de dados relacional, criar autenticação real, registrar auditoria de alterações e implementar rotina automática de backup.
