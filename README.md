# SnowBeePh.github.io
<h3>UOC - Visualización de Datos - Box Plot con R</h3>

<p>Esta práctica ha sido desarrollada con el lenguaje de programación R</p>

<p>Se ha utilizado un fichero de datos formateado proveniente de <b></b><a href="https://www.gapminder.org/data/">https://www.gapminder.org/data/</a></b>, específicamente el encontrado en <b>Health > Life expectancy, male</b> </p>
<p>El fichero <b>life_expectancy_male_formatted.csv</b> se encuentra disponible en este mismo repositorio</p>

<p>El fichero original contenía información de la expectativa de vida masculina en años por país desde 1950 hasta 2100 organizado por páis. <br>
  Igualmente presente en este mismo repositorio bajo el nombre de <b>life_expectancy_male.csv</b>
</p>

<p>El fichero fue formateado en los siguientes aspectos:</p>
<ul>
  <li>Solo se mantuvieron los datos del 2023, con el nombre de la columna <b>years</b></li>
  <li>Se agregó la columna <b>continent</b> para indicar a que continente pertenece cada país</li>
</ul>

<p>Estos cambios fueron realizados para tener una visión más amplia comparando regiones a nivel mundial, permitiendo encontrar fácilmente <i>outliers</i> entre las mismas</p>

<p>El código con el que se realizó es el siguiente:</p>

```
# Librerías requeridas
library(tidyverse)

# Creamos el box plot con los datos recuperados del CSV definiendo las axis
# y las leyendas del mismo para una visualización cómoda
ggplot(data = world_data) +
  geom_boxplot(aes(x = continent, y = years, color = continent)) +
  labs(title = "Expectativa de Vida por Continente [Hombre]",
       subtitle = "Año 2023",
       y = "Edad",
       x = "Continente",
       color = "Continente",
       caption = "Fuente: www.gapminder.com")
```
<p>El resultado será el siguiente:</p>

![life_expectancy_male_2023_boxplot](https://github.com/SnowBeePh/SnowBeePh.github.io/assets/39880969/2888e4a0-66f6-4d2a-8adf-2fd7d9033969)


<p>Finalmente, se puede apreciar la visualización, dónde se puede rápidamente observar que existen amplias diferencias entre las regiones</p>
<ul>
  <li>Las medianas no coinciden ninguna entre ellas</li>
  <li>América parece ser el único continente con una distribución alrededor de la mediana equilibrada, mientras que el resto tiene amplias variaciones</li>
  <li>El único continente cuya distribución superior a la mediana no llega a los 70 años es África</li>
  <li>etc.</li>
</ul>

<p>Muchas gracias por su atención.</p>
<small>Autor: Ian P. Carlos Casillas</small>
