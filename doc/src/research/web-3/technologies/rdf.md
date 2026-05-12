# RDF: Meaning as Triples

## Resources

### Specs

- [W3C RDF 1.2 Primer](https://www.w3.org/TR/rdf12-primer/) - Gentle intro with examples, from the spec authors.
- [W3C RDF 1.2 Concepts](https://www.w3.org/TR/rdf12-concepts/) - Formal abstract data model. Read after the Primer.

### In Semantic Web

- For how RDF compares to property graphs, see [The Graph Space: Property Graph vs RDF](../../graph-database/graph-databases-book/3-the-graph-space.md#property-graph-vs-rdf).
- RDF provides the data layer. For vocabulary/class hierarchies, see RDFS (part of the [OWL](./owl.md) page). For querying, see [SPARQL](./sparql.md).

### Others

- [Baeldung: Introduction to RDF](https://www.baeldung.com/cs/rdf-intro) - Concise, covers triples, serialization formats (Turtle, JSON-LD, RDF/XML), and SPARQL basics.
- [Enterprise Knowledge: The RDF Guide](https://enterprise-knowledge.com/the-resource-description-framework-rdf/) - Practical, application-focused. Good on why RDF matters for knowledge graphs.

### Alternative Serialization Formats

RDF is an abstract model, not a file format. Multiple serializations exist:

- **Turtle** - Human-readable, most commonly used for hand-written RDF.
- **JSON-LD** - JSON-based, popular in web APIs and schema.org.
- **RDF/XML** - Original format, verbose, mostly legacy.
- **N-Triples** - One triple per line, simple but verbose. Good for streaming.
