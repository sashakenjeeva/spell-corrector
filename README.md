# A context-sensitive, one-edit distance spelling corrector

Spelling correctors are now at an advanced stage: they are online (suggest word as you write it), and they also take into account the user's individual preferences. My project takes a step back, to the origins so to say, and focuses on the basic, behind-the-stage word correction process.
The project unfolds in several stages, from word-level correction to integrating context in the correction. 

Thus, the program starts by analysing the specific permutations that occur when mistyping a word, then gives a weighted candidate selection for typos, and finally selects the best based on the latter combined with the the word before and after (bigram language model). Throughout the report, I explain every step and the logic behind it.
The main idea behind this project is the so-called noisy channel model: the idea that a correct word has been put through a noisy channel that modified it (Jurafsky and Martin, 2020). Through the probability of a specific 'noise' (i.e., the probability of specific characters being mistyped as other characters), we'll get the intended word with highest probability. Then, we'll have to also integrate the absolute probability of a word occurring in a corpus (unigram) and of it occurring with the words around (bigrams).

So, ultimately my spelling corrector is able to do something like this:
"I walke to the suprmarket tody" --> "I walked to the supermarket today"
