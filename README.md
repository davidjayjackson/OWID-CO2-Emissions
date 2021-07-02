# OWID-CO2-Emissions

### Code for Calculating Rate of Change by Country and Year

df <- df %>%
  arrange(Entity, Year) %>%
  group_by(Entity) %>%
  summarise(
    first_year = min(Year),
    last_year = max(Year),
    roc = (last(Emissions) - first(Emissions)) / first(Emissions)
  )
    
