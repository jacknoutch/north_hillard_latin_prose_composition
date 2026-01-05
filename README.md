# README: North & Hillard Latin Prose Composition

The transcribed document derives from [archive.org](https://archive.org/details/north-m.-hilladr-a.-latin-prose-composition-1913/page/n1/mode/1up).

## Description

### Special Vocabularies

`special_vocabularies.md` is a Markdown transcription of the Special Vocabularies at pages 204 to 238.

The Markdown file is organised by Exercise (a h2 heading) with a list of vocabulary items for each exercise in English, following by the Latin. The various notes are preserved, though errors in the text have been corrected where identified.

## Workflow

```
sed -i "s/^Exercise/## Exercise/" special_vocabularies.md
sed -i '/^[#]/b; /^[[:space:]]*$/b; s/^/- /' special_vocabularies.md
```

Replace "- - " with "- "

## Typing macrons and breves on a Windows machine

It's needed to type macrons and breves over all five vowels (and their capitals) to accurately transcribe the text. Copy and paste is too slow.

The simplest way to type such characters is to use Alt codes. Make sure Num lock is on. Holding down Alt, type the corresponding number for the character on the number pad.

However, Alt codes above 255 do not always work. The vowels with breves and macrons all have Alt codes over 255. They can be typed in Word, but not in Chrome, Edge, VS Code, etc.

My workaround is to use [AutoHotkey](https://www.autohotkey.com/) with the following script. This *still* doesn't work in VS Code with Markdown files (though it does with, e.g., txt files in VSC). This is because VSC seems to "steal" the keystrokes before AutoHotkey is able to register and replace them.

But this works enough for me to type in the browser and edit the files on Github.

```
#Requires AutoHotkey v2.0

:*?:a+::ă
:*?:a=::ā
:*?:e+::ĕ
:*?:e=::ē
:*?:i+::ĭ
:*?:i=::ī
:*?:o+::ŏ
:*?:o=::ō
:*?:u+::ŭ
:*?:u=::ū

:*?:A+::Ă
:*?:A=::Ā
:*?:E+::Ĕ
:*?:E=::Ē
:*?:I+::Ĭ
:*?:I=::Ī
:*?:O+::Ŏ
:*?:O=::Ō
:*?:U+::Ŭ
:*?:U=::Ū
```

### The Alt codes

For each vowel, there are four variations: Upper and lower case macron, Upper and lower case breve. These four variations are consecutive in both Unicode and the Alt code.

So, for `a` the Alt codes are `256 Ā`, `257 ā`, `258 Ă`, `259 ă`.

The first Alt code for each of the vowels' quartets is: 
- `a 256`
- `e 274`
- `i 298`
- `o 332`
- `u 362`

A fuller table (without capitals) is given below in a more readable format.

| name | graph | alt code | unicode |
|---|---|---|---|
| a breve | ă | 259 | U+0103 |
| a macron | ā | 257 | U+0101 |
| e breve | ĕ | 277 | U+0115 |
| e macron | ē | 275 | U+0113 |
| i breve | ĭ | 301 | U+012D |
| i macron | ī | 299 | U+012B |
| o breve | ŏ | 335 | U+014F |
| o macron | ō | 333 | U+014D |
| u breve | ŭ | 365 | U+016D |
| u macron | ū | 363 | U+016B |
