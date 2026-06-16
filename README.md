<h1 align="center">⚽ Portugal vs DR Congo — Previsão para o Mundial 2026</h1>

<p align="center">
  <em>Quem vai ganhar? Os dados respondem.</em><br>
  Modelo Dixon-Coles (Poisson bivariado) sobre o histórico do futebol internacional.
</p>

<p align="center">
  <img alt="Python" src="https://img.shields.io/badge/Python-3.10+-3776AB?logo=python&logoColor=white">
  <img alt="Jupyter" src="https://img.shields.io/badge/Jupyter-Notebook-F37626?logo=jupyter&logoColor=white">
  <img alt="Modelo" src="https://img.shields.io/badge/Modelo-Dixon--Coles-1f9e5a">
</p>

<p align="center">
  <a href="https://rdtg94.github.io/portugal-jogo1-mundial-2026/"><b>🔗 Ver previsão interativa</b></a>
  &nbsp;·&nbsp;
  <a href="./previsao_portugal_congo.ipynb"><b>📓 Notebook completo</b></a>
</p>

---

## 🎯 O veredito

| Resultado | Probabilidade |
|:---|:---:|
| 🇵🇹 **Portugal vence** | **~56%** |
| 🤝 Empate | ~30% |
| 🇨🇩 DR Congo vence | ~14% |

**Resultado mais provável:** Portugal 1–0 · **Golos esperados:** 1.3 – 0.5

---

## 📌 Sobre o projeto

Este projeto estima a probabilidade de cada resultado em **Portugal–DR Congo** (Mundial 2026, fase de grupos, Houston) a partir do histórico completo do futebol internacional.

O modelo não adivinha: aprende a força de ataque e de defesa de cada seleção a partir de milhares de jogos reais e deriva as probabilidades de vitória, empate e derrota de uma distribuição de Poisson sobre os golos esperados. É a mesma família de modelos que sustenta os sistemas de previsão desportiva de referência, como o supercomputador da Opta.

## 🧪 Metodologia

O **Dixon-Coles** é o estado da arte na previsão de resultados de futebol. Em resumo:

- **Golos esperados** de cada equipa modelados como `exp(ataque − defesa)`, com vantagem de casa quando aplicável.
- **Correção de Dixon-Coles (ρ)** para os resultados de poucos golos (0-0, 1-0, 0-1, 1-1), onde a independência de Poisson falha.
- **Decaimento temporal:** jogos recentes pesam mais do que jogos antigos (meia-vida ≈ 1 ano), refletindo a forma atual.
- **Estimação por máxima verosimilhança**, com gradiente analítico para convergência em ~1 segundo.
- **Intervalos de confiança por bootstrap** não-paramétrico, para quantificar a incerteza da previsão.

O jogo é modelado em **campo neutro** (Houston), pelo que a vantagem de casa não é aplicada a nenhuma seleção.

## ✅ Validação

O modelo foi validado fora da amostra, não apenas ajustado aos dados:

| Métrica | Valor | Referência |
|:---|:---:|:---|
| Brier score | **0.498** | 0.667 (palpite aleatório) |
| Acerto 1X2 | **60.6%** | em 1 327 jogos de teste |
| Benchmark Opta | 54.6% | o modelo converge para o mesmo valor |

## 📂 Estrutura do repositório

```
.
├── index.html                       # Página interativa (GitHub Pages)
├── previsao_portugal_congo.ipynb    # Notebook completo: dados, modelo, validação
├── linkedin-card.png                # Imagem de divulgação
└── README.md
```

## 🚀 Como reproduzir

```bash
# 1. Clonar o repositório
git clone https://github.com/rdtg94/portugal-jogo1-mundial-2026.git
cd portugal-jogo1-mundial-2026

# 2. Instalar dependências
pip install pandas numpy scipy matplotlib jupyter

# 3. Abrir o notebook
jupyter notebook previsao_portugal_congo.ipynb
```

Os dados são carregados automaticamente a partir do dataset público [`martj42/international_results`](https://github.com/martj42/international_results) (49 477 jogos de seleções desde 1872). Não é necessário descarregar nada manualmente.

## ⚠️ Limitações

O modelo é rigoroso dentro do seu domínio. As fronteiras desse domínio:

- Usa a **força média histórica** de cada seleção, não a escalação concreta de cada jogo nem lesões.
- A estimativa de **DR Congo** é a mais incerta, por a seleção ter menos histórico competitivo recente.
- As casas de apostas implicam ~Portugal 78% / empate 13% / Congo 9%. A diferença é esperada: o mercado precifica a qualidade individual dos plantéis, que um modelo baseado apenas em resultados de seleção não observa.

A previsão é **probabilística**, não determinística. Trabalho de análise e demonstração metodológica — não constitui aconselhamento de apostas.

## 👤 Autoria

**Ricardo Gonçalves** · Data Scientist · Doutorando em Biotecnologia

[![LinkedIn](https://img.shields.io/badge/LinkedIn-rdtg-0A66C2?logo=linkedin&logoColor=white)](https://linkedin.com/in/rdtg)
[![Instagram](https://img.shields.io/badge/Instagram-rdtg94-E4405F?logo=instagram&logoColor=white)](https://instagram.com/rdtg94)
[![Email](https://img.shields.io/badge/Email-contacto-EA4335?logo=gmail&logoColor=white)](mailto:ricardodtgoncalves@gmail.com)

---

<p align="center"><sub>Modelo Dixon-Coles · dados públicos · Python · feito com rigor e por gosto pelo jogo.</sub></p>
