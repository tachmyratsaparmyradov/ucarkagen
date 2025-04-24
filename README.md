# Üç arka generator
Maglumatlar yaml faýlynda berilýär we generator berlen nusgany dolduryp berýär

## Nädip işletmeli?
* Giriş maglumatlar ".yaml" faýl
* Nusga ".docx" faýl
* Taýýarlamaly üç arka ".docx" faýlyň ýeri
``` python
from ucarkagen import ucarkagen

ucarkagen("giris.yaml", "nusga.docx", "ucarka.docx")
```

## YAML faýl
* men - özi barada maglumat
* is-yerler - özüniň iş ýerleri tablisasynyň maglumaty, her sanaw elementi aýratyn setiriň maglumaty. 'men'-iň içinde ýerleşmeli
* garyndas - garyndaşlar tablisasynyň maglumaty, her sanaw elementi aýratyn setiriň maglumaty

Ýokardaky üç açar sözüni üýtgetmek gadagan. Galan açar sözler üýtgäp biler, ýöne nusgadaky degişli bellikleri hem üýtgetmeli bolýar.
``` yaml
men:
  ady: Plany
  familiyasy: Planyýew
  ata-ady: Planyýewiç
  doglan-guni: 01.01.1990ý
  doglan-yeri: Aşgabat ş.
  milleti: türkmen
  bilimi: ýokary
  okuw-mekdebi: 2013-nji ýyl, ABŞ MIT
  hunari: Software Engineer
  alym-dereje: ýok
  dil: türkmen, rus, iňlis
  sylag: ýok
  dasary-yurt: ýok
  mejlis-agza: ýok
  is-yerler:
    - wagty: 2024ý ýanwar - 2024ý dekabr
      salgy: Soft Inc, web-dev
    - wagty: 2025ý ýanwar - 2025ý dekabr
      salgy: Game Inc, game developer
  oy-salgysy: Earth Orbit, ISS
  telefon: +1234567890 (home)

garyndas:
  - faa: Meredow Meret Meredowiç
    dereje: atasy
    doglan-yyly: 1900
    doglan-yeri: Aşgabat ş.
    is-yeri: Proffessor, ABŞ MIT
    oy-salgysy: Earth Orbit, ISS
  - faa: Meredow Meret Meredowiç
    dereje: kakasy
    doglan-yyly: 1900
    doglan-yeri: Aşgabat şäheri
    is-yeri: Proffessor, ABŞ MIT
    oy-salgysy: Earth Orbit, ISS
```

## Nusga
Nusga ".docx" faýly bolmaly. Ondaky bellikleriň ählisi **'%'** bilen başlamaly. Bellikleriň üç görnüşi bar - prefiksler boýunça:
* **"%men-"** - yaml faýlyndaky "men" maglumatlar bilen doldurylýar. Meselem:
  ``` yaml
  men:
    ady: Plany
  ```
  Bu ýerde *".docx"* faýlyndan *"%men-ady"* belligi gözlener we tapsa ýeri *"Plany"* bilen çalşylar
* **"%men-is-yerler-"** - yaml faýlyndaky *"men"*-iň içindäki *"is-yerler"* sanawy bilen doldurylýar. Bu bellikleriň hemmesi hökman diňe bir tablisada ýerleşmeli
* **"%garyndas-"** - yaml faýlyndaky *"garyndas"* sanawy bilen doldurylýar. Bu bellikleriň hemmesi hökman diňe bir tablisada ýerleşmeli

## Talaplar
2 modul talap edilýär:
1. [PyYAML](https://pypi.org/project/PyYAML/)
2. [python-docx](https://pypi.org/project/python-docx/)
