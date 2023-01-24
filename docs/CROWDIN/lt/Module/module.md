---
substitutions:
  DiaLink: |-
    ```{image} ../images/omnipod/DiaLink.png
    ```
  EmaLink: |-
    ```{image} ../images/omnipod/EmaLink.png
    ```
  LoopLink: |-
    ```{image} ../images/omnipod/LoopLink.png
    ```
  OrangeLink: |-
    ```{image} ../images/omnipod/OrangeLink.png
    ```
  RileyLink: |-
    ```{image} ../images/omnipod/RileyLink.png
    ```
---

# Component Overview

AndroidAPS is not just a (self-built) application, it is just one of several modules of your closed loop system. Before deciding for components, it would be a good idea to have a look at the [component setup](../index#component-setup), too.

```{image} ../images/modules.png
:alt: Components overview
```

```{eval-rst}
.. pastaba::
   **SVARBUS SAUGOS ĮSPĖJIMAS**

   Šioje dokumentacijoje aprašytos pagrindinės AndroidAPS saugos funkcijos, grindžiamos aparatinės įrangos, su kuria nustatėte savo sistemą, saugos savybėmis. Labai svarbu, kad insulino pompa ir CGM sistema, naudojama uždaro ciklo sistemai su automatiniu insulino tiekimu, būtų tinkamai išbandytos ir visiškai veikiančios, pažymėtos CE ženklu (Europoje) kaip medicinos prietaisai. Šių komponentų aparatinės ar programinės įrangos pakeitimai gali sukelti netikėtą insulino tiekimą ir taip sukelti didelę riziką vartotojui. Nenaudokite sugedusių, modifikuotų ar pačių pagamintų insulino pompų ar CGM duomenų skaitytuvų, kad sukurtumėte ar valdytumėte AndroidAPS sistemą.

   Be to, ne mažiau svarbu naudoti tik originalius priedus, tokius kaip įšovikliai, kateteriai ir insulino rezervuarai, patvirtinti jūsų pompos ar CGM gamintojo. Nepatikrintų ar modifikuotų priedų naudojimas gali sukelti CGM sistemos netikslumus ir insulino tiekimo klaidas. Insulinas yra labai pavojingas, jei jis neteisingai dozuotas. Nežaisk su savo gyvenimu naudodamas neišbandytus ar modifikuotus priedus.

   Galiausiai, jūs neturėtumėte vartoti SGLT-2 inhibitorių (glifozinų), nes jie nenuspėjamai sumažina cukraus kiekį kraujyje.  Ypač pavojingas derinys su sistema, kuri sumažina bazę siekdama pakelti glikemiją, nes dėl gliflozinų šis glikemijos padidėjimas gali neįvykti ir gali grėsmingai pritrūkti insulino.
```

## Būtinieji Moduliai

### Geri individualūs insulino dozavimo algoritmai

Nors jūs negalite nei nusipirkti, nei lengvai sukurti, greičiausiai tai yra modulis, kuris labiausiai nuvertinamas, nors jis yra būtinas uždaram ciklui. Jei algoritmas padės palaikyti diabeto valdymą, jam reikia teisingų nustatymų, kad nepriimtumėte rimtų klaidingų sprendimų.
Net jei dar trūksta kitų modulių, kartu su diabeto komanda galite patikrinti ir pakoreguoti esamą „profilį“.
Dauguma uždaro ciklo naudotojų naudoja vadinamąją cirkadinę valandinę bazę, insulino jautrimo faktorių bei insulino ir angliavandenių santykio faktorius, kurie yra pagrįsti hormoniniu jautrumu insulinui dienos metu.

Profilį sudaro

- Bazė
- JIF (jautrumo insulinui faktorius) yra jūsų kraujo gliukozės kiekis, kurį sumažina vienas vienetas insulino
- CR (carb ratio) is grams carbohydrate per one unit insulin
- IVT (insulino veikimo trukmė).

### Negalima naudoti SGLT-2 inhibitorių

SGLT-2 inhibitoriai, dar vadinami gliflozinais, slopina gliukozės absorbciją (pasisavinimą) inkstuose. Kadangi jie nenuspėjamai sumažina gliukozės kiekį kraujyje, jų NEGALIMA naudoti su uždaro ciklo sistema, pavyzdžiui, AndroidAPS! Yra didžiulė ketoacidozės ar hipoglikemijos rizika! Ypač pavojingas šių medikamentų derinys su sistema, kuri sumažina bazę siekdama pakelti glikemiją, nes dėl gliflozinų šis glikemijos padidėjimas gali neįvykti ir gali grėsmingai pritrūkti insulino.

### Telefonas

The current version of AndroidAPS requires an Android smartphone with Google Android 8.0 or above. So if you are thinking about a new phone, Android 8.1 is recommended at a minimum but optimally choose Android 9 or 10.
Users are strongly encouraged to keep their build of AndroidAPS up to date for safety reason, however for users unable to use a device with a minimum version of Android 8.0, AndroidAPS version 2.6.1.4, suitable for older Android versions, remains available from the [old repository.](https://github.com/miloskozak/androidaps)

Vartotojai sukūrė [patikrintų išmaniųjų telefonų ir išmaniųjų laikrodžių, sąrašą:\<https://docs.google.com/spreadsheets/d/1gZAsN6f0gv6tkgy9EBsYl0BQNhna0RDqA9QGycAqCQc/edit?usp=sharing>][patikrintų išmaniųjų telefonų ir išmaniųjų laikrodžių, sąrašą:<https://docs.google.com/spreadsheets/d/1gzasn6f0gv6tkgy9ebsyl0bqnhna0rdqa9qgycaqcqc/edit?usp=sharing>]

Norėdami įvesti mobilųjį telefoną ar išmanųjį laikrodį, kurio dar nėra sąraše, užpildykite formą \<<https://docs.google.com/forms/d/e/1FAIpQLScvmuqLTZ7MizuFBoTyVCZXuDb__jnQawEvMYtnnT9RGY6QUw/viewfor>>'\_.

Praneškite apie bet kokias lentelės problemas el. paštu [hardware@androidaps.org](mailto:hardware@androidaps.org). Jei norite pateikti mobiliuosius telefonus ar išmaniuosius laikrodžius testavimui, atsiųskite el. laišką adresu [donations@androidaps.org](mailto:hardware@androidaps.org).

### Insulino pompa

AndroidAPS **šiuo metu** veikia su

- [Accu-Chek Combo](../Configuration/Accu-Chek-Combo-Pump.md) (additionally needed: Ruffy app, LineageOS or Android 8.1 on your phone)
- [Accu-Chek Insight](../Configuration/Accu-Chek-Insight-Pump.md)
- [DanaR](../Configuration/DanaR-Insulin-Pump.md)
- [Dana-i/RS](../Configuration/DanaRS-Insulin-Pump.md)
- [some old Medtronic pumps](../Configuration/MedtronicPump.md) from upcoming version 2.4 ([additional communication device](../Module/module#additional-communication-device) needed)
- [Omnipod Eros](../Configuration/OmnipodEros.md) ([additional communication device](../Module/module#additional-communication-device) needed)
- [Omnipod DASH](../Configuration/OmnipodDASH.md)

If no additional communication device  is mentioned the communication betweeen insulin pump and AndroidAPS is based on the integrated bluetooth stack of Android without the need of an additional communication device to translate the communnication protocol.

\*\* Kitos pompos\*\*, kurios ateityje gali veikti su AndroidAPS, yra išvardytos puslapyje „Ateityje galimos naudoti pompos" \<../Getting-Started/Future-possible-Pump-Drivers.md>\`\_.

Jei norite įsigyti pompą \*\* savo lėšomis , tiekėjų adresus skirtingose šalyse galite rasti šioje lentelėje \<<https://drive.google.com/open?id=1CRfmmjA-0h_9nkRViP3J9FyflT9eu-a8HeMrhrKzKz0>>“. Prašome užpildyti savo pardavėjo informaciją, jei ji dar nėra joje nurodyta.

#### Additional communication device

For old medtronic pumps an additional communication device (besides your phone) is needed to "translate" the radio signal from pump to bluetooth. Make sure to choose the correct version depending on your pump.

- {{ OrangeLink }}  [OrangeLink Website](https://getrileylink.org/product/orangelink)
- {{ RileyLink }} [433MHz RileyLink](https://getrileylink.org/product/rileylink433)
- {{ EmaLink }}  [Emalink Website](https://github.com/sks01/EmaLink) - [Contact Info](mailto:getemalink@gmail.com)
- {{ DiaLink }}  DiaLink - [Contact Info](mailto:Boshetyn@ukr.net)
- {{ LoopLink }}  [LoopLink Website](https://www.getlooplink.org/) - [Contact Info](https://jameswedding.substack.com/) - Untested

**Kuri pompa labiausiai tinka uždaro ciklo sistemai su AndroidAPS?**

Combo, Insight ir senesnės Medtronic pompos yra patikimos ir tinkamos uždaram ciklui. Dėl infuzinės sistemos standartinės Luer užrakto jungties, Combo turi didelį pranašumą. Ir tam naudojama įprasta baterija, kurią galite nusipirkti bet kurioje degalinėje ar jums patogioje parduotuvėje. Ir jei jums to tikrai reikia, galite pavogti / pasiskolinti iš nuotolinio valdymo pultelio iš viešbučio kambario ;-).

The advantages of the DanaR/RS and Dana-i vs. Combo yra:

- The Dana pumps connect to almost any phone with Android >= 5.1 without the need to flash lineage. If your phone breaks you usually can find easily any phone that works with the Dana pumps as quick replacement... su Combo tai nėra taip lengva. bent jau tol, kol Android 8.1 diegiama tik keliuose telefonų modeliuose
- Initial pairing is simpler with the Dana-i/RS. Tačiau paprastai šio žingsnio reikia tik pradinio sąrankos metu.
- Kol kas Combo dirba su ekrano analizavimu. Iš esmės tai veikia gerai, bet, deja, lėtai. Tai nėra taip blogai, ko reikia ciklui, nes visa tai veikia fone. Tačiau tai leis lengviau atšaukti esamą Bluetooth ryšį. Tai gali būti nepatogu, jei inicijuojate bolusą ir vėliau būdami per daug toli nuo išmaniojo telefono, pvz., gamindami maistą.
- The Combo vibrates on the end of TBRs, the DanaR vibrates (or beeps) on SMB. Naktį greičiausiai naudositės TBR, o ne SMB.  The Dana-i/RS is configurable that it does neither beep or vibrate.
- Reading the history on the Dana-i/RS in a few seconds with carbs makes it possible to switch phones easily while offline and continue looping as soon a soon as some CGM values are in.

Visos pompos, palaikančio AndroidAPS, yra atsparios vandeniui (bent jau naujos). Tik Dana pompos taip pat turi „garantiją dėl vandens atsparumo“ dėl uždaro akumuliatoriaus ir rezervuaro užpildymo skyriaus.

### Glikemijos šaltinis

Tai tik trumpa su AndroidAPS suderinamų NGJ monitoringo sistemų apžvalga. For further details, look [here](../Configuration/BG-Source.md). Tiesiog trumpa pastaba: jei galite pateikti gliukozės duomenis xDrip+ programoje ar Nightscout svetainėje, galite pasirinkti xDrip+ (arba Nightscout su interneto ryšiu) kaip AAPS KG šaltinį.

- [Dexcom G6](../Hardware/DexcomG6.md): BOYDA is recommended as of version 3.0 (see [release notes](../Installing-AndroidAPS/Releasenotes#important-hints) for details). xDrip+ must be at least version 2022.01.14 or newer
- [Dexcom G5](../Hardware/DexcomG5.md): Veikia su xDrip+ arba modifikuota Dexcom programa
- [Dexcom G4](../Hardware/DexcomG4.md): Šie sensoriai yra gana seni, bet jūs galite rasti instrukcijas apie tai, kaip naudoti juos su xDrip+ programa
- [Libre 2](../Hardware/Libre2.md): Veikia su xDrip+ (nereikia siųstuvo), tačiau taip pat turite sukurti savo modifikuotą programą Libre 2.
- [Libre 1](../Hardware/Libre1.md): Jums reikalingas siųstuvas, pavyzdžiui, Blucon ar MiaoMiao, kurį galite susikurti patys arba tiesiog nusipirkti, ir xDrip+ programa
- [Eversense](../Hardware/Eversense.md): Kol kas veikia tik kartu su ESEL programa ir modifikuota Eversense programa (neveikia su Dana RS ir LineageOS deriniu, tačiau gerai veikia su DanaRS ir Android arba Combo ir Lineage OS)
- [Enlite (MM640G/MM630G)](../Hardware/MM640g.md): quite complicated with a lot of extra stuff

### Nightscout

Nightscout yra atvirojo kodo žiniatinklio programa, galinti registruoti ir rodyti jūsų NGJ ir AndroidAPS duomenis bei generuoti ataskaitas. You can find more information on the [website of the Nightscout project](http://nightscout.github.io/). Galite sukurti savo [Nightscout svetainę](https://nightscout.github.io/nightscout/new_user/), naudodami pusiau automatinę Nightscout sąranką 'zehn.be \<<https://ns.10be.de/en/index.html>> \_ arba patalpinti savo serveryje (tai skirta IT ekspertams).

Nightscout yra nepriklausomas nuo kitų modulių. Jums jo reikės, kad galėtumėte įvykdyti 1-ą Tikslą.

Additional information on how to configure Nightscout for use with AndroidAPS can be found [here](../Installing-AndroidAPS/Nightscout.md).

### AAPS-.apk failas

Pagrindiniai sistemos komponentai. Prieš diegdami programą, pirmiausia turite sukurti apk failą (kuris yra Android programos failo pavadinimo plėtinys). Instructions are  [here](../Installing-AndroidAPS/Building-APK.md).

## Pasirenkamieji Moduliai

### Išmanieji laikrodžiai

Bet koks išmanusis laikrodis su Android Wear 1.x ar naujesne versija veikia. Daugelis uždaro ciklo vartotojai naudoja Sony Smartwatch 3 (SWR50), nes taip pat galima priimti reikšmes iš Dexcom G5/G6, kai išmaniojo telefono nėra diapazone. Kai kuriuos kitus išmaniuosius laikrodžius galima pritaikyti, kad juos būtų galima naudoti kaip autonominį imtuvą (žr. [dokumentaciją \<\<https://github.com/NightscoutFoundation/xDrip/wiki/Patching-Android-Wear-devices-for-use-with-the-G5>][dokumentaciją <<https://github.com/nightscoutfoundation/xdrip/wiki/patching-android-wear-devices-for-use-with-the-g5>], jei norite gauti daugiau informacijos).

Vartotojai sukūrė [patikrintų išmaniųjų telefonų ir išmaniųjų laikrodžių, sąrašą:\<https://docs.google.com/spreadsheets/d/1gZAsN6f0gv6tkgy9EBsYl0BQNhna0RDqA9QGycAqCQc/edit?usp=sharing>][patikrintų išmaniųjų telefonų ir išmaniųjų laikrodžių, sąrašą:<https://docs.google.com/spreadsheets/d/1gzasn6f0gv6tkgy9ebsyl0bqnhna0rdqa9qgycaqcqc/edit?usp=sharing>]. There are different watchfaces for use with AndroidAPS, which you can find [here](../Configuration/Watchfaces.md).

Norėdami įvesti mobilųjį telefoną ar išmanųjį laikrodį, kurio dar nėra sąraše, užpildykite formą \<<https://docs.google.com/forms/d/e/1FAIpQLScvmuqLTZ7MizuFBoTyVCZXuDb__jnQawEvMYtnnT9RGY6QUw/viewfor>>'\_.

Praneškite apie bet kokias lentelės problemas el. paštu [hardware@androidaps.org](mailto:hardware@androidaps.org). Jei norite pateikti mobiliuosius telefonus ar išmaniuosius laikrodžius testavimui, atsiųskite el. laišką adresu [donations@androidaps.org](mailto:hardware@androidaps.org).

### xDrip+

Net jei jums nereikia xDrip+ programos kaip KG duomenų šaltinio, vis tiek galite ja naudotis aliarmams arba patogų glikemijos duomenų rodymą. xDrip+ galite nustatyti norimus įspėjimo signalų, apibrėžti laiką, kada jie turėtų būti aktyvūs, ar jie gali nepaisyti išmaniojo telefono nutildymo ir pan. Some xDrip+ information can be found [here](../Configuration/xdrip.md). Atminkite, kad xDrip+ tobulinimas yra labai aktyvus ir dokumentacija kartais negali jo sekti, todėl ne visada gali būti atnaujinta.

## Ką daryti laukiant modulių

Kartais užtrunka šiek tiek laiko, kol bus gauti visi uždaro ciklo moduliai. Nesijaudinkite, laukdami galite padaryti daug. It is NECESSARY to check and (where appropriate) adapt basal rates (BR), insulin-carbratio (IC), insulin-sensitivity-factors (ISF) etc. Ir galbūt atviras ciklas gali būti geras būdas išbandyti sistemą ir susipažinti su AndroidAPS. Šiame režime AndroidAPS teikia rekomendacijas, kurių galite laikytis rankiniu būdu.

You can keep on reading through the docs here, get in touch with other loopers online or offline, [read](../Where-To-Go-For-Help/Background-reading.md) documentations or what other loopers write (even if you have to be careful, not everything is correct or good for you to reproduce).

**Atlikta?**
Jei turite visus AAPS komponentus kartu arba bent jau pakankamai, kad pradėtumėte nuo atviro ciklo, pirmiausia turėtumėte perskaityti [Tikslų skiltį](../Usage/Objectives.md) prieš pradedant naują Tikslą bei nustatyti savo
[įrangą](../index#component-setup).

% Image aliases resource for referencing images by name with more positioning flexibility

% Hardware and Software Requirements