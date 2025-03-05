# Curso-RNa-seq


## Pasos para hacer un alánisis de RNAseq

## Ejercicio graficos ggplot

Cargar los programas de ggplot

```{r programas, include=FALSE}
library(ggplot2)
library(pheatmap)
library(ggrepel)
data(iris)  # Cargamos la base de datos iris
head(iris)  # Vista previa de los datos
```

## Gráfico de dispersión 

Para sacar un gráfico de dispersión usar el siguiente comando

```{r, dispersion}
ggplot(iris, aes(x = Sepal.Length, y = Sepal.Width, color = Species)) +
  geom_point(size = 3) +
  theme_minimal() +
  labs(title = "Gráfico de Dispersión de Sepal.Length vs Sepal.Width",
       x = "Longitud del Sépalo",
       y = "Ancho del Sépalo")
```

# Grafico Histograma 
```{r, histograma}
ggplot(iris, aes(x = Sepal.Length, fill = Species)) +
  geom_histogram(binwidth = 0.3, alpha = 0.7, position = "identity") +
  theme_minimal() +
  labs(title = "Distribución de la Longitud del Sépalo",
       x = "Longitud del Sépalo",
       y = "Frecuencia")
```

## Grafico Boxplot
```{r, boxplot}
ggplot(iris, aes(x = Species, y = Sepal.Length, fill = Species)) +
  geom_boxplot() +
  theme_minimal() +
  labs(title = "Distribución de Sepal.Length por Especie",
       x = "Especie",
       y = "Longitud del Sépalo")
