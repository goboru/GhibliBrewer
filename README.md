# GhibliBrewer
Transform your R plots with palettes inspired by the beautiful visuals of Studio Ghibli movies!

This package was based on coding from the [MetBrewer](https://github.com/BlakeRMills/MetBrewer) package. 
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
palette <- glibli.brewer("Howl-Castle")
palette <- glibli.brewer(palette="Totoro-Mouth", direction="default", type="discrete", n=5)
```
* palette: String, name of the palette
* direction: "default", "reverse" or "random". "default" if not specified.
* type: "discrete" or "continuous". "discrete" if not specified. 
* n: Number of colors, up to the maximum of colors predefined in the palette. Maximun size of the palette by default.


**Display an individual palette:**
```
# Run the glibli.brewer() function without assigning the output to a variable
glibli.brewer(palette="Totoro-Mouth", direction="default", type="discrete", n=5)
```

**Display all palettes:**
```
# All palettes as set by default
display.ghibli()
```
![All](https://github.com/goboru/GhibliBrewer/assets/102520815/f1b88ae4-4384-4168-b3cb-e91d49c3426e)

```
# Display all palettes with a specific number of colors with "n"
display.ghibli(n=4)

# Change the direction of the palettes with "direction"
display.ghibli(direction="random")
```
### Integration with ggplot2
**Add discrete palette to ggplot:**
```
plot.colorblind.ghib("Totoro-Mouth")
```
**Add continuous palette to ggplot:**
```
plot.colorblind.ghib("Totoro-Mouth")
```



# Colorblind-friendly palette assistance
We carefully created and tested colorblind-friendly palettes in our package. In addition, we also added the option for the user to study themself which colors in a palette are more problematic in regard to colorblind-friendliness. It is important to note that while some palettes aren't labeled as "colorblind-friendly," removing one or two colors can help achieve that. Our function to visualize palettes and check if they are clolorblind-friendly also work with any palette defined by the user.

**Display all colorblind-friendly palettes:**
```
display.ghibli(colorblind_only = T)
```
![all-cb](https://github.com/goboru/GhibliBrewer/assets/102520815/0d2515cc-c2e5-4087-bbe9-88142d73c390)

**Simulate a GhibliBrewer palette in the way that a person with protanopia, deuteranopia, or tritanopia would see them, respectively:**
```
plot.colorblind.ghib("Totoro-Mouth")
```

**Simulate any palette in the way that a person with protanopia, deuteranopia, or tritanopia would see them, respectively:**
```
palette <- c('red', 'green', 'orange', 'black')
plot.colorblind.palette(palette)
```

### Editing a palette considering colorblindness
A good example of a palette that is close to being colorblind-friendly is "Howl-Peace". We can visualize this palette using plot.colorblind.ghib()
```
plot.colorblind.ghib("Howl-Peace")
```
![colorblind-example](https://github.com/goboru/GhibliBrewer/assets/102520815/bbb47b34-cc6a-4f1d-a491-dfd6a1ad098e)


You can notice that the most problematic combination in this palette is between colors 2-7(tritanopia) and 4-7(deuteranopia and protanopia). We can remove one of them (#7), and, even if intuitively this palette does not appear colorblind-friendly, you can see that there is no highly-problematic combination now:
```
palette <- ghibli.brewer("Howl-Peace")[c(1,2,3,4,5,6)]
plot.colorblind.palette(palette)
```
![colorblind-fixed](https://github.com/goboru/GhibliBrewer/assets/102520815/918960eb-77b4-41b9-9e28-f8b33e37775a)


# GhibliBrewer palettes

## All palettes
![All](https://github.com/goboru/GhibliBrewer/assets/102520815/f1b88ae4-4384-4168-b3cb-e91d49c3426e)


## Nausicaä of the Valley of the Wind (1984)
### Nausicaa-Pilot
![NausicaaPilot](https://github.com/goboru/GhibliBrewer/assets/112853494/22db4d78-64d7-4e31-833d-28c16c7d2db8)

### Nausicaa-Bug
![NausicaaBug](https://github.com/goboru/GhibliBrewer/assets/112853494/69a2fb59-98b1-499b-a45d-04daf53f8ca6)

## Castle in the Sky (1986)
### Sky-Grass
![SkyGrass](https://github.com/goboru/GhibliBrewer/assets/112853494/cf0ba293-5ee9-4411-9bf9-b640f34f031e)

### Sky-Necklace
![SkyNecklace](https://github.com/goboru/GhibliBrewer/assets/112853494/cca12921-55c8-4578-90b9-31e8daf25ab8)

## My neighbour Totoro (1988)
### Totoro-Umbrella
![TotoroUmbrella](https://github.com/goboru/GhibliBrewer/assets/112853494/028a098c-873b-4926-8f7d-b06fc3be4d4a)

### Totoro-Mouth
![TotoroMouth](https://github.com/goboru/GhibliBrewer/assets/112853494/626825a1-c18c-4000-a5db-bfa43cc7d7b2)

### Totoro-Catbus
![TotoroCatbus](https://github.com/goboru/GhibliBrewer/assets/112853494/94e7694e-0188-4eeb-bfe3-2d4ff5480e78)

### Totoro-House
![TotoroHouse](https://github.com/goboru/GhibliBrewer/assets/112853494/efff1010-bc1c-4492-b8d1-b0260bd6eb42)

### Totoro-School
![TotoroSchool](https://github.com/goboru/GhibliBrewer/assets/112853494/a044460a-9734-4b4f-9711-1d135bd80f1c)


## Only Yesterday (1991)
### Yesterday-Park


## Porco Rosso (1992) 
### Porco-Plane
![PorcoPlane](https://github.com/goboru/GhibliBrewer/assets/112853494/08b3a149-6bde-478d-8805-4816a6399c8c)

### Porco-Cave
![PorcoCave](https://github.com/goboru/GhibliBrewer/assets/112853494/87770448-1af9-44fc-9b80-bebfe1f907c0)

## Pom Poko (1994)
### Pompoko-Fortune
![PompokoFortune](https://github.com/goboru/GhibliBrewer/assets/112853494/78035a23-8780-4e00-895d-7f79acee745b)

## On Your Mark (1995)
### Mark-Car


## Princess Mononoke (1997)
### Mononoke-Hug
![MononokeHug](https://github.com/goboru/GhibliBrewer/assets/112853494/2107e48e-08c1-4108-8a6d-862835aeaf38)

### Mononoke-Knife
![MononokeKnife](https://github.com/goboru/GhibliBrewer/assets/112853494/a2c9deea-76b8-4dd9-b52f-dff4d87b59ce)

### Mononoke-Guardian
![MononokeGuardian](https://github.com/goboru/GhibliBrewer/assets/112853494/0803c938-bc6f-4400-87f7-2a88f127687d)

## My Neighbors the Yamadas (1999)
### Yamadas


## Spirited away (2001)
### Chihiro-Dragon
![ChihiroDragon](https://github.com/goboru/GhibliBrewer/assets/112853494/964049ee-721f-4245-92e8-d6d20b355735)

### Chihiro-Lump
![ChihiroLump](https://github.com/goboru/GhibliBrewer/assets/112853494/a735956c-294b-4ba5-a2ed-96b242e8febb)

### Chihiro-Bridge
![ChihiroBridge](https://github.com/goboru/GhibliBrewer/assets/112853494/15160bac-684c-4a1f-8bd5-fb559f5fc7c6)

### Chihiro-NoFace
![ChihiroNoFace](https://github.com/goboru/GhibliBrewer/assets/112853494/e86a98b2-5cf2-4a38-be5c-b863f5aefea7)


## The Cat Returns (2002)
### Cat-Vals

### Cat-Prince

### Cat-Broom

### Cat-Bubble


## Howl's Moving Castle (2004)
### Howl-Horizon
![HowlHorizon](https://github.com/goboru/GhibliBrewer/assets/112853494/91b0935e-7d18-45b6-a935-8b58823858a3)

### Howl-Peace
![HowlPeace](https://github.com/goboru/GhibliBrewer/assets/112853494/a5fd7dd5-475f-419d-b561-09a2d230a9c3)

### Howl-Terrace
![HowlTerrace](https://github.com/goboru/GhibliBrewer/assets/112853494/4041375a-cba9-4190-b91d-c15072e2143e)

### Howl-FireDemon
![HowlFiredemon](https://github.com/goboru/GhibliBrewer/assets/112853494/824ae0e6-ea20-4e8b-8ad8-7555ee69586f)

### Howl-Star
![HowlStar](https://github.com/goboru/GhibliBrewer/assets/112853494/db56cb0e-0238-429c-85b8-d2e5cc7f77ab)

### Howl-Breakfast

### Howl-Castle


## Tales from Earthsea (2006)
### Earthsea-Silk

### Earthsea-Lightning


## Arrietty (2010)
### Arrietty-Garden

### Arrietty-Bedroom


## Ponyo (2008)
### Ponyo-Joy
![PonyoJoy](https://github.com/goboru/GhibliBrewer/assets/112853494/40ecee86-d356-4dc8-93b6-497b401a7c55)

### Ponyo-Ramen
![PonyoRamen](https://github.com/goboru/GhibliBrewer/assets/112853494/c2f9790e-7798-4370-9317-25b3ed9f1de7)

### Ponyo-Boat
![PonyoBoat](https://github.com/goboru/GhibliBrewer/assets/112853494/fda7a05c-9463-4cfb-bfbf-c4652acbdc03)


## The Wind Rises (2013)
### Wind-Timer
![WindTimer](https://github.com/goboru/GhibliBrewer/assets/112853494/b9aee7d2-c52a-45d5-8639-82cce4606b61)

### Wind-Kiss

## When Marnie Was There (2014)
### Marnie-Bedroom

### Marnie-Train


## The Boy and the Heron (2023)
### Heron-Troop

### Heron-Jelly

### Heron-Parrots
![HeronParrots](https://github.com/goboru/GhibliBrewer/assets/112853494/2841fbf8-f3db-4aba-a9bd-681bf07c34f1)

### Heron-Hug
![HeronHug](https://github.com/goboru/GhibliBrewer/assets/112853494/87d5d920-f9a2-4377-87b0-8d012235904c)




*If you have come this far, why don't you try your expertise with game.ghib() ?*
