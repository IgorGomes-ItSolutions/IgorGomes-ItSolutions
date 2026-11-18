# Guia de Git para manter o portfólio

## Fluxo de atualização

1. Abra o repositório correto no GitHub Desktop ou terminal e confira se há alterações locais.
2. Atualize a `main` somente quando não houver trabalho local pendente. Não descarte alterações para atualizar.
3. Crie uma branch com nome descritivo, por exemplo `docs/atualizar-readme` ou `feat/validar-documentos`.
4. Faça uma alteração com objetivo claro. Atualize a documentação correspondente.
5. Execute a validação indicada no README. Registre o que foi testado e o que ficou pendente.
6. Revise o diff, verificando arquivos gerados, dados pessoais e credenciais.
7. Crie um commit descritivo e envie a branch. Abra um pull request com problema, mudança e validação.
8. Revise e integre quando as verificações aplicáveis passarem.

## Exemplo no terminal

Na raiz do repositório, com o trabalho local já salvo:

```bash
git status
git switch main
git pull --ff-only
git switch -c docs/atualizar-readme
# Edite o README e confira as alterações.
git diff --check
git diff
git add README.md
git commit -m "docs: atualizar objetivo e estado do projeto"
git push -u origin docs/atualizar-readme
```

Se `pull --ff-only` falhar, investigue a divergência; não use `reset --hard` para forçar a atualização.

## Padrão de documentação

- Explique primeiro o problema, a entrega e a situação atual.
- Diferencie código preparado, teste local, execução em nuvem e uso em produção.
- Use caminhos relativos para arquivos do mesmo repositório.
- Publique apenas evidências revisadas e dados fictícios ou autorizados.
- Não versione `.env`, tokens, senhas, bancos locais ou dados de usuários.
- Informe quando houver apoio de IA e descreva as verificações efetivamente realizadas.
- Organize pastas conforme o projeto: `src/` ou `app/` para código; `tests/` para testes; `docs/` para documentação. Notebooks, SQL e JSON de ADF podem ter pastas próprias.
- Não mova arquivos apenas para imitar uma estrutura: atualize imports, workflows e links quando um movimento for necessário.
- Licença é uma decisão do autor; não copie uma licença sem entender as permissões concedidas.
