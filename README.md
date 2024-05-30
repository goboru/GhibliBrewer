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
ggplot(diamonds, aes(x = cut, fill=cut)) +
  geom_bar()+
  scale_fill_ghib_d("Howl-FireDemon", n=5)
```
![ggplot-discrete](https://github.com/goboru/GhibliBrewer/assets/102520815/a2afdaf6-90f8-4179-b77b-f9a5655f5c39)

**Add continuous palette to ggplot:**
```
ggplot(diamonds, aes(x = price, y = depth, color=depth)) +
  geom_point() +
  scale_color_ghib_c("Mononoke-Guardian")
```
![ggplot-continuous](https://github.com/goboru/GhibliBrewer/assets/102520815/ee01b38e-f70b-4850-9133-9d209c2c4ea0)
```
ggplot(diamonds, aes(x = log(price), y = carat)) +
  geom_hex() +
  scale_fill_ghib_c("Heron-Jelly")
```
![ggplot-continuous2](https://github.com/goboru/GhibliBrewer/assets/102520815/e9c7d3e2-ffcd-4063-b3bb-53c90f009f8b)



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
![colorblind-example](https://github.com/goboru/GhibliBrewer/assets/102520815/e19e4415-00b8-4e08-b907-0734e8c92592)

You can notice that the most problematic combination in this palette is between colors 4-7(deuteranopia and protanopia) and 2-7(tritanopia). We can remove one of them (#7), and you can see that there is no highly-problematic combination now:
```
palette <- ghibli.brewer("Howl-Peace")[c(1,2,3,4,5,6)]
plot.colorblind.palette(palette)
```
![colorblind-improved](https://github.com/goboru/GhibliBrewer/assets/102520815/08790427-01a5-4c81-a078-3a78cf8ad580)


# GhibliBrewer palettes

## All palettes
![All](https://github.com/goboru/GhibliBrewer/assets/102520815/f1b88ae4-4384-4168-b3cb-e91d49c3426e)


## Nausicaä of the Valley of the Wind (1984)
### Nausicaa-Pilot
![NP](https://github.com/goboru/GhibliBrewer/assets/112853494/a29ddd67-854d-4866-af67-1fe3e11d9c04)

### Nausicaa-Bug
![NB](https://github.com/goboru/GhibliBrewer/assets/112853494/418aaf70-df7e-4850-8cd0-160d290b2794)

## Castle in the Sky (1986)
### Sky-Necklace
![SN](https://github.com/goboru/GhibliBrewer/assets/112853494/a3a017be-bf89-485f-9ac4-641e524729fc)

### Sky-Grass
![SG](https://github.com/goboru/GhibliBrewer/assets/112853494/a220124c-4cd4-4f37-a2c4-0bb5e326e86f)

### Sky-Pirate
![SP](https://github.com/goboru/GhibliBrewer/assets/112853494/8666942a-532f-4d24-92f3-d4f39de704ad)

## My neighbour Totoro (1988)
### Totoro-Mouth
![TM](https://github.com/goboru/GhibliBrewer/assets/112853494/e2582db2-38ca-4e5e-9640-857a1d62986a)

### Totoro-Catbus
![TC](https://github.com/goboru/GhibliBrewer/assets/112853494/b823c8ae-b9a1-4606-85c8-654f71c6fd85)

### Totoro-House
![TH](https://github.com/goboru/GhibliBrewer/assets/112853494/dfac130b-2b71-46e2-bc0d-b94da20019b7)

### Totoro-School
![TS](https://github.com/goboru/GhibliBrewer/assets/112853494/726daae3-b6c4-40ba-8eb8-0bca01a953cc)

### Totoro-Umbrella
![TU](https://github.com/goboru/GhibliBrewer/assets/112853494/949517a8-1a54-4082-ba65-794717655caf)

## Kiki's Delivery Service (1989)
### Kiki-Beach
![KB](https://github.com/goboru/GhibliBrewer/assets/102520815/481c5516-1525-4ebe-b728-0f2ad87623f8)


## Only Yesterday (1991)
### Yesterday-Park
![YP](https://github.com/goboru/GhibliBrewer/assets/112853494/8ef2f0c2-b4d9-43b6-89fe-4203eab2f536)

## Porco Rosso (1992) 
### Porco-Plane
![PP](https://github.com/goboru/GhibliBrewer/assets/112853494/7702c571-e57a-4717-b28b-15d5cba09d6d)

### Porco-Cave
![PC](https://github.com/goboru/GhibliBrewer/assets/112853494/2371e6fd-0165-4d01-8ac7-379fe0a089e5)

### Porco-Garden
![PG](https://github.com/goboru/GhibliBrewer/assets/112853494/665d991c-77e1-416c-84a5-7a2d7e805700)

## Pom Poko (1994)
### Pompoko-Fortune
![PF](https://github.com/goboru/GhibliBrewer/assets/112853494/710119e7-65a3-4327-9eb6-db56b707b4a3)

## On Your Mark (1995)
### Mark-Car
![MC](https://github.com/goboru/GhibliBrewer/assets/112853494/e39c5c64-2b9d-4c0c-8605-6323013285b9)

## Whisper of the Heart (1995)
### Whisper-Roads
![WR](https://github.com/goboru/GhibliBrewer/assets/102520815/d37e2f10-6d3f-467e-bbad-926c4d501523)

###Whisper-Rock
![WK](https://github.com/goboru/GhibliBrewer/assets/102520815/a2f08bbf-53e6-419a-9a1d-f4d3bdb9468a)

## Princess Mononoke (1997)
### Mononoke-Hug
![MH](https://github.com/goboru/GhibliBrewer/assets/112853494/f9b2f111-8028-4fc4-9404-d57eb215f3f6)

### Mononoke-Knife
![MK](https://github.com/goboru/GhibliBrewer/assets/112853494/5f7da96f-cc00-4118-a6f5-4772276a0680)

### Mononoke-Guardian
![MG](https://github.com/goboru/GhibliBrewer/assets/112853494/04ab1af7-6dd8-4b28-b68b-acf3e40f570e)

## My Neighbors the Yamadas (1999)
### Yamadas
![Y](https://github.com/goboru/GhibliBrewer/assets/112853494/7de5e9cd-7fcf-45e8-b20e-8ab77b665a3a)

## Spirited away (2001)
### Chihiro-Dragon
![CD](https://github.com/goboru/GhibliBrewer/assets/112853494/f1c92de4-c0c8-40e9-96f2-a0c74306ef8e)

### Chihiro-Lump
![CL](https://github.com/goboru/GhibliBrewer/assets/112853494/05eae747-849c-4a46-b5ec-111aac0d2167)

### Chihiro-Bridge
![CB](https://github.com/goboru/GhibliBrewer/assets/112853494/724558b0-aba8-4928-b5e3-c22e46439db0)

### Chihiro-NoFace
![CN](https://github.com/goboru/GhibliBrewer/assets/112853494/18b2e9b2-754b-496a-92e9-02846b0458fb)

### Chihiro-Banquet
![ChB](https://github.com/goboru/GhibliBrewer/assets/112853494/9052937c-2675-40ae-bdc1-c3e4cb0a3653)

### Chihiro-Magic
![CM](https://github.com/goboru/GhibliBrewer/assets/112853494/7cf78c79-b24a-4037-b9c4-5f323507a629)

## The Cat Returns (2002)
### Cat-Vals
![CV](https://github.com/goboru/GhibliBrewer/assets/112853494/3e0ead77-81c8-4b0a-afe3-af2dffed22a7)

### Cat-Prince
![CP](https://github.com/goboru/GhibliBrewer/assets/112853494/99ebbbf9-39a0-4c7c-9d88-c63193da3496)

### Cat-Broom
![CaB](https://github.com/goboru/GhibliBrewer/assets/112853494/6a169d5c-9560-4bed-9b87-8a2fb21656fc)

### Cat-Bubble
![CatB](https://github.com/goboru/GhibliBrewer/assets/112853494/54fc4abd-fd5c-4384-8c52-13ee2b6d1357)

## Howl's Moving Castle (2004)
### Howl-Horizon
![HH](https://github.com/goboru/GhibliBrewer/assets/112853494/03a7f97f-d3f6-4e59-91aa-deea05d0c1d0)

### Howl-Peace
![HoP](https://github.com/goboru/GhibliBrewer/assets/112853494/2d57ebf2-9ece-4a66-9f9f-029048ef9f27)

### Howl-Terrace
![HT](https://github.com/goboru/GhibliBrewer/assets/112853494/5480d7f8-78d9-4160-b8c8-7d9854d07c9a)

### Howl-FireDemon
![HF](https://github.com/goboru/GhibliBrewer/assets/112853494/17ed6e79-94c8-4e7a-ad0f-afefba24ba39)

### Howl-Star
![HS](https://github.com/goboru/GhibliBrewer/assets/112853494/cb141409-bc1f-49fe-a167-85dfcb5c03fe)

### Howl-Breakfast
![HB](https://github.com/goboru/GhibliBrewer/assets/112853494/d32f4f06-4a80-4904-8d4b-83122b44ffc5)

### Howl-Castle
![HC](https://github.com/goboru/GhibliBrewer/assets/112853494/0e295a98-64e9-4bf8-9100-97723937addd)

### Howl-Heart
![HoH](https://github.com/goboru/GhibliBrewer/assets/112853494/299f6d20-5ab3-4610-8fae-4e4ff8b59885)

## Tales from Earthsea (2006)
### Earthsea-Silk
![ES](https://github.com/goboru/GhibliBrewer/assets/112853494/d10873ad-7da0-41d7-8c88-78c0ea93247c)

### Earthsea-Lightning
![EL](https://github.com/goboru/GhibliBrewer/assets/112853494/38b1346a-5d2a-4c5f-9484-ba293607184c)

## Ponyo (2008)
### Ponyo-Joy
![PJ](https://github.com/goboru/GhibliBrewer/assets/112853494/f46227be-a35c-478d-b3b9-08dd8cc0f461)

### Ponyo-Ramen
![PR](https://github.com/goboru/GhibliBrewer/assets/112853494/3c3bd898-8618-4385-8899-968c1c072e7a)

### Ponyo-Boat
![PB](https://github.com/goboru/GhibliBrewer/assets/112853494/1417cd2f-e403-4c29-a8c0-be26a8ebff7c)

### Ponyo-Trash
![PT](https://github.com/goboru/GhibliBrewer/assets/112853494/5e62ab04-3d06-43ac-adad-c7f5d617534f)

### Ponyo-Godess
![PoG](https://github.com/goboru/GhibliBrewer/assets/112853494/8eb0c788-88a5-49f9-a7a3-e81cea85b207)

## Arrietty (2010)
### Arrietty-Garden
![AG](https://github.com/goboru/GhibliBrewer/assets/112853494/a87e3aa7-aace-401c-9846-2869b5db5c90)

### Arrietty-Bedroom
![AB](https://github.com/goboru/GhibliBrewer/assets/112853494/46b3dee9-a543-479d-971a-b9fe3551c9db)

## The Wind Rises (2013)
### Wind-Timer
![WT](https://github.com/goboru/GhibliBrewer/assets/112853494/a388948f-9b41-43f8-8c99-3243c9fa4656)

### Wind-Kiss
![WK](https://github.com/goboru/GhibliBrewer/assets/112853494/008ce4c9-b979-4292-8ddd-4a803253ba22)

## The Tale of the Princess Kaguya (2013)
### Kaguya-Kimono
![KK](https://github.com/goboru/GhibliBrewer/assets/112853494/c2c81ef7-b48d-485d-aa9c-4926be0deed4)

## When Marnie Was There (2014)
### Marnie-Bedroom
![MB](https://github.com/goboru/GhibliBrewer/assets/112853494/61b077c4-9adf-420b-aecc-2452f724f931)

### Marnie-Train
![MT](https://github.com/goboru/GhibliBrewer/assets/112853494/efbfa8a3-a308-4267-9221-06eed288d8ac)

### Marnie-Boat
![MaB](https://github.com/goboru/GhibliBrewer/assets/112853494/0fb897c0-42d2-4ce9-9a57-bde430221a7d)

## The Boy and the Heron (2023)
### Heron-Troop
![HeT](https://github.com/goboru/GhibliBrewer/assets/112853494/790c6957-5149-4bc0-a498-7cd4ace6a6a9)

### Heron-Jelly
![HJ](https://github.com/goboru/GhibliBrewer/assets/112853494/110faeb5-81a0-4f9b-8c86-5d69162ca852)

### Heron-Parrots
![HP](https://github.com/goboru/GhibliBrewer/assets/112853494/72f4ce01-e44f-4fab-ac2e-a7d8db2af017)

### Heron-Hug
![HeH](https://github.com/goboru/GhibliBrewer/assets/112853494/503ec721-c04a-45db-8b0c-117a71371419)




*If you have come this far, why don't you try your expertise with game.ghib() ?*
