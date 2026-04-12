# Attention is all you need - Paper Notes

**Paper:** Vaswani et al., 2017  

**Why I read this:** First step in building my AI portfolio

## What problem did it solve?
The transformer replaced Recurrent Neural Network(RNNs) because they read words one at a time in a sequence manner this make it to forgot things from farback in a sentence. The transformer reads all the words simultaneously, making it faster and better at understanding long range relationships. 

## What is attention?
The transformer searches for the most relevant word to every other word. It measures relevance between all words and blends their meanings proportionally by those scores. 

## What are Q, K, V?
- Q (Query) - what a word is looking for
- K (Key) - what each word advertises to others
- V (Value) - the actual content passed on when attended to
Attention(Q, K, V) = softmax(QKᵀ / √dk) × V

Q × K          →  raw relevance scores
÷ √dk          →  stable scores
softmax        →  percentages (attention weights)
× V            →  final output (blended meaning)

## what is multi-head attention?
Attention runs 8 times in parallel, each head looking for different relationships - grammar, meaning, word order - then all findings are combined.

## How does it build a sentence?
1. Words become numbers
2. Position stamps are added so order is known 
3. Attention runs across all words * 6 layers
4. Each layer builds deeper understanding
5. Decoder generated output one word at a time

## Why did this paper matter?
It introduced one architecture that works for every language task and outperformed everything before it. Every major AI system today- GPT, Claude, Gemini, BERT- is built on this.

## What is positional encoding and how it works?
* The transformer reads all words at once so it has no sense of word order. 
* Positional encoding solves this by stamping each word with its position. 
* for example: word 1 gets stamp 1, word 2 gets stamp 2 and so on.
* Sine and cosine waves are used to create these stamps because they produce a unique number pair at every position. No two positionas gets the same pair.
* This stamp is added to the word's meaning vector before attention runs. So bythe time attentions starts, every word already know its plae in the sentence.
