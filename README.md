# PerfectPangrams
Finding English Perfect Pangrams

## There are three types of files in this repository

### 1. Possible Perfect Pangram Trees

This is the tree representation of all possible perfect pangram groupings. Note that the tree is not a binary tree; every node is split into two sub-nodes that composes the original node, and every subnode can be split out multiple times as new nodes.

Example from the unix dictionary output:

```
585347->52739|532608
   52739->515|52224
      515->0|515====>[jab]
      52224->0|52224====>[klop, polk]
   52739->19458|33281
      19458->0|19458====>[bolk]
      33281->0|33281====>[jap]
   532608->0|532608====>[nth]
```

Node ```52739``` is decomposed twice, whereas its complement ```532608``` is decomposed only once. The node ```585347``` therefore has 3 different combinations, since ```52224``` maps to two different words. Those three combinations are:

```
1. jab, klop, nth
2. jab, polk, nth
3. bolk, jap, nth
```

The trees are also summarized to improve readability and minimize redudancies. Also from the unix dictionary output:

```
67108863->33554173|33554690
   33554173->2616|532608|1508353|2113600|4198404|25198592====>
      [fjeld]
      [nth]
      [squark]
      [vog]
      [cwm]
      [pyx]
   33554690->0|33554690====>[biz]
```

Which means that the output of node ```33554173``` has only 1 unique combination, composed of six words.

### 2. Dictionaries

This does not include OWL3 or OWL3+ (OWL3 augmented for this project) for copyright and trademark reasons as they are owned by Hasbro.

This includes the hand-curated blacklist of words that were found to be disqualifying.

This also includes the freely available unix dictionary.

### 3. Word Set for Perfect Pangram Trees

For each possible perfect pangram tree file, there is a file that indicates which sets of words are in that file. With this list, one can start tagging tenses for those words to potentially automate the generation of the perfect pangram from the tree.

## The code

I am not sure if people are interested in the code, and will have to spend time to clean up the code before for sharing.