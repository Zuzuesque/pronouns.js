# Understanding `pronouns.js`

**`pronouns` is a function that has its own properties as well.**

Calling `pronouns('he')`, for example, will return the following object:

```js
{
  pronouns: [ [ 'he', 'him', 'his', 'his', 'himself' ] ],
  sub: 'he',
  subject: 'he',
  obj: 'him',
  object: 'him',
  det: 'his',
  determiner: 'his',
  pos: 'his',
  possessive: 'his',
  ref: 'himself',
  reflexive: 'himself',
  examples: [
    [
      'He went to the park.',
      'I went with him.',
      'He brought his frisbee.',
      'At least I think it was his.',
      'He threw the frisbee to himself.'
    ]
  ],
  toString: [Function: () => String],
  toUrl: [Function: () => String]
}
```

Let's go through each one...

### `pronouns`

An array containing arrays of length 5. There is one row for each "or"-separated pronoun given in the input string.

### `subject`, `object`, `determiner`, `possessive`, and `reflexive`

There are 5 forms for each pronoun in a row:

subject|object|possessive determiner|possessive pronoun|reflexive
-------|------|---------------------|------------------|---------
he     | him  | his                 | his              | himself

This wiki is not an English lesson, so please look these up if you are confused. The three letter abbreviations are aliases so you can keep your code a bit more concise.

### `examples`

This is an array of examples of each pronoun form. Sample sentences taken from the [original code](https://github.com/witch-house/pronoun.is/blob/master/src/pronouns/pages.clj#L46).

### `toString()`

Returns a human-readable string that can also be used as an input to get an identical object back.

### `toUrl()`

Returns a link to the [pronoun.is/](https://pronoun.is/) page corresponding to the object. These are formatted slightly differently than `toString()`.

---

Lastly, `pronouns` has some properties that can be accessed without calling any functions.

### `pronouns.table`

This is the complete table in JSON format. It's the same one located in [resources/pronouns.json](resources/pronouns.json).

### `pronouns.abbreviated`

This is an abbreviated table containing the shortest unambiguous path to get to each row.

### `pronouns.util`

The `util` object is exposed in case you want to use it, though most users will not need to. Most of its methods are for accessing and formatting rows from a table. Its source is located in [src/util.js](src/util.js).