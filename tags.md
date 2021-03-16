Eigenschappen van kaart-elementen specifiek voor het Kadaster-1832, volgens het OpenStreetMap-tagging schema.

# Algemeen
* alle eigenschappen worden vermeld als een `key=value`-tag
* `name` is de algemene key om gelijk welk object een naam te geven

# Lijnen
* Dijken als vlak worden aangegeven met `landuse=construction`
* Water als vlak wordt aangegeven met `natural=water`

## Wegen

Allen getagged met de `highway`-key;
* `trunk` > `primary` > `secondary` voor **hoofdwegen**
* `tertiary` voor algemeen **doorgaande** wegen
* `unclassified` voor **lokale** wegen
* `residential` voor woon-straten in een bebouwde kom, doorgaans voorzien van een `name`
* `track` voor paden over een ander grondgebruik heen (dus niet noodzakelijk karrepaden met een spoorbreedte)
* `path` voor kleinere wegen / paden die met streepjes worden aangegeven op het minuutplan
* `pedestrian` / `footway` voor een path in een bebouwde kom (dus vaak steegjes, al dan niet met een `name`)
* `construction` voor wegen-in-aanleg, waarbij het in-aanleg-zijnde-type als `construction=*` wordt opgenomen

## Waterlopen

Allen getagged met de `waterway`-key;
* `river` voor grotere rivieren
* `canal` voor gegraven kanalen
* `stream` voor kleinere waterloopjes, het default-type
* `ditch` voor zeer kleine slootjes, vb ter afwatering van de weg(berm)

# Plaatsen

Allen getaagged met de `place`-key, in de regel ook voorzien van een `name`-tag;
* `city` voor een grote stad
* `town` voor een kleiner stadje
* `village` voor een dorp
* `hamlet` voor een gehucht
* `isolated_dwelling` voor losse gebouwen als mini-nederzetting
* `islet` voor eilanden
* `locality` voor een veldnaam

# Grenzen
Dit zijn allen relations, met als kenmerken;
* `type=boundary`
* `boundary=administrative`
* `admin_level=*` voor het hiërarchische niveau van de eenheid
* doorgaans een `name`
* `gebiedstype="kadastrale gemeente"`
* `kad:provincie=*` met de vermelding van de provincie anno 1832

# Kadastraal adres: identificatie van een perceel

Er zijn twee schema's in gebruik voor het taggen van het kadastraal adres: de eigenlijke referentie-tags, en het schema zoals dat wordt toegepast in de bredere OSM-community en vb. de HouseNumberTaggingTool;
| Referentie-key | Alternatieve `addr`-tag | voorbeeld | betekenis
| :---           | :------------------------- | :-------- | :--------
| `kad:adres`    |                            | Amsterdam A1/bis | het volledige kadastrale adres, ongesplitst
| `kad:gemeente` | `addr:city`                | Amsterdam | De kadastrale **gemeente** van het perceel
| `kad:sectie`   | `addr:county`              | A | de kadastrale **sectie** van het perceel
| `kad:perceelnr` | `addr:housenumber` | 1 | het eigenlijke perceelnummer, in de regel een integer
| `kad:perceelnrtvg` | | bis | (optioneel) de toevoeging / suffix op het perceelnummer, zoals *bis*
| `kad:blad`     | `addr:country` | 1 | (optioneel) het blad-nummer van het minuutplan waarop het perceel afgebeeld staat
| `minuutplan`   | | MIN07005A01 | (optioneel) de volledige code van het minuutplan

# Gebouwen

Allen getagged met de `building`-key;
* `yes` als default waarde
* `house` voor huizen
* `shed` voor schuren
* `warehouse` voor pakhuizen

Aanvullend;
* `man_made=windmill` voor molens

# Ongebouwd

* `landuse=meadow` voor **weiland**
  - `landuse=grass` voor functioneel gras, zoals een uitweg
  - `landuse=village_green` voor centrale parken in een stad
* `landuse=farmland` voor **bouwland**
    - `crop=*` om het gewas mee aan te geven indien gekend, vb `aardappel` of `tabak`
* `landuse=allotments` voor tuinbouw-grond (**tuin**)
* `landuse=residential` voor een huis-erf / **erf** 
    - `landuse=commercial` voor commerciële erven
    - `landuse=farmyard` voor boerderij-erven
    - `landuse=retail` voor winkels
    - `landuse=industrial` voor industrie
* `landuse=cemetery` voor **begraafplaats**
* `landuse=orchard` voor **boomgaard**
* `landuse=plant_nursery` voor een planten-**kwekerij**
* `leisure=garden` voor siertuin / **terrein tot vermaak**
    - `leisure=pitch` voor sportvelden, veelal kolf
* `landuse=forest` voor **bos**
    - `leaf_type=needleleaved` voor naaldbos
* `landuse=construction` voor **dijken** en kaden
* `landuse=landfill` voor **vuilnis**-stort-plekken
* `landuse=military` voor **militair**e terreinen
* `landuse=quarry` voor **vergraven gronden**
* `natural=sand` voor **zand** (strand, zand-verstuiving, duin, ...)
    - `landuse=beach` voor strand
    - `natural=mud` voor natte zandvlakten, meestal in de context van een getijdengeul
* `natural=heath` voor **heide**
* `natural=water` voor **water**
* `natural=wetland` voor natte gronden in het algemeen, met een paar subtypen, aangegeven met de `wetland=*` tag;
    - `wetland=wet_meadow` voor **hooiland**
    - `wetland=reedbed` voor **riet(land)**
    - `wetland=bog` voor **veen**
    - `wetland=marsch` voor **moeras**



