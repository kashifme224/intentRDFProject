# IntentRDFProject
This repository contains the RDF models proposed in the paper "Contextual Knowledge-based Intent Processing for Management of Next Generation Cellular Networks" that is under review at IEEE NetSoft2023. The paper can be found on arXiv at https://arxiv.org/abs/2302.08544.

## Files
The repository consists of the following contents:

- **intentmodel**: provides the intent common model (https://www.tmforum.org/resources/reference/tr290-intent-common-model-v2-0-0/) as RDF graphs along with its reporting classes for a service orchestration use case.
- **sample_intents**: provides the layered intents for 2 service use cases for a 5G mobile network
- **service_models**: provides the proposed mission and non-mission critical service models as RDF graphs as defined in the 3GPP TS 23.501.

## Usage

To use the intent and entity models in your own project, you can simply import the RDF files into your own RDF store or application. The ontology file should be imported first to ensure that the intent and entity models are properly interpreted.

For example, using the `rdflib` Python library:

```python
from rdflib import Graph

# create an RDF graph
g = Graph()

# read the ontology file
g.parse('Mcptt.rdf', format='turtle')

# example SPARQL query
qres = g.query(
    """
    SELECT ?parameter ?value
    WHERE
    {
       ?service ?property [ icm:valueBy [ ?parameter ?value ] ] .
       FILTER (?parameter = param && ?service = serv)
    }
    """)

# print the results of the query
for row in qres:
    print(row.label)
```
## License
The intent and service models in this repository are released under the Creative Commons Attribution 4.0 International license. The full text of the license can be found at https://creativecommons.org/licenses/by/4.0/legalcode.

## Contact
If you have any questions or comments about the RDF models in this repository, please contact the author at kashif.mehmood@ntnu.no.
```kotlin

I hope this is what you were looking for! Let me know if you have any other questions.

```
