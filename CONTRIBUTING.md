# Guia de Contribuição

Obrigado pelo interesse em contribuir com o projeto Aagrifam Romaneios!

## Como contribuir

### 1. Reportar problemas
- Use as **Issues** do GitHub
- Descreva o problema com clareza
- Inclua passos para reproduzir
- Adicione capturas de tela quando possível

### 2. Sugerir melhorias
- Abra uma Issue com a tag `enhancement`
- Explique o caso de uso
- Sugira como implementar (opcional)

### 3. Enviar código

```bash
# 1. Faça fork do repositório

# 2. Clone seu fork
git clone https://github.com/SEU-USUARIO/aagrifam-romaneios.git
cd aagrifam-romaneios

# 3. Crie uma branch
git checkout -b feature/nome-da-feature
# ou
git checkout -b fix/descricao-do-bug

# 4. Faça suas alterações e teste no navegador

# 5. Commit seguindo o padrão Conventional Commits
git commit -m "feat: adiciona filtro por mês de referência"
git commit -m "fix: corrige cálculo de total quando quantidade é decimal"
git commit -m "docs: atualiza README com novo print"

# 6. Push e abra Pull Request
git push origin feature/nome-da-feature
```

## Padrão de commits (Conventional Commits)

| Prefixo | Quando usar |
|---|---|
| `feat:` | Nova funcionalidade |
| `fix:` | Correção de bug |
| `docs:` | Apenas documentação |
| `style:` | Formatação, sem mudança de lógica |
| `refactor:` | Refatoração sem mudança de comportamento |
| `test:` | Adição ou correção de testes |
| `chore:` | Tarefas de manutenção, build, deps |

## Código de conduta

- Seja respeitoso e construtivo
- Foque no problema, não na pessoa
- Aceite feedback como oportunidade de aprendizado
- Documente decisões importantes
