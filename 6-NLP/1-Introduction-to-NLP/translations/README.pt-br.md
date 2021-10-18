# Introdução ao Processamento de Linguagem Natural

Esta aula cobre uma breve história e conceitos importantes do *processamento de linguagem natural*, uma subárea da *Linguística computacional*.

## [Quiz pŕe-aula](https://white-water-09ec41f0f.azurestaticapps.net/quiz/31/)

## Introdução

PLN (ou, em inglês NLP), como é geralmente conhecido, é uma das áreas mais conhecidas onde o aprendizado de máquina (machine learning) tem sido aplicado e usado na produção de software.

✅ Você consegue pensar em algum software que você usa todo dia que provavelmente tem algum PLN integrado? E programas de processamento de palavras e aplicativos mobile que você usa com frequência?

Você vai aprender sobre:

- **A ideia das linguagens**. Como as linguagens se desenvolveram e quais as maiores áreas de estudo têm sido.
- **Definição e conceitos**. Você também vai aprender definições e conceitos sobre como os computadores processam texto, incluindo análise sintática (parsing), gramática, e identificação de substantivos e verbos. Existem algumas tarefas de programação nesta aula, e muitos conceitos importantes serão introduzidos, que você ira aprender a programar nas próximas aulas.

## Linguística computacional

Linguística computacional é uma área de pesquisa e desenvolvimento ao longo de várias décadas que estuda como computadores podem trabalhar com, e até entender, traduzir, e comunicar com linguagens. Processamento de linguagem natural (PLN) é um campo correlato que tem o foco em como computadores podem processar linguagens 'naturais' ou humanas.

### Exemplo - transcrição de voz no celular

Se você já usou o recurso de digitação por voz ao invés de escrever ou fez uma pergunta para uma assistente virtual, sua fala foi convertida para o formato textual e então processou ou *parseou* (analisou a sintaxe) da linguagem que você falou. As palavras-chave detectadas então são processadas em um formato que o celular ou o assistente possa entender e agir.

![compreensão](../images/comprehension.png)
> Compreensão de linguagem de verdade é difícil! Imagem por [Jen Looper](https://twitter.com/jenlooper)
> Tradução:
   > Mulher: Mas o que você quer? Frango? Peixe? Patê?
   > Gato: Miau

### Como essa tecnologia é possível?

Ela é possível porque alguém escreveu um programa de computador para fazer isto. Algumas décadas atrás, escritores de ficção previram que as pessoas iriam falar principalmente com seus computadores, e que computadores sempre iriam entender exatamente o que eles queriam dizer. Infelizmente, isto mostrou-se mais difícil do que muitos imaginavam, e enquanto hoje é um problema muito melhor compreendido, existem desafios significantes em alcançar o processamento de linguagem natural 'perfeito' quando pensamos em entender o significado de uma frase/expressão. Este é um problema particularmente difícil quando é preciso entender humor ou detectar emoções como sarcasmo em uma frase.

At this point, you may be remembering school classes where the teacher covered the parts of grammar in a sentence. In some countries, students are taught grammar and linguistics as a dedicated subject, but in many, these topics are included as part of learning a language: either your first language in primary school (learning to read and write) and perhaps a second language in post-primary, or high school. Don't  worry if you are not an expert at differentiating nouns from verbs or adverbs from adjectives!

If you struggle with the difference between the *simple present* and *present progressive*, you are not alone. This is a challenging thing for many people, even native speakers of a language. The good news is that computers are really good at applying formal rules, and you will learn to write code that can *parse* a sentence as well as a human. The greater challenge you will examine later is understanding the *meaning*, and *sentiment*, of a sentence.

## Prerequisites

For this lesson, the main prerequisite is being able to read and understand the language of this lesson. There are no math problems or equations to solve. While the original author wrote this lesson in English, it is also translated into other languages, so you could be reading a translation. There are examples where a number of different languages are used (to compare the different grammar rules of different languages). These are *not* translated, but the explanatory text is, so the meaning should be clear.

For the coding tasks, you will use Python and the examples are using Python 3.8.

In this section, you will need, and use:

- **Python 3 comprehension**.  Programming language comprehension in Python 3, this lesson uses input, loops, file reading, arrays.
- **Visual Studio Code + extension**. We will use Visual Studio Code and its Python extension. You can also use a Python IDE of your choice.
- **TextBlob**. [TextBlob](https://github.com/sloria/TextBlob) is a simplified text processing library for Python. Follow the instructions on the TextBlob site to install it on your system (install the corpora as well, as shown below):

   ```bash
   pip install -U textblob
   python -m textblob.download_corpora
   ```

> 💡 Tip: You can run Python directly in VS Code environments. Check the [docs](https://code.visualstudio.com/docs/languages/python?WT.mc_id=academic-15963-cxa) for more information.

## Talking to machines

The history of trying to make computers understand human language goes back decades, and one of the earliest scientists to consider natural language processing was *Alan Turing*.

### The 'Turing test'

When Turing was researching *artificial intelligence* in the 1950's, he considered if a conversational test could be given to a human and computer (via typed correspondence) where the human in the conversation was not sure if they were conversing with another human or a computer.

If, after a certain length of conversation, the human could not determine that the answers were from a computer or not, then could the computer be said to be *thinking*?

### The inspiration - 'the imitation game'

The idea for this came from a party game called *The Imitation Game* where an interrogator is alone in a room and tasked with determining which of two people (in another room) are male and female respectively. The interrogator can send notes, and must try to think of questions where the written answers reveal the gender of the mystery person. Of course, the players in the other room are trying to trick the interrogator by answering questions in such as way as to mislead or confuse the interrogator, whilst also giving the appearance of answering honestly.

### Developing Eliza

In the 1960's an MIT scientist called *Joseph Weizenbaum* developed [*Eliza*](https://wikipedia.org/wiki/ELIZA), a computer 'therapist' that would ask the human questions and give the appearance of understanding their answers. However, while Eliza could parse a sentence and identify certain grammatical constructs and keywords so as to give a reasonable answer, it could not be said to *understand* the sentence. If Eliza was presented with a sentence following the format "**I am** <u>sad</u>" it might rearrange and substitute words in the sentence to form the response "How long have **you been** <u>sad</u>". 

This gave the impression that Eliza understood the statement and was asking a follow-on question, whereas in reality, it was changing the tense and adding some words. If Eliza could not identify a keyword that it had a response for, it would instead give a random response that could be applicable to many different statements. Eliza could be easily tricked, for instance if a user wrote "**You are** a <u>bicycle</u>" it might respond with "How long have **I been** a <u>bicycle</u>?", instead of a more reasoned response.

[![Chatting with Eliza](https://img.youtube.com/vi/RMK9AphfLco/0.jpg)](https://youtu.be/RMK9AphfLco "Chatting with Eliza")

> 🎥 Click the image above for a video about original ELIZA program

> Note: You can read the original description of [Eliza](https://cacm.acm.org/magazines/1966/1/13317-elizaa-computer-program-for-the-study-of-natural-language-communication-between-man-and-machine/abstract) published in 1966 if you have an ACM account. Alternately, read about Eliza on [wikipedia](https://wikipedia.org/wiki/ELIZA)

## Exercise - coding a basic conversational bot

A conversational bot, like Eliza, is a program that elicits user input and seems to understand and respond intelligently. Unlike Eliza, our bot will not have several rules giving it the appearance of having an intelligent conversation. Instead, our bot will have one ability only, to keep the conversation going with random responses that might work in almost any trivial conversation.

### The plan

Your steps when building a conversational bot:

1. Print instructions advising the user how to interact with the bot
2. Start a loop
   1. Accept user input
   2. If user has asked to exit, then exit
   3. Process user input and determine response (in this case, the response is a random choice from a list of possible generic responses)
   4. Print response
3. loop back to step 2

### Building the bot

Let's create the bot next. We'll start by defining some phrases.

1. Create this bot yourself in Python with the following random responses:

    ```python
    random_responses = ["That is quite interesting, please tell me more.",
                        "I see. Do go on.",
                        "Why do you say that?",
                        "Funny weather we've been having, isn't it?",
                        "Let's change the subject.",
                        "Did you catch the game last night?"]
    ```

    Here is some sample output to guide you (user input is on the lines starting with `>`):

    ```output
    Hello, I am Marvin, the simple robot.
    You can end this conversation at any time by typing 'bye'
    After typing each answer, press 'enter'
    How are you today?
    > I am good thanks
    That is quite interesting, please tell me more.
    > today I went for a walk     
    Did you catch the game last night?
    > I did, but my team lost
    Funny weather we've been having, isn't it?
    > yes but I hope next week is better
    Let's change the subject.
    > ok, lets talk about music
    Why do you say that?
    > because I like music!
    Why do you say that?
    > bye
    It was nice talking to you, goodbye!
    ```

    One possible solution to the task is [here](solution/bot.py)

    ✅ Stop and consider

    1. Do you think the random responses would 'trick' someone into thinking that the bot actually understood them?
    2. What features would the bot need to be more effective?
    3. If a bot could really 'understand' the meaning of a sentence, would it need to 'remember' the meaning of previous sentences in a conversation too?

---

## 🚀Challenge

Choose one of the "stop and consider" elements above and either try to implement them in code or write a solution on paper using pseudocode.

In the next lesson, you'll learn about a number of other approaches to parsing natural language and machine learning.

## [Post-lecture quiz](https://white-water-09ec41f0f.azurestaticapps.net/quiz/32/)

## Review & Self Study

Take a look at the references below as further reading opportunities.

### References

1. Schubert, Lenhart, "Computational Linguistics", *The Stanford Encyclopedia of Philosophy* (Spring 2020 Edition), Edward N. Zalta (ed.), URL = <https://plato.stanford.edu/archives/spr2020/entries/computational-linguistics/>.
2. Princeton University "About WordNet." [WordNet](https://wordnet.princeton.edu/). Princeton University. 2010. 

## Assignment 

[Search for a bot](assignment.md)
