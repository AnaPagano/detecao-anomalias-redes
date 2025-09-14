# Detecção de Anomalias em Redes (UNSW-NB15)

Projeto da disciplina TC-CD: EDA, engenharia de atributos e modelos para detecção de tráfego anômalo.

## Dataset
UNSW-NB15 (ACCS). Arquivos usados: `UNSW_NB15_training-set.csv` e `UNSW_NB15_testing-set.csv`.  
• Página oficial: https://research.unsw.edu.au/projects/unsw-nb15-dataset  
**Observação:** Os CSVs **não** estão neste repositório (tamanho/limite GitHub). Baixe-os da fonte oficial.

## Como rodar
1. Crie um ambiente e instale dependências:
   ```bash
   pip install -r requirements.txt
   ```
2. Rode no Google Colab abrindo o notebook:  
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/AnaPagano/detecao-anomalias-redes/blob/main/Detec%C3%A7%C3%A3o_de_Anomalias_em_Redes_de_Computadores_%28UNSW_NB15%29.ipynb)




##  Estrutura do projeto
```
detecao-anomalias-redes/
├── Figuras/                  
├── .gitignore
├── LICENSE
├── NOTEBOOK-FINAL.ipynb      
├── README.md
├── requirements.txt          
```

##  Resultados

Foram testados três modelos principais para detecção de tráfego anômalo no dataset **UNSW-NB15**, além de uma versão balanceada do Random Forest com **SMOTE**:

- **Random Forest (supervisionado):**
  - Acurácia = 1.00
  - Precisão = 1.00
  - Recall = 1.00
  - F1-Score = 1.00
  - ROC-AUC = 1.00
  - Melhor desempenho entre todos os modelos.

- **Random Forest + SMOTE:**
  - Resultados idênticos ao RF puro (1.00 em todas as métricas).
  - Útil para cenários de classes desbalanceadas.

- **Isolation Forest (não supervisionado):**
  - Acurácia = 0.54
  - ROC-AUC ≈ 0.20
  - Precisão (ataque) = 0.90
  - Recall (ataque) = 0.32
  - F1-Score (ataque) = 0.47
  - Alto número de falsos positivos.

- **One-Class SVM (não supervisionado):**
  - Acurácia = 0.62
  - Precisão (ataque) = 0.94
  - Recall (ataque) = 0.44
  - F1-Score (ataque) = 0.60
  - Desempenho intermediário, mas inferior ao Random Forest.

###  Comparação Resumida

| Modelo              | Acurácia | ROC-AUC | Precisão (Ataque) | Recall (Ataque) | F1 (Ataque) |
|---------------------|----------|---------|-------------------|-----------------|-------------|
| Random Forest       | 1.00     | 1.00    | 1.00              | 1.00            | 1.00        |
| RF + SMOTE          | 1.00     | 1.00    | 1.00              | 1.00            | 1.00        |
| Isolation Forest    | 0.54     | 0.20    | 0.90              | 0.32            | 0.47        |
| One-Class SVM       | 0.62     | –       | 0.94              | 0.44            | 0.60        |

**Conclusão:** O modelo **Random Forest supervisionado** teve desempenho perfeito neste dataset, superando em muito os métodos não supervisionados (IF e OCSVM).


##  Conclusões

- Algoritmos **supervisionados (com rótulos)** tiveram desempenho muito superior aos **não supervisionados**.  
- A análise exploratória (EDA) mostrou que atributos como **bytes, pacotes e duração** são determinantes para diferenciar tráfego normal de ataque.  
- A **engenharia de atributos** (bytes_total, ratio, pkts_total, log_dur) ajudou a capturar padrões importantes e melhorar a separação entre classes.  
- O Random Forest se destacou como o melhor modelo, alcançando **100% em todas as métricas**.  
- Aplicação prática: sistemas de **detecção de intrusão** em redes e cenários de **IoT**, onde a identificação rápida e precisa de ataques é essencial.  


## 👩‍💻 Autores
Ana Pagano
