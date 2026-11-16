# 🧑‍⚖️ Revisão Humana x Custo do Erro (Human-in-the-loop)

**🔗 Demo ao vivo: https://moniquesilva79.github.io/revisao-humana-ia/**

Encontra o **percentual ótimo de revisão humana** sobre o que a IA produz. A ideia é revisar primeiro os itens de **menor confiança**, até o ponto em que revisar mais custa mais do que os erros evitados. Compara com não revisar nada e com revisar tudo.

## 🎯 Problema que resolve
Ao colocar IA em produção, a pergunta "vamos revisar tudo?" divide o time. Revisar 100% anula boa parte do ganho, e não revisar nada pode sair caro em multas, retrabalho e imagem. Esta calculadora transforma a discussão em números: precisão da IA, custo de revisar, custo de errar e quanto a nota de confiança da IA separa erros de acertos.

## ✨ Funcionalidades
- Volume, precisão da IA e poder de separação da nota de confiança
- Custo de revisão por item e taxa de detecção do revisor
- Custo médio de um erro que chega ao cliente
- Percentual ótimo, custo total, erros que chegam ao cliente e economia frente a revisar 0% e 100%
- Curva de custo total, de revisão e de erros e tabela comparativa de estratégias

## 🧮 Como o cálculo funciona
```
g(f)        = 1 − (1 − f)^k        (parcela dos erros entre os f% de menor confiança)
custo(f)    = itens × f × custo de revisão
            + erros da IA × (1 − g(f) × detecção do revisor) × custo do erro
ótimo       = f de menor custo total (busca de 0% a 100%, passo de 0,5%)
```

## 📊 Exemplo (valores padrão)
| Indicador | Valor |
|---|---|
| Itens/mês e precisão | 40.000 itens, 94% de precisão (2.400 erros) |
| Revisão ótima | **48,5%** dos itens (19.400/mês) |
| Erros que chegam ao cliente | 280/mês (88,3% evitados) |
| Custo total | R$ 70.931/mês |
| Economia x revisar 100% | R$ 38.669/mês |

## 🧰 Tecnologias
HTML, CSS e JavaScript puros, sem frameworks, sem dependências e sem servidor. Publicado no GitHub Pages.

## 🚀 Como rodar localmente
```bash
git clone https://github.com/MoniqueSilva79/revisao-humana-ia.git
cd revisao-humana-ia
python -m http.server 8000   # e acesse http://localhost:8000
```

## ⚠️ Limitações
É um modelo simplificado: o parâmetro k (separação da confiança) deve ser medido com um conjunto de teste rotulado. Em decisões reguladas (crédito, saúde, jurídico), a revisão pode ser obrigatória independentemente do custo.

## 🗺️ Próximos passos
- [ ] Estimar k a partir de uma amostra rotulada (CSV)
- [ ] Custos de erro diferentes por tipo de erro
- [ ] Simular a melhora da precisão ao longo do tempo

## 🔗 Série de calculadoras de IA
[Custo por tarefa de agentes](https://moniquesilva79.github.io/custo-agentes-ia/) · [Precificação do FTE digital](https://moniquesilva79.github.io/precificacao-fte-digital/) · [ROI e payback](https://moniquesilva79.github.io/roi-automacao-ia/) · [Priorização de processos](https://moniquesilva79.github.io/priorizacao-processos/) · [Revisão humana x custo do erro](https://moniquesilva79.github.io/revisao-humana-ia/) · [Curva de melhoria contínua](https://moniquesilva79.github.io/curva-melhoria-ia/)

---
Projeto autoral de **Monique da Silva Cruz**: [LinkedIn](https://www.linkedin.com/in/moniquesilva-cloud-ti-projetos-latam) · [outros projetos](https://github.com/MoniqueSilva79)
