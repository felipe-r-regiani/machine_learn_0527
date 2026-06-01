# machine_learn_0527

Este repositório é dedicado à implementação "from scratch" do algoritmo **K-means**, um dos mais populares métodos de aprendizado não supervisionado para agrupamento (clustering) de dados. O projeto aplica o K-means para **segmentação de clientes** com base em frequência de compras e ticket médio, demonstrando todo o fluxo desde a inicialização dos centróides até a visualização dos clusters.

## 📂 Conteúdo

- **k-means.ipynb**: Notebook completo contendo a implementação do K-means e sua aplicação em segmentação de mercado. O projeto abrange:

  - **Carregamento dos Dados**: Leitura do dataset CSV utilizando `np.genfromtxt`, ignorando o cabeçalho.
  
  - **Distância Euclidiana** (`euclidean_distance`): Função que calcula a distância entre um ponto e todos os centróides utilizando `np.sqrt` e `np.sum`, vetorizada para eficiência.
  
  - **Algoritmo K-means** (`kmeans`): Implementação completa incluindo:
    - **Inicialização**: Seleção aleatória de K pontos do dataset como centróides iniciais (`np.random.choice`).
    - **Associação**: Para cada ponto, cálculo da distância até todos os centróides e atribuição ao cluster mais próximo (`np.argmin`).
    - **Atualização**: Recálculo de cada centróide como a média dos pontos do cluster (`np.mean`).
    - **Critério de Parada**: Convergência quando os centróides não se alteram significativamente (`np.allclose`), evitando iterações desnecessárias.
    - **Parâmetros**: `k` (número de clusters), `max_iter` (número máximo de iterações).
  
  - **Visualização dos Resultados**: Plotagem 2D utilizando Matplotlib com:
    - Pontos coloridos por cluster com alpha para visualização de densidade.
    - Centróides destacados em preto com marcador "X" de tamanho ampliado.
    - Grade, rótulos nos eixos (Frequência de Compras, Ticket Médio) e legenda.
    - Título "Segmentação de Clientes com K-Means".

- **dataset_clientes_kmeans.csv**: Dataset real de clientes com 240 registros e 2 features:
  - `frequencia_compras`: Número de compras por mês.
  - `ticket_medio`: Valor médio gasto por compra (R$).
  - Dados ideais para visualização 2D dos clusters formados.

## 🛠️ Tecnologias e Bibliotecas

As ferramentas centrais utilizadas neste projeto são:

- **Python 3**: Linguagem base.
- **NumPy**: Operações vetoriais e matriciais para cálculo eficiente de distâncias Euclidianas, médias dos clusters e seleção aleatória de centróides.
- **Matplotlib**: Geração do gráfico de dispersão 2D com clusters coloridos e centróides destacados.
- **CSV**: Leitura do dataset de clientes.
- **Jupyter Notebook**: Ambiente interativo para execução, visualização e documentação.

## 🚀 Como começar

1. Clone este repositório:
   ```bash
   git clone https://github.com/felipe-r-regiani/machine_learn_0527.git
   ```

2. Instale as bibliotecas necessárias:
   ```bash
   pip install numpy matplotlib
   ```

3. Execute o notebook:
   - Abra o `k-means.ipynb`.
   - Experimente diferentes valores de `k` (2 a 6) e observe como os clusters se reorganizam.
   - Analise o perfil de cada cluster: clientes de alto ticket vs. baixa frequência, etc.
   - Teste aumentar o `max_iter` e veja quantas iterações são necessárias para convergir.
   - Reexecute o notebook várias vezes — a inicialização aleatória pode gerar agrupamentos diferentes.
