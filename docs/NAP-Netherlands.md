# NAP Netherlands

| NAP Name | NAP Link | Contact | Status |
| :------------: | :------------------: | :------------------: | :------: |
| NTM (Nationaal Toegangspunt Mobiliteitsdata) | [ntm.ndw.nu](https://ntm.ndw.nu) | ntm@ndw.nu | ![deployed](https://img.shields.io/badge/-deployed-green?style=flat) |

## Access metadata

Metadata for an individual dataset can be retrieved via a REST endpoint, compliant with mobilityDCAT-AP:

```
https://ntm.ndw.nu/api/dcat/v1/{datasetID}?lang=nl
```

The `lang` parameter (`nl` or `en`; default `nl`) indicates the preferred language. If a translation in the requested language is available, it is returned; otherwise the API falls back to the publication's source language (`nl` or `en`) — consumers should always check each literal's language tag rather than assume it matches the requested `lang` value. English content is either manually validated or machine-translated from Dutch; the provenance is indicated per literal via its language tag (e.g. `en` vs. `en-t-nl-t0-deepl`, following IETF BCP 47 conventions for machine translation). Since translation now runs automatically on save for new and modified publications, fallback cases are expected to become rare over time.

The response is a valid RDF graph describing the requested dataset. Structurally, it is returned as a `dcat:Catalog` containing a single `dcat:CatalogRecord`, whose `foaf:primaryTopic` points to the `dcat:Dataset` itself. The `dcat:CatalogRecord` carries record-level metadata (`dct:created`, `dct:modified`, `dct:language`) describing when the metadata entry was created or last changed, separate from the dataset's own properties. The dataset may contain one or more `dcat:Distribution` entries.

Content negotiation is supported via the `Accept` header, returning:
- `application/rdf+xml` (RDF/XML)
- `application/ld+json` (JSON-LD)
- `application/turtle` (Turtle)

## Harvest metadata

Metadata of the entire catalogue can be retrieved in a single call via:

```
https://ntm.ndw.nu/api/dcat/v1?lang=nl
```

This returns a `dcat:Catalog` containing a `dcat:CatalogRecord` for every published dataset, each structured as described above. The same content negotiation and language parameter apply.
