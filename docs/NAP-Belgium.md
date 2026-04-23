# NAP Belgium

| NAP Name | NAP Link | Contact | Status |
| :------------: | :------------------: | :------------------: | :------: |
| NAP Belgium	| [transportdata.be](https://www.transportdata.be)	| contact@transportdata.be |	![deployed](https://img.shields.io/badge/-deployed-green?style=flat) |

## Access metadata

Following the DCAT model, metadata can be accessed at both individual dataset level and catalog-wide level. MobilityDCAT-AP support for the Transportdata platform is implemented through [ckanext-dcat-be-napits](https://github.com/belgium-its-steering-committee/ckanext-dcat-be-napits), a custom-built extension to the CKAN platform.

### Dataset

Suffix the dataset page url with a common linked data format extension:  
Example: `https://transportdata.be/dataset/wegenregister.ttl`

### Catalog

Suffix the catalog url with a common linked data format extension:  
Example: `https://transportdata.be/catalog.ttl`  


See the [ckanext-dcat documentation](https://docs.ckan.org/projects/ckanext-dcat/en/latest/endpoints/#dataset-endpoints) for more details on how the url's are composed and what RDF formats are available.

## Harvest metadata

Development in progress. Documentation not available just yet.
