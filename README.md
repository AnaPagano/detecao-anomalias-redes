# Detecção de Anomalias em Redes (UNSW-NB15)

Projeto da disciplina TC-CD: EDA, engenharia de atributos e modelos para detecção de tráfego anômalo.

## 📂 Dataset
UNSW-NB15 (ACCS). Arquivos usados: `UNSW_NB15_training-set.csv` e `UNSW_NB15_testing-set.csv`.  
• Página oficial: https://research.unsw.edu.au/projects/unsw-nb15-dataset  
**Observação:** Os CSVs **não** estão neste repositório (tamanho/limite GitHub). Baixe-os da fonte oficial.

## ⚙️ Como rodar
1. Crie um ambiente e instale dependências:
   ```bash
   pip install -r requirements.txt
   ```
2. Rode no Google Colab abrindo o notebook:  
   [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/SEU-USUARIO/detecao-anomalias-redes/blob/main/notebook.ipynb)

## 🚀 Estrutura do projeto
```
├── notebook.ipynb        # notebook principal
├── notebook.py           # versão em script Python (opcional)
├── requirements.txt      # dependências
└── figuras/              # imagens geradas
    ├── f1.png ... f16.png
    └── ultima.png
```

## 📊 Resultados (resumo)
- Random Forest → Precisão e Recall > 98%, ROC-AUC ≈ 1.00  
- Isolation Forest → bom recall, mas muitos falsos positivos  
- One-Class SVM → desempenho inferior neste dataset  

## 📝 Conclusões
- Algoritmos supervisionados (Random Forest) tiveram melhor desempenho.  
- Métodos não supervisionados são úteis em cenários sem rótulos, mas menos eficazes aqui.  
- Futuro: aplicar balanceamento de classes e testar deep learning.

## 👩‍💻 Autores
Adriana Pagano e equipe
