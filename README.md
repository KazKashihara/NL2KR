# NL2KR

[NL2KR](http://bioai.lab.asu.edu/nl2kr/) is a semi-automated semantic parsing platform and it has two sub-parts which depends on each other (1) NL2KR-L for learning and (2) NL2KR-T for translating.   

The NL2KR-L takes an initial lexicon consisting of some words and their meanings in terms of lambda-calculus expressions, a set of training sentences and their target formal representations as input. It then uses a Combinatorial Categorical Grammar (CCG) parser to construct the parse trees. Next, the learning sub-part of the system uses Inverse-λ and Generalization algorithms to learn meanings of newly encountered words, which are not present in the initial lexicon, and adds them to the lexicon. A parameter learning method is then used to estimate a weight for each lexicon entry (word, its syntactic category and meaning) such that the joint probability of the sentences in the training set getting translated to their given formal representation is maximized. 

The result of NL2KR-L is the final lexicon, which contains all the words, their meanings and their weights.   Once the training component finishes its job, the translation component (NL2KR-T) uses this updated lexicon and translates sentences using the CCG parser. Since words can have multiple meanings and their associated λ-calculus expressions, weights assigned to each lexical entry in the lexicon helps in deciding more likely meaning of a word in the context of a sentence.     


Publications related to NL2KR (New to Old):
1. Vo Nguyen, Arindam Mitra and Chitta Baral. The NL2KR platform for building Natural Language Translation Systems. ACL 2015. 

2. Shruti Gaur, Nguyen H. Vo, Kazuaki Kashihara, and Chitta Baral. Translating Simple Legal Text to Formal Representations. In New Frontiers in Artificial Intelligence (JSAI-isAI 2014 Workshops, LENLS, JURISIN, and GABA, Kanagawa, Japan, November 23-24, 2014, Revised Selected Papers). Edited by: Tsuyoshi Murata, Koji Mineshima, Daisuke Bekki. 2015. 

3. Baral, C., Dzifcak, J., Kumbhare, K., & Vo, N. H. (2013). The NL2KR system. Language Processing and Automated Reasoning (NLPAR), 2013.


The Generalization algorithm used in NL2KR generates the meanings of missing words by applying missing words. 
The enhanced Generalization algorithm uses the semantically similar words of the missing word and apply the templates of these words to generate the missing word’s meanings.
This enhanced algorithm improves the accuracy with the smaller learned lexicons than the original Generalization.

In addition, NL2KR can extend from English to other languages that have the CCG parser.
We implement a Japanese CCG parser to NL2KR system to adjust Japanese (JNL2KR) and applied the enhanced Generalization algorithm to NL2KR and JNL2KR.

[Download NL2KR with Glove](https://drive.google.com/file/d/1OYHpZdo75UP93RlvQiA9CYQYEUVdQTHx/view?usp=sharing)

[Download NL2KR with Word2Vec](https://drive.google.com/file/d/1CfHZkU3t7m8cxiDTCsVU2IfHyVK4NEi5/view?usp=sharing)

[Download JNL2KR](https://drive.google.com/file/d/1HSbNtO0CTM6aV4kKRWsMZdw2XMBIqu5t/view?usp=sharing)

[Download JNL2KR with Word2Vec](https://drive.google.com/file/d/1E-DiIN6__XWX5qOeqJ3p6bzIj0azZ87r/view?usp=sharing)

[Download JNL2KR with WS4J](https://drive.google.com/file/d/1sVzaCdjR72ZMhYqmOVXCMyORUZ7rRgYO/view?usp=sharing)

Publications related to the enhanced Genralization algorithm and extend NL2KR to Japanese (JNL2KR):
1. Kazuaki Kashihara. Translate Japanese into Formal Languages with an Enhanced Generalization Algorithm. Science and Information Conference, 2020

2. (Japanese) 樫原和昭, 植松すみれ, 宮尾祐介, Chitta Baral. ベクトル空間表現を用いた JNL2KR の語義曖昧性解消. 言語処理学会 第23回年次大会発表論文集, 2017

3. (Japanese) 樫原和昭, 植松すみれ, 宮尾祐介, Chitta Baral. JNL2KRシステムを用いた日本語から意味表現への変換. 言語処理学会 第22回年次大会発表論文集, 2016
