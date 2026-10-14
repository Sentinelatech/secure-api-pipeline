# secure-api-pipeline

Segurança de aplicação de ponta a ponta: uma API com falhas conhecidas é analisada, as falhas são corrigidas e um pipeline de integração contínua passa a barrar código inseguro automaticamente antes do merge. Une o lado de quem encontra o problema (AppSec) e o de quem o impede de voltar (DevSecOps).

> Projeto 7 de 7 do laboratório [sentinelatech](https://github.com/sentinelatech). Área: **AppSec e DevSecOps**. É o projeto que mais aproveita a sua experiência de backend.

## Por que isso importa em segurança

Quem programa já conhece o terreno onde as falhas moram: autenticação, controle de acesso, entrada de dados. Mostrar que você identifica uma vulnerabilidade no código, corrige e automatiza a verificação é exatamente o perfil que AppSec e DevSecOps procuram.

## Objetivo

Partir de uma API com vulnerabilidades do OWASP Top 10, documentar cada falha e sua correção, e montar um pipeline no GitHub Actions que reprova o código quando encontra segredo exposto, dependência vulnerável ou padrão inseguro.

## Estrutura

```
docs/especificacao.md       escopo e critério de aceite
docs/vulnerabilidades.md     cada falha: o que é, impacto, correção
app/                         a API (versão com falhas e versão corrigida, por branch ou tag)
.github/workflows/           o pipeline de verificação
relatorio/                   o relatório, com o antes e depois
```

## Falhas abordadas

Controle de acesso quebrado (IDOR) · injeção em consulta · autenticação por token mal configurada. Todas documentadas com a correção ao lado.

## Pipeline

A cada push ou pull request, o GitHub Actions roda: varredura de segredos (gitleaks), análise estática (Semgrep), checagem de dependências e imagem (Trivy) e um teste dinâmico básico (OWASP ZAP). Achado relevante reprova o merge.

## Ferramentas

Node ou Python para a API · Burp Suite Community (exploração) · GitHub Actions · gitleaks · Semgrep · Trivy · OWASP ZAP.

## Resultado

<!-- Preencher ao fim -->

## Aviso

A API é sua, roda no seu ambiente, e as falhas são introduzidas de propósito para estudo e correção. Nada aqui é feito contra sistema de terceiros. Nenhum segredo real é versionado — o pipeline existe justamente para garantir isso.
