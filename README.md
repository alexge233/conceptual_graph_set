# conceptual_graph_set
A conceptual graph data-set for NLP/NLU serialised in JSON format

This is a data-set of [conceptual graphs](https://en.wikipedia.org/wiki/Conceptual_graph) which have
been obtained from RSS feeds from BBC, SkyNews, KnoxNews, USA Today and Science Daily.
The graphs have been manually transcribed and may contain a few errors (contradictions).

The POS tag field is empty on purpose, albeit an updated data-set with POS tags could be made available upon request.
This set has been used for dependency parsing (NLU) based on Semantics and Syntactics.

Each JSON object is a *sample* which associates a pattern/sentence (field `text`) to a conceptual graph.
The JSON for the CG uses an adjacency matrix:

1. A list of `concepts`
2. A list of `relations`
3. A list of `edges` connecting `concepts` to `relations` or vice versa.

The actual fields are:

- `index` defining the order of appearance.
- `label` defining the actual text/sign/token of a node.
- `uuid` a UUID v4 for unique identification.

In the case of edges/adjacancies:

- `nodeFrom` is the originating vertice of the edge
- `nodeFrom` is the destination vertice of the edge
- `index` is used for easy index access
- `order` is used for edge order

You can deserialise them using the [cgpp](https://github.com/alexge233/cgpp.git) for C++, 
or any JSON library in the language of your preference.

You may have a look in directory `images` for examples of some rendered graphs.
Rendering was done using [VivaGraphJS](https://github.com/anvaka/VivaGraphJS) in a browser.

Please add a reference to the following citation when using this data-set for Academic or Research purposes:

```
@article{gkiokas2014training,
  title={Training a Cognitive Agent to Acquire and Represent Knowledge from RSS feeds onto Conceptual Graphs},
  author={Gkiokas, Alexandros and Cristea, Alexandra I},
  journal={IARIA COGNITIVE},
  pages={184--194},
  year={2014},
  publisher={Citeseer}
}
```
