# Markov In Inefficient JS

View `public_index.html` for a sample.

These chains are generated with two independent dictionaries of 2-grams and 3-grams. 
Sentences are split into words and these words are used to index the following words. 
For instance, the following sentences:

> to be or not to be
> that is the question

...would be recategorized as:

```
to: ['be', 'be']
be: ['or']
or: ['not']
not: ['to']
that: ['is']
...etc
```

Note that the duplicated `be`'s are intentional; a random index in the `to` array
can then be used to pick a next word, weighted for probability.

3-grams are indexed as:

```
'to be': ['or']
'be or': ['not']
...etc
```

and so on.

It's horribly inefficient, but... So sue me.

More information [here](http://blog.jordan.matelsky.com/markov/).
