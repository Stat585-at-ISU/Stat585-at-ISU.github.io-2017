---
title: "A Layered Grammar of Graphics"
author: "Joe Papio"
topic: "03"
layout: post
root: ../../../
---

## How does having a grammar help with creating charts?

TL;DR: I'm thankful Hadley has spent so much time thinking about this topic so that we don't have to.

In language, grammar provides structure and roles to words, which taken together along with context and other nonverbal cues then convey meaning from the speaker to the listener. Even supposedly "simple" sentences can have deep underlying syntactical structures based on layers within the utterance, such that the same string of words spoken in one context by one individual with a certain set of intonations and pauses could convey an entirely different meaning than if that same string of words was uttered by another individual in a different context, whether the intonations and pauses were the same or not. What I found most fascinating studying linguistics was how (seemingly) easy it is for us to automatically detect and parse these layers of meaning, and without really putting much (if any) conscious thought into the process.

The grammar that Hadley describes in his article appears to work similarly in many ways. He takes the process of creating a plot and deconstructs it in to several simpler, easier to conceive pieces. In our respective native languages, once we understand the rules dictating how adjectives interact with nouns and then nouns interact with verbs, and so on and so forth, we can use those rules to combine the pieces together into an infinite set of possible strings, despite the rules which marginally constrain (at least in English), the order in which certain types of words can appear in relation to other types of words. (English and related languages often have a syntax that is based mostly in the ordering of the words, but other languages can and do involve other options for structure, such as tone or agglutination.) Likewise, after a basic understanding the grammar Hadley lays out, you can follow basic templates to build both simple and also relatively complex graphics. 

Much like a lexicon, Hadley's grammar also has some "words" which are about invoking meaning and other "words" which are essentially "meaningless", but which are necessary to maintain the structure. for example, the *+* doesn't convey any information in the vizualization, but it acts as connective tissue much in the way articles, prepositions, or conjunctions are the connective tissue between pairs of nouns or nouns and verbs, etc. These "function words" are often easily overlooked when they are present, but if someone breaks the rules of their usage, we tend to react negatively to their "unstructured" or "misstructured" utterances.

Outside of running the commands, the grammar is also nice in that it makes it easier for the coder (and any readers of his or her code) to easily see which components of the code are about building which components of the graphic, such that it is easier to see the relationship between the layers and the dataset (or datasets), and also the relationship between multiple layers. Having these relationships easily parseable also makes modifying the graphic much more straight forward.

When we learn our first language, we do much of the work of figuring out the grammar before we're old enough to realize or remember it. So, by the time we're really aware of using our language, the hard work of understanding the structure and rules has essentially been done for us (by our previous and unremembered selves). So much in the way I'm thankful that my pre-remembering self spent so much time thinking about English and figured out the grammar for speaking for me, I'm also thankful Hadley has spent so much time thinking about this topic so we don't have to.
