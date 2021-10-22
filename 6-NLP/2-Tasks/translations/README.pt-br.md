# Técnicas e tarefas frequentes do Processamento de Linguagem Natural

Para a maioria das tarefas de *processamento de linguagem natural*, o texto a ser processado precisa ser quebrado em partes, examinado, e os resultados guardados ou cruzados com regras e data sets. Estas tarefas permitem que o programador obtenha _significado_ ou _intencionalidade_ ou a _frequência_ de termos e palavras em um texto.

## [Quiz pré-aula](https://white-water-09ec41f0f.azurestaticapps.net/quiz/33?loc=br)

Vamos descobrir técnicas frequentemente usadas no processamento de texto. Combinadas com aprendizado de máquina, estas técnicas ajudam você a analisar grandes quantidades de texto com eficiência. Contudo, antes de aplicar o aprendizado de máquina para estas tarefas, vamos entender os problemas encontrados por um especialista de PLN (ou NLP, em inglês).

## Tarefas frequentes para o PLN

Existem diferentes formas de analisar um texto em que você está trabalhando. Existem tarefas que você pode executar e através destas você pode obter um entendimento melhor do texto e chegar a conclusões. Você geralment realiza estas tarefas em sequência.

### Tokenização

Provavelmente a primeira coisa que a maioria dos algoritmos de PLN precisa é fazer um split (quebra) do texto em tokens, ou palavras. Apesar de parecer simples, levar em consideração pontuação e delimitadores de palavras e orações de diferentes linguagens pode ser trabalhoso. Você pode ter que usar vários métodos para determinar delimitadores.

![tokenização](../images/tokenization.png)
> Tokenizando uma frase de **Orgulho e preconceito**. Infográfico por [Jen Looper](https://twitter.com/jenlooper)

### Embeddings

[Word embeddings](https://wikipedia.org/wiki/Word_embedding) are a way to convert your text data numerically. Embeddings are done in a way so that words with a similar meaning or words used together cluster together.

![word embeddings](images/embedding.png)
> "I have the highest respect for your nerves, they are my old friends." - Word embeddings for a sentence in **Pride and Prejudice**. Infographic by [Jen Looper](https://twitter.com/jenlooper)

✅ Try [this interesting tool](https://projector.tensorflow.org/) to experiment with word embeddings. Clicking on one word shows clusters of similar words: 'toy' clusters with 'disney', 'lego', 'playstation', and 'console'.

### Parsing & Part-of-speech Tagging

Every word that has been tokenized can be tagged as a part of speech - a noun, verb, or adjective. The sentence `the quick red fox jumped over the lazy brown dog` might be POS tagged as fox = noun, jumped = verb.

![parsing](images/parse.png)

> Parsing a sentence from **Pride and Prejudice**. Infographic by [Jen Looper](https://twitter.com/jenlooper)

Parsing is recognizing what words are related to each other in a sentence - for instance `the quick red fox jumped` is an adjective-noun-verb sequence that is separate from the `lazy brown dog` sequence.  

### Word and Phrase Frequencies

A useful procedure when analyzing a large body of text is to build a dictionary of every word or phrase of interest and how often it appears. The phrase `the quick red fox jumped over the lazy brown dog` has a word frequency of 2 for the.

Let's look at an example text where we count the frequency of words. Rudyard Kipling's poem The Winners contains the following verse:

```output
What the moral? Who rides may read.
When the night is thick and the tracks are blind
A friend at a pinch is a friend, indeed,
But a fool to wait for the laggard behind.
Down to Gehenna or up to the Throne,
He travels the fastest who travels alone.
```

As phrase frequencies can be case insensitive or case sensitive as required, the phrase `a friend` has a frequency of 2 and `the` has a frequency of 6, and `travels` is 2.

### N-grams

A text can be split into sequences of words of a set length, a single word (unigram), two words (bigrams), three words (trigrams) or any number of words (n-grams).

For instance `the quick red fox jumped over the lazy brown dog` with a n-gram score of 2 produces the following n-grams:

1. the quick 
2. quick red 
3. red fox
4. fox jumped 
5. jumped over 
6. over the 
7. the lazy 
8. lazy brown 
9. brown dog

It might be easier to visualize it as a sliding box over the sentence. Here it is for n-grams of 3 words, the n-gram is in bold in each sentence:

1.   <u>**the quick red**</u> fox jumped over the lazy brown dog
2.   the **<u>quick red fox</u>** jumped over the lazy brown dog
3.   the quick **<u>red fox jumped</u>** over the lazy brown dog
4.   the quick red **<u>fox jumped over</u>** the lazy brown dog
5.   the quick red fox **<u>jumped over the</u>** lazy brown dog
6.   the quick red fox jumped **<u>over the lazy</u>** brown dog
7.   the quick red fox jumped over <u>**the lazy brown**</u> dog
8.   the quick red fox jumped over the **<u>lazy brown dog</u>**

![n-grams sliding window](images/n-grams.gif)

> N-gram value of 3: Infographic by [Jen Looper](https://twitter.com/jenlooper)

### Noun phrase Extraction

In most sentences, there is a noun that is the subject, or object of the sentence. In English, it is often identifiable as having 'a' or 'an' or 'the' preceding it. Identifying the subject or object of a sentence by 'extracting the noun phrase' is a common task in NLP when attempting to understand the meaning of a sentence.

✅ In the sentence "I cannot fix on the hour, or the spot, or the look or the words, which laid the foundation. It is too long ago. I was in the middle before I knew that I had begun.", can you identify the noun phrases?

In the sentence `the quick red fox jumped over the lazy brown dog` there are 2 noun phrases: **quick red fox** and **lazy brown dog**.

### Sentiment analysis

A sentence or text can be analysed for sentiment, or how *positive* or *negative* it is. Sentiment is measured in *polarity* and *objectivity/subjectivity*. Polarity is measured from -1.0 to 1.0 (negative to positive) and 0.0 to 1.0 (most objective to most subjective).

✅ Later you'll learn that there are different ways to determine sentiment using machine learning, but one way is to have a list of words and phrases that are categorized as positive or negative by a human expert and apply that model to text to calculate a polarity score. Can you see how this would work in some circumstances and less well in others?

### Inflection

Inflection enables you to take a word and get the singular or plural of the word.

### Lemmatization

A *lemma* is the root or headword for a set of words, for instance *flew*, *flies*, *flying* have a lemma of the verb *fly*.

There are also useful databases available for the NLP researcher, notably:

### WordNet

[WordNet](https://wordnet.princeton.edu/) is a database of words, synonyms, antonyms and many other details for every word in many different languages. It is incredibly useful when attempting to build translations, spell checkers, or language tools of any type.

## NLP Libraries

Luckily, you don't have to build all of these techniques yourself, as there are excellent Python libraries available that make it much more accessible to developers who aren't specialized in natural language processing or machine learning. The next lessons include more examples of these, but here you will learn some useful examples to help you with the next task.

### Exercise - using `TextBlob` library

Let's use a library called TextBlob as it contains helpful APIs for tackling these types of tasks. TextBlob "stands on the giant shoulders of [NLTK](https://nltk.org) and [pattern](https://github.com/clips/pattern), and plays nicely with both." It has a considerable amount of ML embedded in its API.

> Note: A useful [Quick Start](https://textblob.readthedocs.io/en/dev/quickstart.html#quickstart) guide is available for TextBlob that is recommended for experienced Python developers 

When attempting to identify *noun phrases*, TextBlob offers several options of extractors to find noun phrases. 

1. Take a look at `ConllExtractor`.

    ```python
    from textblob import TextBlob
    from textblob.np_extractors import ConllExtractor
    # import and create a Conll extractor to use later 
    extractor = ConllExtractor()
    
    # later when you need a noun phrase extractor:
    user_input = input("> ")
    user_input_blob = TextBlob(user_input, np_extractor=extractor)  # note non-default extractor specified
    np = user_input_blob.noun_phrases                                    
    ```

    > What's going on here? [ConllExtractor](https://textblob.readthedocs.io/en/dev/api_reference.html?highlight=Conll#textblob.en.np_extractors.ConllExtractor) is "A noun phrase extractor that uses chunk parsing trained with the ConLL-2000 training corpus." ConLL-2000 refers to the 2000 Conference on Computational Natural Language Learning. Each year the conference hosted a workshop to tackle a thorny NLP problem, and in 2000 it was noun chunking. A model was trained on the Wall Street Journal, with "sections 15-18 as training data (211727 tokens) and section 20 as test data (47377 tokens)". You can look at the procedures used [here](https://www.clips.uantwerpen.be/conll2000/chunking/) and the [results](https://ifarm.nl/erikt/research/np-chunking.html).

### Challenge - improving your bot with NLP

In the previous lesson you built a very simple Q&A bot. Now, you'll make Marvin a bit more sympathetic by analyzing your input for sentiment and printing out a response to match the sentiment. You'll also need to identify a `noun_phrase` and ask about it.

Your steps when building a better conversational bot:

1. Print instructions advising the user how to interact with the bot
2. Start loop 
   1. Accept user input
   2. If user has asked to exit, then exit
   3. Process user input and determine appropriate sentiment response
   4. If a noun phrase is detected in the sentiment, pluralize it and ask for more input on that topic
   5. Print response
3. loop back to step 2

Here is the code snippet to determine sentiment using TextBlob. Note there are only four *gradients* of sentiment response (you could have more if you like):

```python
if user_input_blob.polarity <= -0.5:
  response = "Oh dear, that sounds bad. "
elif user_input_blob.polarity <= 0:
  response = "Hmm, that's not great. "
elif user_input_blob.polarity <= 0.5:
  response = "Well, that sounds positive. "
elif user_input_blob.polarity <= 1:
  response = "Wow, that sounds great. "
```

Here is some sample output to guide you (user input is on the lines with starting with >):

```output
Hello, I am Marvin, the friendly robot.
You can end this conversation at any time by typing 'bye'
After typing each answer, press 'enter'
How are you today?
> I am ok
Well, that sounds positive. Can you tell me more?
> I went for a walk and saw a lovely cat
Well, that sounds positive. Can you tell me more about lovely cats?
> cats are the best. But I also have a cool dog
Wow, that sounds great. Can you tell me more about cool dogs?
> I have an old hounddog but he is sick
Hmm, that's not great. Can you tell me more about old hounddogs?
> bye
It was nice talking to you, goodbye!
```

One possible solution to the task is [here](solution/bot.py)

✅ Knowledge Check

1. Do you think the sympathetic responses would 'trick' someone into thinking that the bot actually understood them?
2. Does identifying the noun phrase make the bot more 'believable'?
3. Why would extracting a 'noun phrase' from a sentence a useful thing to do?

---

Implement the bot in the prior knowledge check and test it on a friend. Can it trick them? Can you make your bot more 'believable?'

## 🚀Challenge

Take a task in the prior knowledge check and try to implement it. Test the bot on a friend. Can it trick them? Can you make your bot more 'believable?'

## [Post-lecture quiz](https://white-water-09ec41f0f.azurestaticapps.net/quiz/34/)

## Review & Self Study

In the next few lessons you will learn more about sentiment analysis. Research this interesting technique in articles such as these on [KDNuggets](https://www.kdnuggets.com/tag/nlp)

## Assignment 

[Make a bot talk back](assignment.md)
