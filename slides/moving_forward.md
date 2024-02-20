# Moving forward

-

## Problems with the approach to date

- Doing initial analysis manually is unnecessarily time consuming
- Hard for collaborators to stay in sync during analysis
- Automating a manual analysis after the fact is _more_ time consuming
- Bespoke automation each time is a barrier to reusability
- Delaying publication is not acceptable
- Publicly pointing out mistakes in previous analyses also not great

-

## Aim going forward

- Do analysis with publishing in mind from day 0
- Publish data and workflow concurrently with preprint
- Harmonise tooling, reduce code duplication

-

## Why is this hard?

- Different technology experiences
  - Python? Julia? Mathematica??
- Reusing tools
  - Two different papers in preparation want to use the same technique:
  - Where does the implementation live?
- Collaborative analysis
  - Different analyses depend on each other
  - How do we avoid needing to throw data over the wall?

-

## Collaboration

- Everyone needs everyone's data
  - This may be big
- Everyone needs everyone's code
  - This may be tied to particular versions of data
- Everyone needs to be able to run the entire workflow
  - Environments need to be well specified or shared
  - (Workflow needs to be well-specified)

-

## Possible solution 1

- Git repository (GitHub, GitLab, ...) for code
- [DVC](https://dvc.org) for data
- Conda `environment.yml` for environment
- Each collaborator
  - Clones code, data
  - Instantiates environment

-

## Possible solution 1a

- Add continuous integration
  - When data or code updated:
  - Environment instantiated on a server
  - Analysis run end-to-end
  - Generated assets made available
- We still want to test locally

-

## Possible solution 2

`¯\_(ツ)_/¯`
