# Dokumentacja Techniczna Dla Mobilnej Aplikacji DFN 2020
Pliki konfiguracyjne znajdują się na ftp'ie
vm-szkoly.wcss.wroc.pl
w katalogu public_html/_mobile/

## Struktura katalogów:
* events-dfn.json - plik zawiera wydarzenia odbywające się w trakcie festiwalu. Zalecamy aby plik zawierał tylko wydarzenia z danego roku
* news-dfn.json - plik zawiera aktualności, które są wyświetane w aplikacji mobilnej
* dfn/
  * brain.png potrzebny do pliku konfiguracyjnego (wyświetlany na splash screenie)
  * nauka2.0.png potrzebny do pliku konfiguracyjnego (wyświetlany na splash screenie)
  * about_us.md zawartość pliku jest wyświetlana w aplikacji w zakładce "O nas", w celu formatowania pliku wykorzystujemy markdown - formattery dla dokumentów online: https://dillinger.io/
  * configFile.json - plik konfiguracyjny aplikacji  
  * sponsors/.. w tym katalogu trzymamy wszystkich sponsorów


## Plik konfiguracyjny 

### Przykład pliku konfiguracyjnego

    {
      "appVersion": "1.0.0",
      "configVersion": 4,
      "maxNewsCount": 7,
      
      "theme": {
        "primaryColor": "0xFF854DCF",
        "secondaryColor": "0xFFB32750",
        "accentColor": "0xFFF86000",
        "backgroundColor": "0xFFFFB6C1",
        "appBarColor": "0xFFE066FF"
      },
      
      "logo": "http://www.festiwal.wroc.pl/_mobile/dfn/brain.png",
      "taglineLogo": "http://www.festiwal.wroc.pl/_mobile/dfn/nauka2.0.png",
      "tagline": "Nauka 2.0",
      "website": "http://www.festiwal.wroc.pl",
      
      "newsFeed": "http://www.festiwal.wroc.pl/_mobile/news-dfn.json",
      "eventsFeed": "http://www.festiwal.wroc.pl/_mobile/events-dfn.json",
      "aboutFeed": "http://www.festiwal.wroc.pl/_mobile/dfn/about_us.md",
      
      "sponsors": [
        {
          "type": "patron",
          "name": "MINISTERSTWO NAUKI I SZKOLNICTWA WYŻSZEGO",
          "logo": "http://www.festiwal.wroc.pl/storage/image/XVI%20DFN%202013/logotypy/mnisw.jpg",
          "description": "patron",
		  "link":"https://www.gov.pl/web/nauka/"
        },
        {
          "type": "patronage",
          "name": "Urząd Miejski Wrocławia",
          "logo": "http://www.festiwal.wroc.pl/storage/image/XXDFN/logotypy/PL_podstawowy-01.jpg",
          "description": "patronage",
		  "link": "https://www.wroclaw.pl/"
        },
        {
          "type": "patronage",
          "name": "Wrocławskie Centrum Akademickie",
          "logo": "http://www.festiwal.wroc.pl/storage/image/XXIII%20DFN%202020/logoWCA.jpg",
          "description": "patronage",
		  "link": "https://www.wroclaw.pl/"
        },
        {
          "type": "grant",
          "name": "Urząd Marszałkowski Województwa Dolnoślaskiego",
          "logo": "http://www.festiwal.wroc.pl/storage/image/logo/logo-dolnyslask.gif",
          "description": "patronage",
		  "link": "https://www.wroclaw.pl/"
        },
        {
          "type": "mediaPatronage",
          "name": "Miejskie Przedsiębiorstwo Wodociągów i Kanalizacji we Wrocławiu S.A.",
          "logo": "http://www.festiwal.wroc.pl/storage/image/XXDFN/logotypy/mpwik.png",
          "description": "mediaPatronage",
		  "link": "https://www.wroclaw.pl/"
        },
        {
          "type": "mediaPatronage",
          "name": "Stan-Mit-Serwis",
          "logo": "http://www.festiwal.wroc.pl/storage/image/logo/logo_sms.GIF",
          "description": "mediaPatronage",
		  "link": "https://www.wroclaw.pl/"
        },
        {
          "type": "mediaPatronage",
          "name": "Miesięcznik 'Delta'",
          "logo": "http://www.festiwal.wroc.pl/storage/image/XVI%20DFN%202013/logotypy/delta.jpg",
          "description": "mediaPatronage",
		   "link": "https://www.wroclaw.pl/"
        },
        {
          "type": "mediaPatronage",
          "name": "Miesięcznik 'Chemik'",
          "logo": "http://www.festiwal.wroc.pl/storage/image/logo/chemik(1).jpg",
          "description": "mediaPatronage",
		   "link": "https://www.wroclaw.pl/"
        },
        {
          "type": "mediaPatronage",
          "name": "TVP 3 Wrocław",
          "logo": "https://pl.wikipedia.org/wiki/TVP3_Wroc%C5%82aw#/media/Plik:Tvp3wroclaw.png",
          "description": "TVP 3 Wrocław",
		  "link": "https://www.wroclaw.pl/"
        }
      ]
    }


### Opis pól  
  
#### Konfiguracja pliku

Nazwa Pola | Opis | Typ | Przykład
------------ | ------------- | ------------- | -------------
appVersion | jest to pole wersji aplikacji mobilnej, w tym polu powinno się trzymać najnowszą wersję aplikacji mobilnej która została zreleasowana. Android i iOS powinny mieć zawsze tą samą wersję, nigdy nie zmniejszamy tego parametru | String, tekst | "1.0.0"
configVersion | aktualna wersja pliku konfiguracyjnego, zalecamy zwiększanie jej o 1 przy aktualizacji, nigdy nie zmniejszamy tego parametru | Liczba całkowita | 4
maxNewsCount | liczba ostatnich newsów, które chcemy pokazać w aplikacji mobilnej | Liczba całkowita | 7

    {
     "appVersion": "1.0.0",
     "configVersion": 4,
     "maxNewsCount": 7,
     ...
    }
    
#### Konfiguracja Stylu/Kolorów

Them zawiera "kolory" dla aplikacji - są to kolory główne w aplikacji. Zmiana tych kolorów w pliku konfiguracyjnym wpłynie na zmianę kolorów 
Nazwa Pola | Opis | Typ | Przykład
------------ | ------------- | ------------- | -------------
primaryColor| główny kolor aplikacji, wykorzystany w tytule, przyciskach | Color w hexie, wraz z informacją o transparencji/przezroczystości w pierwszej części 0xFF | "0xFF854DCF"
secondaryColor | kolor wykorzystywany w opisach aktualności, wydarzeń oraz kiedy dany przycisk jest nieaktywny | Color w hexie, wraz z informacją o transparencji/przezroczystości w pierwszej części 0xFF | "0xFF747589"
accentColor | kolor wykorzystany głównie w nagłówkach  |  Color w hexie, wraz z informacją o transparencji/przezroczystości w pierwszej części 0xFF  | "0xFFEB4280"
backgroundColor | kolor tła aplikacji |  Color w hexie, wraz z informacją o transparencji/przezroczystości w pierwszej części 0xFF   | "0xFFF4F4F4"
appBarColor | kolor głównego/górnego menu |  Color w hexie, wraz z informacją o transparencji/przezroczystości w pierwszej części 0xFF | "0xFF3B4FE3"

    {
    ...    
     "theme": {
            "primaryColor": "0xFF854DCF",
            "secondaryColor": "0xFF747589",
            "accentColor": "0xFFEB4280",
            "backgroundColor": "0xFFF4F4F4",
            "appBarColor": "0xFF3B4FE3"
          },
    ...      
    }
    
##### Przykład kolorów 

![News](https://github.com/apachucy/fileRespository/raw/master/images/news.jpg)
Przykład wykorzystania domyślnej kolorystyki na ekranie aktualności

![News](https://github.com/apachucy/fileRespository/raw/master/images/news_alternative.jpg)
Przykład wykorzystania alternatywnej kolorystyki na ekranie aktualności

#### Konfiguracja Danych do aplikacji

Nazwa Pola | Opis | Typ | Przykład
------------ | ------------- | ------------- | -------------
logo | logo wydarzenia wykorzystane na ekranie inicjalizowania aplikacji | link | "http://www.festiwal.wroc.pl/_mobile/dfn/brain.png"
taglineLogo | Nazwa/motyw przewodni aktualnej edycji DFN w formie graficznej, wyświetla się na ekranie inicjalizowania aplikacji oraz w górnej części aplikacji (actionbar). Aktualnie: Nauka 2.0 | link |  "http://www.festiwal.wroc.pl/_mobile/dfn/nauka2.0.png" 
tagline |Nazwa/motyw przewodni aktualnej edycji DFN w formie tekstowej. Aktualnie niewykorzystany w aplikacji | tekst | "Nauka 2.0"
website | adress strony DFNu, który otwierany jest po naciśnięciu ikony w actionbarze (ikonka świata)| link | "http://www.festiwal.wroc.pl"
newsFeed | link do pliku, który zawiera newsy, które chcemy pokazać w zakładce "Aktualności" | link | "http://www.festiwal.wroc.pl/_mobile/news-dfn.json"
eventsFeed | link do pliku, który zawiera wydarzenia, które chcemy pokazać w zakładce "Wydarzenia" | link | "http://www.festiwal.wroc.pl/_mobile/events-dfn.json"
aboutFeed | link do pliku, który zawiera informacje o festiwalu, dane z tego pliku będą widoczne w zakładce "O nas" | link | "http://www.festiwal.wroc.pl/_mobile/dfn/about_us.md"

    {
        ...
        "logo": "http://www.festiwal.wroc.pl/_mobile/dfn/brain.png",
        "taglineLogo": "http://www.festiwal.wroc.pl/_mobile/dfn/nauka2.0.png",
        "tagline": "Nauka 2.0",
        "website": "http://www.festiwal.wroc.pl",
        "newsFeed": "http://www.festiwal.wroc.pl/_mobile/news-dfn.json",
        "eventsFeed": "http://www.festiwal.wroc.pl/_mobile/events-dfn.json",
        "aboutFeed": "http://www.festiwal.wroc.pl/_mobile/dfn/about_us.md",
        ...
    }

![Splash Screen](https://github.com/apachucy/fileRespository/raw/master/images/splash_screen.jpg)
Ekran splash screen wyświetla "taglineLogo" oraz "logo"
![News](https://github.com/apachucy/fileRespository/raw/master/images/news.jpg)
Ekran Aktualności wyświetla informacje, które znajduja się w "newsFeed"
![Events](https://github.com/apachucy/fileRespository/raw/master/images/events.jpg)
Ekran Wydarzeń wyświetla informacje, które znajdują się w propercie "eventsFeed"

#### Sponsorzy

Nazwa Pola | Opis | Typ | Przykład
------------ | ------------- | ------------- | -------------
type | typ sponsora, widoczny na zakładce sposorzy w aplikacji mobilnej. Aplikacja mobilna zawiera następujące typy: regular, patron, grant, support, patronage, mediaPatronage, partner. Dodanie innego typu bez dodania go do aplikacji mobilnej wpłynie na błędne działanie aplikacji| tekst | "regular"
name | nazwa sponsora, aktualnie niewykorzystywana w aplikacji (pole może być puste)| tekst | "Wrocławskie Centrum Akademickie"
logo | logo sponsora | link | "http://www.festiwal.wroc.pl/storage/image/XXIII%20DFN%202020/logoWCA.jpg"
description | dodatkowy opis przeznaczony dla sponsora, aktualnie pole niewykorzystywane w aplikacji (pole może być puste) | tekst | "Wrocław jest miastem akademickim. Pracownicy naukowi i studenci stanowią znaczną część populacji. Miejski samorząd kieruje swoją uwa."
link | strona sponsora, pole może być puste | String | "https://www.wroclaw.pl/"

    {
        ...
        "sponsors": [
            {
              "type": "patron",
              "name": "MINISTERSTWO NAUKI I SZKOLNICTWA WYŻSZEGO",
              "logo": "http://www.festiwal.wroc.pl/storage/image/XVI%20DFN%202013/logotypy/mnisw.jpg",
              "description": "patron",
    		  "link":"https://www.gov.pl/web/nauka/"
            },
        ...
    }    
        

![Sponsorzy](https://github.com/apachucy/fileRespository/raw/master/images/sponsors.jpg)
Ekran ten zawiera informacje z tablicy "sponsors"
