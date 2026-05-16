# RDF: Meaning as Triples

RDF (Resource Description Framework) is a framework for expressing machine-readable information about [resources](./uri/rfc-3986.md) (can be anything as defined like the URI spec). RDF enables automated processing and exchange of information across applications without losing meaning.

In the Semantic Web stack, XML provides structure but its tags have no machine-interpretable meaning: `<creator>` is just a string to an XML parser. RDF adds a **universal data model** (triples with IRIs) on top, so every relationship and resource has a globally unique identifier. This makes data interoperable and mergeable across sources. In that sense, **RDF is metadata about resources, described in a way machines can reason about**.

> Remark: Think of it like this - With XML, data can be displayed to human & human can write programs to process the XML documents. Interpretation of XML is still under human's discretion. With RDF, there's a standard way to interpret the XML documents.

RDF is another graph model like property graphs. For how RDF compares to property graphs, see [The Graph Space](../../graph-database/graph-databases-book/3-the-graph-space.md#property-graph-vs-rdf).

RDF is recommended by W3C.

- Enriching web pages with machine-readable metadata (schema.org).
- Linking datasets across sources (e.g. paintings to artist information in Wikidata).
- Standards-compliant database data exchange.
- Cross-dataset querying via SPARQL.

Subpages:

- [Data Model](./rdf/data-model.md): Triples, RDF terms, named graphs, semantics.
- [Serialization Formats](./rdf/serialization.md): Turtle, N-Triples, TriG, N-Quads, JSON-LD, RDFa, RDF/XML.
- [RDFS](./rdf/rdfs.md): Vocabularies and class hierarchies for RDF.

See also [OWL](./owl.md) for full ontology language and [SPARQL](./sparql.md) for querying.

## Resources

### Specs

- [W3C RDF 1.2 Primer](https://www.w3.org/TR/rdf12-primer/) is a gentle intro with examples (Warning: It's an informative Group Note Drafts and no guarantee is made regarding its claims).
- [W3C RDF 1.2 Concepts](https://www.w3.org/TR/rdf12-concepts/) is the formal abstract data model. This is a normative specs, as oppose to the above specs.

### Others

- [Baeldung: Introduction to RDF](https://www.baeldung.com/cs/rdf-intro) is concise and covers triples, serialization formats (Turtle, JSON-LD, RDF/XML), and SPARQL basics.
- [Enterprise Knowledge: The RDF Guide](https://enterprise-knowledge.com/the-resource-description-framework-rdf/) is practical and application-focused, good on why RDF matters for knowledge graphs.
