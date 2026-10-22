# Especificação — secure-api-pipeline

**Semana:** 04/12 a 10/12/2026
**Entrega final:** API corrigida + pipeline funcionando + relatório

## Contexto

Uma API interna foi escrita sem cuidado de segurança. Você vai mapear as falhas, corrigi-las e deixar um pipeline que impede que falhas desse tipo voltem a entrar no código — o trabalho combinado de AppSec e DevSecOps.

## Escopo

1. **Construir a base vulnerável** — uma API pequena sua com três falhas introduzidas de propósito: controle de acesso quebrado (IDOR), injeção em consulta e token mal configurado.
2. **Explorar e documentar** — demonstrar cada falha (Burp Suite ou requisições diretas), explicar o impacto e como ela seria abusada.
3. **Corrigir** — aplicar a correção de cada falha, com o diff à vista.
4. **Automatizar** — um workflow no GitHub Actions que roda, a cada push e PR: gitleaks (segredos), Semgrep (análise estática), Trivy (dependências e imagem) e OWASP ZAP (teste dinâmico básico). Achado relevante reprova.
5. **Relatar** — o relatório com cada falha, a correção e o antes/depois do pipeline.

## Critério de aceite

- [ ] As três falhas demonstradas, com impacto explicado
- [ ] Correção de cada uma, com o diff referenciado
- [ ] Pipeline que reprova um PR com segredo ou dependência vulnerável (mostrar a execução vermelha e depois verde)
- [ ] `docs/vulnerabilidades.md` com falha, impacto e correção lado a lado
- [ ] Nenhum segredo real no histórico do repositório
- [ ] README com o resultado em uma linha

## Fora de escopo

Testar a API de terceiros. Técnicas de ataque fora do seu próprio ambiente.

## Fases (issues da semana)

| Dia | Fase | Entrega do dia |
|---|---|---|
| Sex 04/12 | API base com as falhas | API rodando localmente |
| Seg 07/12 | Explorar e documentar as falhas | As três falhas demonstradas |
| Ter 08/12 | Corrigir as falhas | Versão corrigida, com os diffs |
| Qua 09/12 | Pipeline completo no Actions | gitleaks, Semgrep, Trivy e ZAP rodando |
| Qui 10/12 | Reprovar, aprovar e fechar | Execução vermelha e verde, `docs/vulnerabilidades.md`, README |
