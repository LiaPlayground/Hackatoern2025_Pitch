<!--

author:   Sebastian Zug, André Dietrich
comment:  Pitch-Talk im Rahmen des OE_Sprints - Technische Weiterentwicklung des OER-Ökosystem
email:    Sebastian.Zug@informatik.tu-freiberg.de
version:  0.0.3

language: de
narrator: Deutsch Male
edit:     true
mode:     Presentation

logo:     ./images/logo.png
link:     ./style.css

-->

[![LiaScript](https://raw.githubusercontent.com/LiaScript/LiaScript/master/badges/course.svg)](https://liascript.github.io/course/?https://raw.githubusercontent.com/LiaPlayground/Hackatoern2025_Pitch/refs/heads/main/README.md)

# OER Exporter für LiaScript

<section class="flex-container">

<!-- class="flex-child" style="min-width: 250px;" -->
> Wettbewerbsbeitrag für
>
> <h2>OE_Sprints - Technische Weiterentwicklung des OER-Ökosystem</h2>
>
><h4>Sebastian Zug & André Dietrich, 23. Juli 2025 </h4>

<!-- class="flex-child" style="min-width: 250px;" -->
![partner_map](https://github.com/LiaPlayground/LiaScript_Workshop_Lehrende_an_Schulen/blob/main/pic/LiaScript_Meets_OER.png?raw=true "OER-Logo - Quelle: Jonathasmello - Eigenes Werk, CC BY 3.0, [https://commons.wikimedia.org/w/index.php?curid=18460156](https://commons.wikimedia.org/w/index.php?curid=18460156) erweitert um LiaScript Logo")

</section>

--------------------------------------------

_ Der Quellcode kann des Open Source Dokuments ist unter [Link](https://github.com/SebastianZug/LiaScript_Workshop_Lehrende_an_Schulen/blob/main/Motivation.md) zu finden._

## Grundkonzept von LiaScript 

> [LiaScript](https://liascript.github.io/) ist eine Auszeichnungssprache für die Gestaltung von  interaktiven Lehr-Lern-Inhalte. Der Lehrende definiert den Inhalt in einer Markdown-ähnlichen Syntax, die im Browser gerendert wird. 

--------------------------------------------

__Tabellen als Grafiken__

| X | B(y) | C(y) |
|---|:----:|:----:|
| 1 |   2  |   3  |
| 4 |   5  |   6  |

__Quizze__

Wann wurde die TU Bergakademie Freiberg gegründet?

- [(X)] 1765
- [( )] 1896

__Sprachausgaben__

> Click to run!
>
> {{|> Deutsch Female}}
> Hallo liebe LiaScript Interessierte!

__Kombinationsmöglichkeiten__

    {{|> US English Male}}
Although [[ him | (he)]] usually [[walk |(walks)]] to school, today [[ him | (he)]] [[ are | (is)]] taking the bus because it [[ rain | (rains)]].

__Externe interaktive Elemente__

??[](https://phet.colorado.edu/sims/html/wave-interference/latest/wave-interference_all.html)

??[](https://tinyurl.com/25ux6rr8)

--------------------------------------------

> Die Stärke von LiaScript liegt in der Idee der einfachen Sprache, die beliebig erweitert werden kann und es erlaubt Elemente manigfaltig zur rekombinieren. Für den Austausch und die Erstellung von Lehrinhalten wird nur eine Textdatei benötigt, die Interpretation der Kurse erfolgt direkt im Browser, ohne zentralen Server oder Nutzermanagement. Damit unterstützt LiaScript die Idee von Open Educational Resources (OER).

## Alles wunderbar, oder ... ?

                           {{0-1}}
*************************************************************

<section class="flex-container">

<!-- class="flex-child" style="min-width: 250px;" -->
![](./images/AnkuendigungLehrerWorkshop.jpg "Ankündigung Lehrer Workshop")

<!-- class="flex-child" style="min-width: 250px;" -->
![](./images/AnkuendigungGeschichteWorkshop.jpg "https://digigw.hypotheses.org/4396")

</section>

> __Lehrende wünschen häufig eine Integration von Inhalten in bestehende Lernmanagementsysteme (LMS), Studierende fragen nach Skripten in Form von PDF-Dokumenten, um Notizen machen zu können.__

*************************************************************

                           {{1-2}}
*************************************************************

> Entsprechend wurde das Kommandozeilen-Tool [liaex](https://github.com/LiaScript/LiaScript-Exporter) entwickelt, das LiaScript in SCORM, IMS, PDF, Progressive Web App (PWA) und andere Formate exportiert.

```bash
$ liaex -i project/README.md --format scorm2004 --output rockOn
..
project/README.md
project/Lizenz.md
..
[12:38:31] SCORM 'Init'
[12:38:31] SCORM 'create /tmp/lia2022114-556265-d2jh0k.odg7e/pro/imsmanifest.xml'
[12:38:31] SCORM 'create /tmp/lia2022114-556265-d2jh0k.odg7e/pro/metadata.xml'
[12:38:31] SCORM 'create /tmp/lia2022114-556265-d2jh0k.odg7e/pro/XMLSchema.dtd'
[12:38:31] SCORM 'create /tmp/lia2022114-556265-d2jh0k.odg7e/pro/adlcp_v1p3.xsd'
```

Beispiele für die Einbettung von LiaScript ins sächsische OPAL-LMS finden sich unter [LiaScript Meets OER](https://bildungsportal.sachsen.de/opal/auth/RepositoryEntry/28960423936?5).

*************************************************************


## Sprintziel



<section class="flex-container">

<!-- class="flex-child" style="min-width: 250px;" -->

<div class="flex-child" style="min-width: 250px;">

> __Das Vorhaben wandelt den Exporter in eine lokale bzw. optionale Cloud-Server-App mit grafischer Oberfläche um und erweitert den Funktionsumfang um xAPI-Unterstützung.__

![Realisierung](./images/Konzept.png "Elemente der Umsetzungsidee")

</div>

<!-- class="flex-child" style="min-width: 250px;" -->
![Goal](./images/goal_small.jpg "Mögliche Ansicht des LiaScript Exporters in der Variante als Webservice")

</section>


## Nachhaltigkeit 

> + __Niederschwelliger Einstieg__: Lehrkräfte können bestehende LiaScript OER Materialien per Mausklick exportieren und unmittelbar in „ihrem“ LMS hochladen.
> + __Mehrwert durch Analytik__: SCORM- und xAPI-Pakete schreiben Fortschritts- und Interaktionsdaten zurück; so lassen sich Kurse evidenzbasiert qualitativ verbessern.
> + __Geräte- und Plattformvielfalt__: Durch plattformübergreifende Paketierung (z. B. via pkg) der Kurse entstehen lauffähige Installationen für Windows, macOS, Linux und Android.


            {{1-2}}
***********************************************

!?[Twillo](https://www.youtube.com/watch?v=2_aE9SwN1Rs)


<!-- style="background-color: yellow; font-size: 16ptx" -->
> __Wir freuen uns auf Ihre Fragen!__

***********************************************