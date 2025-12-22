---
title: "13 - Mise en forme de texte"
description: "Liste complète et utilisation des formatters de texte pour transformer des chaînes dans les templates"
date: "2025-11-20"
version: "1"
---

# Mise en forme de texte

Liste de fonctions pour manipuler et transformer vos chaînes JSON

---

## :lowerCase

Met toutes les lettres en minuscules.

### Exemples

```text
'My Car':lowerCase() // "my car"
'my car':lowerCase() // "my car"
null:lowerCase() // null
1203:lowerCase() // 1203
```

---
## :upperCase

Met toutes les lettres en majuscules.

### Exemples

```text
'My Car':upperCase() // "MY CAR"
'my car':upperCase() // "MY CAR"
null:upperCase() // null
1203:upperCase() // 1203
```

---
## :ucFirst

Met en majuscule la première lettre.

### Exemples

```text
'My Car':ucFirst() // "My Car"
'my car':ucFirst() // "My car"
null:ucFirst() // null
undefined:ucFirst() // undefined
1203:ucFirst() // 1203
```

---
## :ucWords

Met en majuscule la première lettre de chaque mot.

### Exemples

```text
'my car':ucWords() // "My Car"
'My cAR':ucWords() // "My CAR"
null:ucWords() // null
undefined:ucWords() // undefined
1203:ucWords() // 1203
```

---
## :print(message)

Retourne toujours le même message lorsqu’il est appelé (une sorte de formatter « catch all »).

### Paramètres

- `message` : texte à afficher (String)

### Exemples

```text
'My Car':print('hello!') // "hello!"
'my car':print('hello!') // "hello!"
null:print('hello!') // "hello!"
1203:print('hello!') // "hello!"
```

---
## :printJSON

Convertit (stringify) un objet / tableau en texte.

### Exemples

```text
[{'id':2,'name':'homer'},{'id':3,'name':'bart'}]:printJSON() // "[
  {"id": 2, "name": "homer"},
  {"id": 3, "name": "bart"}
]"
'my car':printJSON() // ""my car""
```

---
## :unaccent

Supprime les accents du texte.

### Exemples

```text
'crème brulée':unaccent() // "creme brulee"
'CRÈME BRULÉE':unaccent() // "CREME BRULEE"
'être':unaccent() // "etre"
'éùïêèà':unaccent() // "euieea"
```

---
## :convCRLF

Rend les retours chariot `\r\n` et les sauts de ligne `\n` *dans les documents*, au lieu de les afficher comme une chaîne.

### Notes importantes

- Fonction supportée pour les fichiers **DOCX, PPTX, ODT, ODP et ODS**.
- Le support **ODS** est expérimental pour le moment (contactez le support si vous constatez des problèmes).
- Depuis `v3.5.3`, utiliser `:convCRLF` avant `:html` convertit `\n` en balises `<br>`.  
  Exemple : `{d.content:convCRLF:html}`

### Exemples

```text
// With API options: {
//   "extension": "odt"
// }
'my blue 
 car':convCRLF() // "my blue <text:line-break/> car"
'my blue 
 car':convCRLF() // "my blue <text:line-break/> car"
// With API options: {
//   "extension": "docx"
// }
'my blue 
 car':convCRLF() // "my blue </w:t><w:br/><w:t xml:space="preserve"> car"
'my blue 
 car':convCRLF() // "my blue </w:t><w:br/><w:t xml:space="preserve"> car"
```

---
## :substr(begin, end, wordMode)

Découpe (slice) une chaîne entre un début et une fin.

### Paramètres

- `begin` : index (base 0) à partir duquel commencer l’extraction (Integer)
- `end` *(optionnel)* : index (base 0) avant lequel terminer l’extraction (Integer)
- `wordMode` *(optionnel)* : si `true`, ne coupe jamais les mots. Dans ce cas :
  - `end` doit être supérieur à `begin` et les valeurs négatives ne peuvent pas être utilisées. `end - begin` = nombre max de caractères par ligne.
  - Un mot ne peut être tronqué que s’il ne tient pas dans la ligne.
  - Le mot commence toujours au début d’une nouvelle ligne (comme dans Word ou LibreOffice).
  - La même largeur de ligne (`end - begin`) doit être utilisée entre des appels successifs de `substr` pour imprimer tous les mots du texte (sans trous). Ex :
    - `{d.text(0 , 50 , true)}` -> ligne 1 de 50 caractères
    - `{d.text(50 , 100, true)}` -> ligne 2 de 50 caractères
    - `{d.text(100, 150, true)}` -> ligne 3 de 50 caractères
    - `{d.text(150, 200, last)}` -> ligne 4 de largeur infinie
  - `last` peut être utilisé à la place de `true` pour imprimer le reste du texte, même s’il dépasse la largeur définie (Mixed)

### Exemples

```text
'foobar':substr(0, 3) // "foo"
'foobar':substr(1) // "oobar"
'foobar':substr(-2) // "ar"
'foobar':substr(2, -1) // "oba"
'abcd efg hijklm':substr(0, 11, true) // "abcd efg "
'abcd efg hijklm':substr(1, 11, true) // "abcd efg "
```

---
## :split(delimiter)

Découpe une chaîne avec un séparateur (delimiter).

Peut être utilisé avec `arrayJoin('', 1, 2)` pour sélectionner un élément spécifique du tableau généré.

### Paramètres

- `delimiter` : séparateur (String)

### Exemples

```text
'abcdefc12':split('c') // ["ab","def","12"]
1222.1:split('.') // ["1222","1"]
'ab/cd/ef':split('/') // ["ab","cd","ef"]
```

---
## :padl(targetLength, padString)

Complète (pad) la chaîne **au début** avec une autre chaîne.

### Paramètres

- `targetLength` : longueur de la chaîne résultante une fois complétée. Si la valeur est inférieure à la longueur de la chaîne, la chaîne est retournée telle quelle (number).
- `padString` : chaîne utilisée pour compléter. Si elle est trop longue pour respecter `targetLength`, elle est tronquée à partir de la fin. Valeur par défaut : `" "` (String)

### Exemples

```text
'abc':padl(10) // "       abc"
'abc':padl(10, 'foo') // "foofoofabc"
'abc':padl(6, '123465') // "123abc"
'abc':padl(8, '0') // "00000abc"
'abc':padl(1) // "abc"
```

---
## :padr(targetLength, padString)

Complète (pad) la chaîne **à la fin** avec une autre chaîne.

### Paramètres

- `targetLength` : longueur de la chaîne résultante une fois complétée. Si la valeur est inférieure à la longueur de la chaîne, la chaîne est retournée telle quelle (number).
- `padString` : chaîne utilisée pour compléter. Si elle est trop longue pour respecter `targetLength`, elle est tronquée à partir de la fin. Valeur par défaut : `" "` (String)

### Exemples

```text
'abc':padr(10) // "abc       "
'abc':padr(10, 'foo') // "abcfoofoof"
'abc':padr(6, '123465') // "abc123"
'abc':padr(8, '0') // "abc00000"
'abc':padr(1) // "abc"
```

---
## :ellipsis(maximum)

Ajoute `"..."` si le texte est trop long.

### Paramètres

- `maximum` : nombre maximum de caractères à afficher (Integer)

### Exemples

```text
'abcdef':ellipsis(3) // "abc..."
'abcdef':ellipsis(6) // "abcdef"
'abcdef':ellipsis(10) // "abcdef"
```

---
## :prepend(textToPrepend)

Ajoute un préfixe à un texte.

### Paramètres

- `textToPrepend` : texte à préfixer (string)

### Exemples

```text
'abcdef':prepend('123') // "123abcdef"
```

---
## :append(textToAppend)

Ajoute un suffixe à un texte.

### Paramètres

- `textToAppend` : texte à suffixer (string)

### Exemples

```text
'abcdef':append('123') // "abcdef123"
```

---
## :replace(oldText, newText)

Remplace un texte selon un motif (pattern).

Tous les matchs du motif (premier argument : `oldText`) sont remplacés par la chaîne de remplacement (second argument : `newText`).
Le motif ne peut être qu’une chaîne.

### Paramètres

- `oldText` : ancien texte à remplacer (string)
- `newText` : nouveau texte (string)

### Exemples

```text
'abcdef abcde':replace('cd', 'OK') // "abOKef abOKe"
'abcdef abcde':replace('cd') // "abef abe"
'abcdef abcde':replace('cd', null) // "abef abe"
'abcdef abcde':replace('cd', 1000) // "ab1000ef ab1000e"
```

---
## :len

Retourne la longueur d’une chaîne ou d’un tableau.

### Exemples

```text
'Hello World':len() // 11
'':len() // 0
[1,2,3,4,5]:len() // 5
[1,'Hello']:len() // 2
```

---

## :t

Traduit le texte à l’aide du dictionnaire de traduction.

---
## :preserveCharRef

Préserve les références de caractères.

Par défaut, la plateforme supprime tous les caractères interdits avant d’injecter les données dans du XML (ex. `&`, `>`, `<`, `�`, ...).  
Par conséquent, une référence de caractère injectée telle que `&#xa7;` ( = `§` ) serait transformée en `&amp;#xa7;` dans le XML.

Ce formatter empêche cette transformation et préserve la référence de caractère.

Ce formatter est utile pour certains scénarios spécifiques de génération XML où le caractère direct ne peut pas être utilisé (ex. encodage non UTF-8),  
et où la référence de caractère doit être conservée.

Il accepte les formats numériques (ex. `&#100;`) et hexadécimaux (ex. `&#xa10ef;`), en minuscules ou majuscules.

---
## :formatR

Formate un code pays/région en un nom de région lisible.

### Exemples

```text
// With API options: {
//   "lang": "en-us"
// }
'US':formatR() // "United States"
'DE':formatR() // "Germany"
'FRA':formatR() // "France"
'250':formatR() // "France"
'276':formatR() // "Germany"
// With API options: {
//   "lang": "fr-fr"
// }
'US':formatR() // "États-Unis"
'DE':formatR() // "Allemagne"
'FRA':formatR() // "France"
'250':formatR() // "France"
'276':formatR() // "Allemagne"
```
---
## Pour aller plus loin

-> [14 - Formatage des nombres](14-formatage-des-nombres)
