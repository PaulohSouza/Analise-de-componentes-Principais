# Analise-de-componentes-Principais
Projetos relacionados a algoritmos de análise de componentes principais

# Declaração de Bibliotecas
library(pacman)
library(factoextra)
library(ggplot2)

# Seleciona os dados que quer analisar
Dados <- read.csv(file.choose())

dados <- data.frame(Dados)
# Remover a coluna Tratamento
col1 <- lapply(dados[-1], unlist)

# Remover a coluna de bloco
col2 <- lapply(col1[-1], unlist) 

# Gerar data Frame com variáveis restantes
dadospca <- data.frame(col2)      

  # Cria a distribuição dos componentes
  res.pca <- prcomp(dadoscorrel, scale = TRUE)
  fviz_eig(res.pca)
  
  # Define os parâmetros e plota o gráfico
  pca <- fviz_pca_var(res.pca,
                      col.var = "contrib", 
                      gradient.cols = c("#00AFBB", "#E7B800", "#FC4E07"),
                      repel = TRUE, 
                      title = "Análise dos componentes principais - PCA") 
  plot(pca)
