# Notes

## Stuktur

-   Aufgaben- und Problemstellung (Thesen sowie Einordnung als Regressions- und/oder Klassifikationsproblem)
-   Beschreibung der Datenquelle
-   Untersuchung der Daten (z.B. auf NA, Ausreißer) und falls erforderlich Aufbereitung der Daten
-   Untersuchung von mind. 2 Thesen mit Methoden der EDA (d.h. Visualisierung, Transformation)
-   Anwendung mind. einer Machine-Learning Methode und Beurteilung
-   Kritische Bewertung/ Ideen fur weitere Analysen

## Daten aufbereiten

-   Person.ID, Occupation entfernen
-   Sleep Disorder zu true and false
-   Geschecht und BMI Categorie zu numerischen Werten
-   Correlation usw. Berechnen

## Schlaf und Körtper

``` r
final_sleep_data %>%
  select(Quality.of.Sleep, Physical.Activity.Level.Percent, Daily.Steps.Percent, Stress.Level) %>%
  pivot_longer(
    cols = c(Physical.Activity.Level.Percent, Daily.Steps.Percent),
    names_to = "Variable",
    values_to = "Value"
  ) %>%
  ggplot(
    mapping = aes(x = Value, y = Quality.of.Sleep, shape = Variable)
  ) +
  geom_smooth() +
  geom_count(mapping = aes(color = Stress.Level)) +
  labs(
    title = "Körperliche Aktivität und Schlafqualität",
    x = "Relative Aktivität in Prozent", 
    y = "Schlafqualität",
    color = "Stress Level",
    shape = "Aktivitäts Type"
  )
```

Subjektive Daten
text unter summary
konfusionsmatrix
subjective daten
machine learning problem schreien
