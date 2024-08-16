![Lint](https://github.com/tbauriedel/ansible-collection-gographite/actions/workflows/linting.yml/badge.svg)
![Molecule](https://github.com/tbauriedel/ansible-collection-gographite/actions/workflows/molecule.yml/badge.svg)

# ansible-role-gographite

Installs and configures [go-carbon](https://github.com/go-graphite/go-carbon) and [carbonapi](https://github.com/go-graphite/carbonapi).  
All roles of the collection should work without adding any custom configuration.  

## Roles

* [go-carbon](roles/go-carbon/README.md): Install and configure go-carbon
* [carbonapi](roles/carbonapi/README.md) Install and configure carbonapi
  
## Example usage
```
---
- hosts: graphing
  become: true
  collections: tbauriedel.gographite
  roles:
    - go-carbon
    - carbonapi
```

## Contribution
Not all components of the go-graphite project are currently managed with that collection.  
Also not every configuration possibility are implemented for the already existing roles.

New stuff will be added setp by step, wgen the need arises.
If you want to use this ansible collection but something is missing, you are welcome to create a PR with the necessary settings!
