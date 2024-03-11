# BibleGateway API

An API that scrapes BibleGateway to get both daily verses and scripture.

## Installation

> **Note**
> I use `pnpm` in these examples. `npm` will also work if you don't have or want to install `pnpm`

First step is of course installing the module

```bash
pnpm install @glowstudent/biblegateway
```

## Usage

#### Import the library

```ts
import { getVerse } from '@glowstudent/biblegateway';
```

#### Getting the verse of the day:


```ts
import { getVerse } from '@glowstudent/biblegateway';;

  console.log(await getVerseOfTheDay());
```

```json
{
  "citation": "Hebrews 11:1 (NIV)",
  "passage": "Now faith is confidence in what we hope for and assurance about what we do not see."
}
```

#### Getting any verse:

```ts
import { getVerse } from '@glowstudent/biblegateway';

console.log(await getVerse('Luke', '9:55', 'NLT'))
```
```json
{
  "citation": "Luke 9:55 NLT",
  "passage": "But Jesus turned and rebuked them.",
  "footnotes": "9:55 Some manuscripts add an expanded conclusion to verse 55 and an additional sentence in verse 56: And he said, “You don’t realize what your hearts are like. 56 For the Son of Man has not come to destroy people’s lives, but to save them.”",
}
```

or alternatively..

```ts
import { getVerse } from '@glowstudent/biblegateway';

getVerse('Psalms', '22:9-10', 'NIV').then(result => console.log(result));
```

```json
{
  "citation": "Psalms 22:9-10 NIV",
  "passage": "Yet you brought me out of the womb; you made me trust in you, even at my mother’s breast. From birth I was cast on you; from my mother’s womb you have been my God.",
}
```

---

## Responses

Requests return a JSON object and a status code.

### Good Respsonses

Good responses will return a JSON with a `citation` and a `passage`.

```json
{
  "citation": "John 3:16 NLT",
  "passage": "For this is how God loved the world: He gave his one and only Son, so that everyone who believes in him will not perish but have eternal life"
}
```

### Bad Responses

Trying to access a passage that does not exist will prompt an error message

```json
{
  "code": 400,
  "message": "Could not find passage Script 9:99 NLT",
}

```


# Versions

Checkout https://www.biblegateway.com/versions/

## Links

- [GitHub](https://github.com/@glowstudent/BibleGateway-API-NPM)
- [npm](https://www.npmjs.com/package/@glowstudent/biblegateway)
- [Discord](https://discord.gg/4wM63P7ZUd)

## Credits

Thanks to [@cvyx](https://github.com/cvyx) for their PR that prompted the creation of this new repo.

## Contributing

Before creating an issue, please ensure that it hasn't already been reported/suggested.

## License

This project is licensed under the terms of the
[Apache 2.0 license](/LICENSE).
