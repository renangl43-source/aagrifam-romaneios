# Changelog

Todas as mudanças relevantes neste projeto serão documentadas aqui.

O formato segue [Keep a Changelog](https://keepachangelog.com/pt-BR/1.1.0/) e o projeto adota [Versionamento Semântico](https://semver.org/lang/pt-BR/).

## [0.4.0] — 2026-05-01
### Adicionado
- Aba **Relatórios** com tipos Semanal, Mensal e Personalizado
- Cards de resumo do período (romaneios, valor, quantidade, clientes, produtores)
- Análises por produtor, cliente, grupo e status
- Lista detalhada de romaneios e produtos consolidados do período
- Exportação CSV (compatível com Excel/Google Sheets)
- Impressão dedicada do relatório

## [0.3.0] — 2026-05-01
### Adicionado
- Cadastro de **produtores/vendedores** com edição, exclusão e status ATIVO/INATIVO
- Vínculo do produtor ao romaneio via `produtorId`
- Campo **Status de entrega** (PENDENTE, EM SEPARAÇÃO, ENTREGUE, CANCELADO)
- Filtros na lista de romaneios por período, cliente, produtor e status
- Dropdown de status editável direto na tabela
- Dashboard expandido com contadores de status

## [0.2.0] — 2026-05-01
### Adicionado
- Layout do romaneio fiel ao modelo oficial Aagrifam
- Botão de Imprimir / Gerar PDF
- Pré-visualização antes da impressão
- Campos: empresa, cliente, produtor, produtos, quantidades, valores, observações

## [0.1.0] — 2026-05-01
### Adicionado
- Protótipo inicial em HTML com login, cadastros e dashboard
- Persistência de dados via `localStorage`
- Cadastro de clientes/instituições
- Cadastro de produtos
- Criação e listagem de romaneios
