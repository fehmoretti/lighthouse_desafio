# Guia de Instalação e Execução do Projeto

## **Descrição do Projeto**
Este projeto tem como objetivo desenvolver um modelo preditivo para prever o preço de aluguéis temporários em Nova York com base em um conjunto de dados de um concorrente. O projeto inclui:

- Análise Exploratória de Dados (EDA);
- Desenvolvimento de um modelo de Machine Learning para previsão de preços;
- Exportação do modelo em formato `.pkl`;
- Respostas às questões de negócio propostas.

---

## **Repositório**
Este projeto está disponível no GitHub no repositório **lighthouse_desafio**. Para acessá-lo, utilize o seguinte link:

[https://github.com/fehmoretti/lighthouse_desafio](https://github.com/fehmoretti/lighthouse_desafio)

---

## **Requisitos**
Antes de executar o projeto, certifique-se de que você possui os seguintes itens instalados:

1. **Python 3.9 ou superior**
2. **Bibliotecas Python** (especificadas no arquivo `requirements.txt`)

---

## **Instruções de Instalação**

1. **Clone o repositório**:
   ```bash
   git clone https://github.com/fehmoretti/lighthouse_desafio.git
   cd lighthouse_desafio
   ```

2. **Crie um ambiente virtual (opcional, mas recomendado)**:
   ```bash
   python -m venv venv
   source venv/bin/activate  # No Windows: venv\Scripts\activate
   ```

3. **Instale as dependências**:
   ```bash
   pip install -r requirements.txt
   ```

---

## **Instruções de Execução**

1. **Execute o Notebook Jupyter**:
   
   Abra o Jupyter Notebook e carregue o arquivo principal:
   ```bash
   jupyter notebook
   ```
   Em seguida, selecione o arquivo `analise_modelo_precificacao.ipynb`.

2. **Teste o Modelo Carregado**:
   Certifique-se de que o arquivo do modelo (`modelo_precificacao.pkl`) está na mesma pasta do script.
   Para testar, execute o seguinte comando em Python:
   ```python
   import pickle
   import pandas as pd

   # Carregar o modelo
   with open('modelo_precificacao.pkl', 'rb') as file:
       modelo = pickle.load(file)

   # Criar exemplo de entrada
   novo_apartamento = {
       'latitude': 40.75362,
       'longitude': -73.98377,
       'minimo_noites': 1,
       'numero_de_reviews': 45,
       'reviews_por_mes': 0.38,
       'calculado_host_listings_count': 2,
       'disponibilidade_365': 355,
       'bairro_group': 'Manhattan',
       'bairro': 'Midtown',
       'room_type': 'Entire home/apt'
   }

   novo_apartamento_df = pd.DataFrame([novo_apartamento])

   # Fazer previsão
   preco_previsto = modelo.predict(novo_apartamento_df)
   print("Preço sugerido ($):", round(preco_previsto[0], 2))
   ```

3. **Gerar Novas Previsões**:
   Utilize a mesma estrutura para testar diferentes características de apartamentos e obter previsões.

---

## **Estrutura do Repositório**
- `analise_modelo_precificacao.ipynb`: Notebook principal com a EDA e o desenvolvimento do modelo.
- `modelo_precificacao.pkl`: Modelo treinado e salvo.
- `requirements.txt`: Arquivo com as dependências do projeto.
- `README.md`: Este guia.
- `data/`: Pasta contendo o conjunto de dados utilizado no projeto.

---

## **Dependências Principais**
As principais bibliotecas utilizadas neste projeto são:

- `pandas`
- `numpy`
- `scikit-learn`
- `matplotlib`
- `seaborn`

Para instalar todas as dependências, utilize o comando:
```bash
pip install -r requirements.txt
```

---

## **Notas Importantes**
- Certifique-se de que as colunas de entrada estejam alinhadas com o modelo treinado.
- Para alterações ou novos treinamentos, ajuste o Notebook principal e reexporte o modelo.

---

## **Suporte**
Caso encontre problemas ou tenha dúvidas, entre em contato pelo repositório ou envie um e-mail para [felipe_moretti_sk8@hotmail.com].

