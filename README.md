# GhibliBrewer
Palettes from images in Studio Ghibli. 

The package was based on coding from the [MetBrewer](https://github.com/BlakeRMills/MetBrewer) package. 
All original images belong to Studio Ghibli (CC-licensed), and can be accessed through their [website](https://www.ghibli.jp/works/).

This package was equally developed by Gonzalo Borrego-Yaniz and Javier Martínez-López. For requests, questions and comments, feel free to reach out to us!
* Twitter: [Javi](https://twitter.com/javiml221098)   [Gonzalo](https://twitter.com/gonzaloyaniz)

# Instalation
GhibliBrewer is a R package that can be installed via github.

```
install.packages("devtools")

devtools::install_github("goboru/GhibliBrewer")
```

# Usage
**Create a palette:**
```
palette <- glibli.brewer(palette="Totoro-Mouth", direction="default", type="discrete", n=5)
```
* palette: String, name of the palette
* direction: "default", "reverse" or "random"
* type: "discrete" or "continous"
* n: Number of colors, up to the maximum of the palette


**Display an individual palette:**
```
# Run the glibli.brewer() function without setting the output to a variable
glibli.brewer(palette="Totoro-Mouth", direction="default", type="discrete", n=5)
```

**Display all palettes:**
```
# All palettes as default
display.ghibli()

# Set all palettes for n colours with n
display.ghibli(n=4)

# Change the direction of the palettes with direction
display.ghibli(direction="random")
```

**Display all colorblind-friendly palettes:**
```
display.ghibli(colorblind=T)
```

**Simulate palette view in the way that a person with protanopia, deuteranopia, or tritanopia would see them, respectively:**
```
plot.colorblind.ghib("Totoro-Mouth")
```

### Integration with ggplot2
**Add discrete palette to ggplot:**
```
plot.colorblind.ghib("Totoro-Mouth)
```
**Add continuous palette to ggplot:**
```
plot.colorblind.ghib("Totoro-Mouth)
```

# Palettes

## All palettes


## Nausicaä of the Valley of the Wind (1984)
### Nausicaa-Pilot
### Nausicaa-Bug


## Castle in the Sky (1986)
### Sky-Grass
### Sky-Necklace


## My neighbour Totoro (1988)
### Totoro-Umbrella
### Totoro-Mouth
### Totoro-Catbus
### Totoro-House
### Totoro-School


## Only Yesterday (1991)
### Yesterday-Park


## Porco Rosso (1992) 
### Porco-Plane
### Porco-Cave


## Pom Poko (1994)
### Pompoko-Fortune


## On Your Mark (1995)
### Mark-Car


## Princess Mononoke (1997)
### Mononoke-Hug
### Mononoke-Knife
### Mononoke-Guardian


## My Neighbors the Yamadas (1999)
### Yamada


## Spirited away (2001)
### Chihiro-Dragon
### Chihiro-Lump
### Chihiro-Bridge
### Chihiro-NoFace


## The Cat Returns (2002)
### Cat-Vals
### Cat-Prince
### Cat-Broom


## Howl's Moving Castle (2004)
### Howl-Horizon
### Howl-Peace
### Howl-Terrace
### Howl-FireDemon
### Howl-Star
### Howl-Breakfast
### Howl-Castle


## Tales from Earthsea (2006)
### Earthsea-Silk
### Earthsea-Lightning


## Arrietty (2010)
### Arrietty-Garden
### Arrietty-Bedroom


## Ponyo (2008)
### Ponyo-Lantern
### Ponyo-Joy
### Ponyo-Ramen
### Ponyo-Boat


## The Wind Rises (2013)
### Wind-Timer


## When Marnie Was There (2014)
### Marnie-Bedroom
### Marnie-Train


## The Boy and the Heron (2023)
### Heron-Troop
### Heron-Jelly
### Heron-Parrots
### Heron-Hug
