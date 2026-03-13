---
title: "16 - Formatage des dates"
description: "Liste des fonctions (formatters) pour formater les dates JSON"
date: "2025-11-20"
version: "1"
---

# Formatage des dates

Liste de fonctions pour formater vos dates JSON.

---

## Sommaire

- `:formatD`
- `:addD`
- `:subD`
- `:startOfD`
- `:endOfD`
- `:diffD`
- `:convDate`
- Formats de date

---

## :formatD(patternOut, patternIn)

Formater des dates.

Ce formatter prend un **pattern de sortie** en argument. Les patterns de date sont listés dans la section **Formats de date**.

Il est possible de modifier :
- le fuseau horaire via l’option `options.timezone`
- la langue via l’option `options.lang`

Liste des fuseaux horaires : https://en.wikipedia.org/wiki/List_of_tz_database_time_zones

### Paramètres

| Paramètre | Description | Type |
|---|---|---|
| `patternOut` | format de sortie | String |
| `patternIn` | format d’entrée, **ISO 8601** par défaut | String |

### Exemples

```text
// With API options: {
//   "lang": "en-us",
//   "timezone": "Europe/Paris"
// }
'20160131':formatD('L') // "01/31/2016"
'20160131':formatD('LL') // "January 31, 2016"
'20160131':formatD('LLLL') // "Sunday, January 31, 2016 12:00 AM"
'20160131':formatD('dddd') // "Sunday"
// With API options: {
//   "lang": "fr",
//   "timezone": "Europe/Paris"
// }
'2017-05-10T15:57:23.769561+03:00':formatD('LLLL') // "mercredi 10 mai 2017 14:57"
'2017-05-10 15:57:23.769561+03:00':formatD('LLLL') // "mercredi 10 mai 2017 14:57"
'20160131':formatD('LLLL') // "dimanche 31 janvier 2016 00:00"
'20160131':formatD('dddd') // "dimanche"
// With API options: {
//   "lang": "fr",
//   "timezone": "Europe/Paris"
// }
'20160131':formatD('dddd', 'YYYYMMDD') // "dimanche"
1410715640:formatD('LLLL', 'X') // "dimanche 14 septembre 2014 19:27"
// With API options: {
//   "lang": "fr",
//   "timezone": "Asia/Singapore"
// }
'20160131':formatD('dddd', 'YYYYMMDD') // "dimanche"
1410715640:formatD('LLLL', 'X') // "lundi 15 septembre 2014 01:27"
```

---

## :addD(amount, unit, patternIn)

Ajouter un temps à une date.

Unités disponibles : `day`, `week`, `month`, `quarter`, `year`, `hour`, `minute`, `second` et `millisecond`.

Les unités sont **insensibles à la casse** et supportent les formes **plurielles** et les **abréviations**.

### Paramètres

| Paramètre | Description | Type |
|---|---|---|
| `amount` | quantité | Number |
| `unit` | unité | String |
| `patternIn` | *(optionnel)* format d’entrée, **ISO 8601** par défaut | String |

### Exemples

```text
// With API options: {
//   "lang": "fr",
//   "timezone": "Europe/Paris"
// }
'2017-05-10T15:57:23.769561+03:00':addD('3', 'day') // "2017-05-13T12:57:23.769Z"
'2017-05-10 15:57:23.769561+03:00':addD('3', 'month') // "2017-08-10T12:57:23.769Z"
'20160131':addD('3', 'day') // "2016-02-03T00:00:00.000Z"
'20160131':addD('3', 'month') // "2016-04-30T00:00:00.000Z"
'31-2016-01':addD('3', 'month', 'DD-YYYY-MM') // "2016-04-30T00:00:00.000Z"
```

---

## :subD(amount, unit, patternIn)

Soustraire un temps à une date.

Unités disponibles : `day`, `week`, `month`, `quarter`, `year`, `hour`, `minute`, `second` et `millisecond`.

Les unités sont **insensibles à la casse** et supportent les formes **plurielles** et les **abréviations**.

### Paramètres

| Paramètre | Description | Type |
|---|---|---|
| `amount` | quantité | Number |
| `unit` | unité | String |
| `patternIn` | *(optionnel)* format d’entrée, **ISO 8601** par défaut | String |

### Exemples

```text
// With API options: {
//   "lang": "fr",
//   "timezone": "Europe/Paris"
// }
'2017-05-10T15:57:23.769561+03:00':subD('3', 'day') // "2017-05-07T12:57:23.769Z"
'2017-05-10 15:57:23.769561+03:00':subD('3', 'month') // "2017-02-10T12:57:23.769Z"
'20160131':subD('3', 'day') // "2016-01-28T00:00:00.000Z"
'20160131':subD('3', 'month') // "2015-10-31T00:00:00.000Z"
'31-2016-01':subD('3', 'month', 'DD-YYYY-MM') // "2015-10-31T00:00:00.000Z"
```

---

## :startOfD(unit, patternIn)

Créer une date et la positionner au **début** d’une unité de temps.

### Paramètres

| Paramètre | Description | Type |
|---|---|---|
| `unit` | unité | String |
| `patternIn` | *(optionnel)* format d’entrée, **ISO 8601** par défaut | String |

### Exemples

```text
// With API options: {
//   "lang": "fr",
//   "timezone": "Europe/Paris"
// }
'2017-05-10T15:57:23.769561+03:00':startOfD('day') // "2017-05-10T00:00:00.000Z"
'2017-05-10 15:57:23.769561+03:00':startOfD('month') // "2017-05-01T00:00:00.000Z"
'20160131':startOfD('day') // "2016-01-31T00:00:00.000Z"
'20160131':startOfD('month') // "2016-01-01T00:00:00.000Z"
'31-2016-01':startOfD('month', 'DD-YYYY-MM') // "2016-01-01T00:00:00.000Z"
```

---

## :endOfD(unit, patternIn)

Créer une date et la positionner à la **fin** d’une unité de temps.

### Paramètres

| Paramètre | Description | Type |
|---|---|---|
| `unit` | unité | String |
| `patternIn` | *(optionnel)* format d’entrée, **ISO 8601** par défaut | String |

### Exemples

```text
// With API options: {
//   "lang": "fr",
//   "timezone": "Europe/Paris"
// }
'2017-05-10T15:57:23.769561+03:00':endOfD('day') // "2017-05-10T23:59:59.999Z"
'2017-05-10 15:57:23.769561+03:00':endOfD('month') // "2017-05-31T23:59:59.999Z"
'20160131':endOfD('day') // "2016-01-31T23:59:59.999Z"
'20160131':endOfD('month') // "2016-01-31T23:59:59.999Z"
'31-2016-01':endOfD('month', 'DD-YYYY-MM') // "2016-01-31T23:59:59.999Z"
```

---

## :diffD(toDate, unit, patternFromDate, patternToDate)

Calculer la différence entre deux dates et obtenir un intervalle.

Liste des unités de sortie disponibles pour l’intervalle :

- `day(s)` ou `d` : jour de la semaine (dimanche = 0, samedi = 6)
- `week(s)` ou `w` : semaine de l’année
- `quarter(s)` ou `Q` : trimestre
- `month(s)` ou `M` : mois (janvier = 0, décembre = 11)
- `year(s)` ou `y` : année
- `hour(s)` ou `h` : heure
- `minute(s)` ou `m` : minute
- `second(s)` ou `s` : seconde
- `millisecond(s)` ou `ms` : milliseconde

### Paramètres

| Paramètre | Description | Type |
|---|---|---|
| `toDate` | date « to » | String, Number |
| `unit` | unité de sortie : day, week, ... (voir liste ci-dessus). **Millisecondes par défaut** | String |
| `patternFromDate` | *(optionnel)* pattern de `fromDate`, ISO8601 par défaut | String |
| `patternToDate` | *(optionnel)* pattern de `toDate`, ISO8601 par défaut | String |

### Exemples

```text
'20101001':diffD('20101201') // 5270400000
'20101001':diffD('20101201', 'second') // 5270400
'20101001':diffD('20101201', 's') // 5270400
'20101001':diffD('20101201', 'm') // 87840
'20101001':diffD('20101201', 'h') // 1464
'20101001':diffD('20101201', 'weeks') // 8
'20101001':diffD('20101201', 'days') // 61
'2010+10+01':diffD('2010=12=01', 'ms', 'YYYY+MM+DD', 'YYYY=MM=DD') // 5270400000
```

---

## Formats de date

| Format | Sortie | Description |
|---|---:|---|
| `X` | 1360013296 | timestamp Unix |
| `x` | 1360013296123 | timestamp Unix en millisecondes |
| `YY` | 18 | année sur 2 chiffres |
| `YYYY` | 2018 | année sur 4 chiffres |
| `M` | 1-12 | mois (à partir de 1) |
| `MM` | 01-12 | mois sur 2 chiffres |
| `MMM` | Jan-Dec | nom abrégé du mois |
| `MMMM` | January-December | nom complet du mois |
| `D` | 1-31 | jour du mois |
| `DD` | 01-31 | jour du mois sur 2 chiffres |
| `d` | 0-6 | jour de la semaine (dimanche = 0) |
| `dd` | Su-Sa | nom minimal du jour |
| `ddd` | Sun-Sat | nom court du jour |
| `dddd` | Sunday-Saturday | nom complet du jour |
| `H` | 0-23 | heure |
| `HH` | 00-23 | heure sur 2 chiffres |
| `h` | 1-12 | heure (format 12h) |
| `hh` | 01-12 | heure (12h) sur 2 chiffres |
| `m` | 0-59 | minute |
| `mm` | 00-59 | minute sur 2 chiffres |
| `s` | 0-59 | seconde |
| `ss` | 00-59 | seconde sur 2 chiffres |
| `SSS` | 000-999 | millisecondes sur 3 chiffres |
| `Z` | +05:00 | décalage UTC, ±HH:mm |
| `ZZ` | +0500 | décalage UTC, ±HHmm |
| `A` | AM PM | AM/PM |
| `a` | am pm | am/pm |
| `Q` | 1-4 | trimestre |
| `Do` | 1st 2nd ... 31st | jour du mois avec suffixe ordinal |
| `k` | 1-24 | heure (à partir de 1) |
| `kk` | 01-24 | heure (à partir de 1) sur 2 chiffres |
| `w` | 1 2 ... 52 53 | semaine de l’année |
| `ww` | 01 02 ... 52 53 | semaine de l’année sur 2 chiffres |
| `W` | 1 2 ... 52 53 | semaine ISO |
| `WW` | 01 02 ... 52 53 | semaine ISO sur 2 chiffres |
| `wo` | 1st 2nd ... 52nd 53rd | semaine avec suffixe ordinal |
| `gggg` | 2017 | année de semaine (Week Year) |
| `GGGG` | 2017 | année de semaine ISO |
| `z` | EST | offset nommé abrégé |
| `zzz` | Eastern Standard Time | offset nommé non abrégé |

### Liste des formats localisés

Comme les préférences de formatage diffèrent selon la langue, il existe des tokens permettant de formater une date selon la langue du rapport.

Il existe des variations en majuscule et minuscule pour un même format. La version minuscule est destinée à être la version abrégée de la version majuscule correspondante.

| Format | Anglais | Exemple de sortie (Locale) |
|---|---|---|
| `LT` | h:mm A | 8:02 PM |
| `LTS` | h:mm:ss A | 8:02:18 PM |
| `L` | MM/DD/YYYY | 08/16/2018 |
| `LL` | MMMM D, YYYY | August 16, 2018 |
| `LLL` | MMMM D, YYYY h:mm A | August 16, 2018 8:02 PM |
| `LLLL` | dddd, MMMM D, YYYY h:mm A | Thursday, August 16, 2018 8:02 PM |
| `l` | M/D/YYYY | 8/16/2018 |
| `ll` | MMM D, YYYY | Aug 16, 2018 |
| `lll` | MMM D, YYYY h:mm A | Aug 16, 2018 8:02 PM |
| `llll` | ddd, MMM D, YYYY h:mm A | Thu, Aug 16, 2018 8:02 PM |

Source : DayJS (day.js.org).

---

## Pour aller plus loin

-> [17 - Formatage des intervalles](17-formater-intervalles)
