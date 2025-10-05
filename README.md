# Análise de Pareto Dinâmica com UDFs no Power BI

Este repositório contém os recursos necessários para criar uma análise de Pareto dinâmica e reutilizável no Power BI utilizando **User-Defined Functions (UDFs)**. O objetivo é permitir a análise de múltiplas medidas (como Vendas, Quantidade, Custo, etc.) em um único visual, sem a necessidade de duplicar código.

## 🚀 Conteúdo

-   **/tmdl:** Contém o arquivo TMDL com as definições das funções de Pareto.
-   **/pbix:** Inclui o arquivo Power BI (`.pbix`) de exemplo com a solução já implementada.

## 🛠️ Como Utilizar

Siga os passos abaixo para implementar esta solução em seu próprio projeto:

1.  **Baixe as UDFs:** Faça o download do arquivo TMDL da pasta `/tmdl` deste repositório.
2.  **Crie um Campo de Parâmetros:** No seu modelo do Power BI, crie um [campo de parâmetros](https://learn.microsoft.com/pt-br/power-bi/transform-model/desktop-what-if) que inclua todas as medidas que você deseja analisar no gráfico de Pareto.
3.  **Crie as Medidas de Cálculo:** Crie as seguintes medidas DAX em seu modelo. Você pode copiar as fórmulas do arquivo `.pbix` de exemplo:
    * `Indicador`: Medida que exibe o valor selecionado no parâmetro.
    * `Ranking`: Classifica a dimensão com base na medida `Indicador`.
    * `Acumulado`: Calcula o valor acumulado da medida.
    * `Percentual`: Calcula o percentual acumulado para formar a linha de Pareto.
4.  **Configure o Gráfico:**
    * Adicione um visual de **"Gráfico de colunas clusterizadas e de linhas"** ao seu relatório.
    * **Eixo X:** Adicione a coluna de dimensão que você deseja analisar (ex: `Produto[Nome]`).
    * **Eixo Y (colunas):** Adicione a medida `Indicador`.
    * **Eixo Y (linha):** Adicione a medida `Percentual`.

Agora você tem um gráfico de Pareto que pode ser alternado entre diferentes métricas usando o campo de parâmetros!

## 💡 Vantagens das UDFs

-   **Reutilização de Código:** Evita a criação de múltiplas medidas de ranking e acumulado para cada métrica base.
-   **Manutenção Simplificada:** Qualquer alteração na lógica precisa ser feita em apenas um lugar.
-   **Performance Otimizada:** Centraliza os cálculos e melhora a eficiência do modelo semântico.
---
_Desenvolvido por fsanfo_