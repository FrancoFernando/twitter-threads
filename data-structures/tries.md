🧱 Tries in a nutshell

Tries are advanced data structures used to efficiently represent strings:

→ intro
→ nodes
→ operations
→ tries vs maps
→ practical use cases

A data structure thread 🧵 ↓

Intro

• Tries are tree based data structures whose nodes store the letters of an alphabet

• Letters are stored as links to other nodes

• Each path from the root to the leaves forms a word

• All the descendants of a node share a common prefix associated to that node

• For example, the words prefix, premium and preview have pre as common prefix

• When stored in a trie they share 3 links in their paths from the root to the leaves: p -> r-> e



Trie Nodes

Each node contains:

• a set of links to other nodes

• a flag indicating if a word ends in the node

• the max number of links per node depend on the alphabet size

Links between nodes can be represented with:

• hash tables
• fixed size arrays

With hash tables keys are characters and values are links to the next nodes.

With arrays the characters are implicitely encoded as indexes.

Arrays are faster, but waste memory for empty links. Operations

A trie provides 3 main operations:

• inserting a new word

• searching for a given word

• searching for a given prefix

• all operations takes O(n) time, where n is the lenght of the word (or of the prefix in the last case)

↓

• insert a word require traversing the trie while iterating through the word characters

• the starting points are the trie root and the 1st word character

• if a node doesn't contain a link corresponding to a character, we need to create the next node before moving to it

• search a word require a similar process with 2 differences

• if a node doesn't contain a link corresponding to a character, we return false

• once we iterated all the word characters we return true if the node flag indicates that a word ends in the node, false otherwise

• search a prefix is equal to search a word

• the only difference is returning true if we iterated all the prefix characters, without checking the flag

Trie vs Map

The main use cases where tries outperform maps to store a set of words are:

• words with many common prefixes, because a trie can save space reusing the same nodes and links

• find all the words with a common prefix and enumerate the words lexicographically

Practical use cases

A trie allows to answer efficiently to the following questions:

• Are there any words that start with a given prefix?
• How many words start with a given prefix?
• What are all the words that start with a given prefix? Thanks to its properties Tries are used in several practical applications like:

• word games
• speel checkers
• browser history
• autocomplete word system
• longest prefix matching (internet routing)
