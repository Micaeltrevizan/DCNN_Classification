# Análise de Sentimento com CNN e BERT

Este projeto implementa um modelo de classificação utilizando uma Rede Neural Convolucional (CNN) e representações de palavras BERT para classificar textos em português.

## Resumo da Utilidade

O objetivo principal deste código é treinar um modelo de aprendizado profundo capaz de analisar e classificar a categoria dos textos. Ele utiliza uma combinação de representações de palavras BERT para capturar o contexto semântico e uma CNN para extrair padrões e características relevantes dos textos. O modelo treinado pode ser aplicado para analisar o sentimento de comentários de clientes, avaliações de produtos ou qualquer outro texto em português, fornecendo insights valiosos sobre as opiniões e emoções expressas nos textos.

## Funcionalidades

* **Pré-processamento de Texto:**
    * Limpeza de texto (remoção de URLs, menções, caracteres especiais).
    * Tokenização usando o tokenizer BERT.
    * Codificação de sentenças em IDs de tokens.
* **Construção do Modelo CNN:**
    * Utilização de camadas de embedding para representar palavras como vetores.
    * Aplicação de camadas convolucionais 1D para extrair características de n-gramas.
    * Utilização de camadas de max-pooling global para reduzir a dimensionalidade.
    * Implementação de camadas densas e dropout para classificação.
* **Treinamento e Avaliação:**
    * Treinamento do modelo usando o otimizador Adam e função de perda de entropia cruzada.
    * Implementação de checkpoints para salvar e restaurar o modelo treinado.
    * Plotagem da função de perda ao longo do treinamento.
    * Criação de funções para realizar a predição de novos textos.
* **Análise de Dados Externos:**
    * Aplicação do modelo treinado em um novo dataset para realizar a classificação de sentimento.
    * Geração de gráficos para visualização dos resultados.
    * Exportação dos resultados para um arquivo Excel.

## Pré-requisitos

* Python 3.x
* Bibliotecas Python:
    * numpy
    * pandas
    * tensorflow (versão 2.8.0)
    * tensorflow-hub
    * bert-for-tf2
    * sentencepiece
    * beautifulsoup4
    * matplotlib
    * seaborn
    * scikit-learn
* Acesso ao Google Colab (opcional, para execução do notebook).
* Arquivos de dados CSV (CLMLC140.csv e F9 - Copy.csv).

## Instalação

1.  Clone o repositório (se aplicável).
2.  Instale as dependências usando pip:

    ```bash
    pip install numpy pandas tensorflow==2.8.0 tensorflow-hub bert-for-tf2 sentencepiece beautifulsoup4 matplotlib seaborn scikit-learn
    ```

3.  Certifique-se de que os arquivos de dados CSV estejam disponíveis.

## Uso

1.  Execute o script Python (ou o notebook do Colab).
2.  O script irá:
    * Carregar e pré-processar os dados.
    * Construir e treinar o modelo CNN.
    * Avaliar o desempenho do modelo.
    * Aplicar o modelo treinado em um novo dataset.
    * Gerar gráficos e exportar os resultados.

## Estrutura do Código

* **Carregamento e Limpeza de Dados:**
    * Carrega os dados de arquivos CSV.
    * Limpa o texto usando BeautifulSoup e expressões regulares.
    * Realiza a codificação dos labels.
* **Tokenização e Codificação:**
    * Utiliza o tokenizer BERT para tokenizar as sentenças.
    * Codifica as sentenças em IDs de tokens.
* **Construção do Modelo CNN:**
    * Implementa a classe `DCNN` que define a arquitetura do modelo.
* **Treinamento e Avaliação:**
    * Compila e treina o modelo usando `model.fit()`.
    * Implementa um callback personalizado para salvar checkpoints.
    * Gera gráficos da função de perda.
    * Implementa funções para realizar a predição.
* **Análise de Dados Externos:**
    * Carrega um novo dataset.
    * Aplica o modelo treinado para classificar o sentimento.
    * Gera gráficos e exporta os resultados.
* **Exportação dos dados:**
    * Exporta o resultado da classificação em um arquivo .xlsx.

## Observações

* O modelo foi treinado em um conjunto de dados específico e pode precisar de ajuste fino para outros conjuntos de dados.
* A arquitetura do modelo e os hiperparâmetros podem ser ajustados para melhorar o desempenho.
* A utilização de BERT permite capturar o contexto semântico das palavras, melhorando a precisão da análise de sentimento.
* A CNN é utilizada para extrair padrões e características relevantes dos textos, complementando as representações de palavras BERT.
