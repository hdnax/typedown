# The Semantic Web

Link: https://www.w3.org/2000/Talks/0906-xmlweb-tbl/text.htm.

Authors: Tim Berners-Lee, Dan Connolly, Lynn Andrea Stein, Ralph Swick.

## Context

To re-iterate, the **semantic web** is an extension of the **world wide web**. We differentiate the two concepts:

- The world wide web is an interlinked networks of documents, called **hypertexts**.
  - It emphasises on linking related resources together, allowing humans to browse through a network of related resources.
  - Its essence lies in **universality**:
    1. Hypertext link allows anythin to link to anything.
    2. Anything must be able to be put on the web.
  - Implications: The web technology is inclusive, regarding cultures, media, quality.
  - Shortcomings: Machines do not have a well-defined, unambgiuous way to derive meanings from documents in the world wide web.

- The semantic web aims to give data a well-defined meaning so machine can readily process them.

## "Weblike"

- Weblike qualities:
  - Decentralized: No single party control the web content.
  - Universal: Any resources can link to any resources.
  - Compromised "total consistency": Because no single party wholly control the web, no one can ensure assumptions are actually held up.

- Semantic web must be weblike.

- Analogy:
  1. The world wide web is like one big book.
  2. The semantic web is like one big database/mathematical formular.

- The semantic web is not a separate web: It's another dimension of information added to the world wide web.

Before entering the next sections, it's useful to view this tower of semantic web:

![Semantic Web Tower](https://www.w3.org/RDF/Metalog/images/sw-tower.png)

## The First Level of Semantic Web: RDF

- XML (eXtensible Markup Language): Allow creating structured documents that can express various information, but the interpretation of such information is application-specific, which means, there's no universally unambiguous way to describe their meanings.
  - For example, the same `<name>` can mean different things in different contexts.
- RDF (Resource Description Framework): Provide a model to convey meanings of information as sets of **triples** (Subject + Verb + Object). The triples form **directed graphs**, creating a web of concepts.

- RDF treats subjects, verbs and objects as **resources**.
  - Verb is also called an "RDF property".
- In RDF, both subjects and objects are identified by URIs.
  - RDF utilizes **XML namespaces** to assign URIs to every concept. `<name>` in XML now is no longer ambiguous.

- An RDF document asserts that **particular things** have **particular properties** with **particular values**.

## Generalizing About Current Knowledge Representation (KR) Systems

KR is a widely researched topic. The authors identified KR as a field at the time as follows:

> Knowledge Representation as a field is indeed in a state rather similar to the state of Hypertext technology before the web: it is clearly a good idea, and some very nice demonstrations exist, but it has not yet changed the world. In both cases, the idea is good but to be powerful, they must form a single global system. - "The Semantic Web".

In the past, KR systems did not scale:

- Some used a centralized data technology, requiring data to be centralized too.
- Some were "conceptually centralized", requiring everyone to maintain the same definition of concepts.
- Some used fuzzy reasoning systems (maybe it means to imply imprecision or best-effort reasoning), but they did not scale.

KR systems that possess weblike qualities should allow concepts to be independently conceived and retrospectively linked.
