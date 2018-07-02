# Using CoreNLP, d3.js, and dagre.js to visualize sentence parse trees

Posted on August 19, 2013
by bpodgursky

I’ve always been casually interested in the field of Natural Langauge Processing (NLP), a  field of computer science interested in extracting information from natural human language. I have no training or education whatsoever in the field so I’m not in a position to contribute much to the field, but I am definitely interested in seeing where the state of the art is, and in particular how powerful open-source NLP libraries have gotten (Google and Microsoft certainly have more powerful closed-source systems, but that doesn’t really help me.)

A few years ago I started playing with Apache’s OpenNLP project.  I’m a big fan of the Apache foundation and their libraries, but I found myself very frustrated by OpenNLP’s lack of documentation and the hacky-feeling interfaces the library exposed.  However recently I took another look at the available NLP libraries and came across Stanford’s CoreNLP project.   CoreNLP, as it turns out, is an awesome project, and it took almost zero effort to get their example demo working.

As a total NLP beginnner, the sentence parsing functionality was the most immediately approachable example.  Sentence parsing takes a natural-English sentence:

    “I am parsing an example sentence.”

and breaks it down into component tokens and their relations:

`    (ROOT1 (S (NP (PRP I)) (VP (VBP am) (VP (VBG parsing) (NP (DT an) (NN example) (NN sentence)))) (. .)))`

where each token type corresponds to a particular word type–“NP”  means “Noun Phrase”, VBG means “Verb, gerund or present participle”, and so forth (I’ve been referencing this as a complete token list.)

I’ve also been looking into JavaScript graph visualization libraries recently (I’ve struggled to find a JS library remotely as powerful and pretty as graphviz), and wanted to test out the dagre library, which re-implements a simplified dot algorithm in javascipt and can render the results to d3 (the current coolest-kid-on-the-block JS graph library).  So I put the two together and put together a simple visualization which uses dagre to show CoreNLP’s sentence parse tree.  It’s pretty simple, but you can play with it here.
