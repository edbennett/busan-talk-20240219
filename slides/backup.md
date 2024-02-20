# FAIR in detail

-

![Findable](./images/findable.svg) <!-- .element: width="200px" -->

- F1. (Meta)data are assigned a globally unique and persistent identifier <!-- .element class="fragment" -->
- F2. Data are described with rich metadata <!-- .element class="fragment" -->
- F3. Metadata clearly and explicitly include the identifier of the data they describe <!-- .element class="fragment" -->
- F4. (Meta)data are registered or indexed in a searchable resource <!-- .element class="fragment" -->

Script:
Speaking of findability, let's look at the FAIR guiding principles in more detail, starting with findability. [click] First up is the need to assign data and metadata a globally unique and persistent identifier, or PID. A hyperlink to a GitHub repository or University-hosted web page isn't sufficient here, as GitHub usernames change and universities restructure their web presence, which will render all prior references to the data no longer usable. The most commonly used PID is the Digital Object Identifier or DOI, which most journals will assign to papers, and the arXiv also assigns to preprints. [click] It's also important for data to be described by rich metadata. For example, if I want to find all data generated with a specific lattice action and value of the coupling, then I should be able to. [click] The metadata should also include the identifier of the data that they describe. Since data can be large and very difficult to index, and metadata tend to be small and need to be searchable (and hence indexed), it is common to store metadata separately from the data they describe. In this case, being able to make the link between the two is vital; it isn't useful to find the metadata describing exactly the data you need, but then have no way of finding the data from that point. [click] Finally, metadata should be registered or indexed in a searchable resource. If each researcher tags their data with metadata but keeps it in a different location to every other researcher, then a potential user of the data will have no idea where to go looking.

-

![Accessible](./images/accessible.svg) <!-- .element: width="200px" -->

- A1. (Meta)data are retrievable by their identifier using a standardised communications protocol <!-- .element class="fragment" -->
  - A1.1 The protocol is open, free, and universally implementable <!-- .element class="fragment" -->
  - A1.2 The protocol allows for an authentication and authorisation procedure, where necessary <!-- .element class="fragment" -->
- A2. Metadata are accessible, even when the data are no longer available <!-- .element class="fragment" -->

Script:
Data and metadata being findable isn't useful unless they can also be accessed. [click] Firstly, given the identifier of some data or metadata, we need to be able to retrieve them using a
 standardised protocol. For metadata this is likely to be HTTP, but for larger data, there is usually a preference for other protocols that are better optimised for transferring large fil
es efficiently, such as GridFTP or UDT. [click] Whatever protocol is used, it should be open, free, and universally implementable&mdash;a protocol that is only implemented by a single pie
ce of proprietary software is not good enough. [click] Most facilities capable of storing the volumes of data generated in lattice computations are not keen on allowing global anonymous a
ccess to their resources; as such any protocol used for retrieving data will need to support authentication and authorisation. This also enables collaborations to share internal data in a
 FAIR way before they are ready to release them openly, since access controls can be used to limit who can use the data. [click] Finally, the metadata describing our data should remain av
ailable even if the data no longer are. Data are large enough that it can be impractical to store them for long periods of time; due to constraints on funding, or simple hardware failure,
 the older the data, the less likely it is to still be there. However, references to the dataset in literature should still resolve to something useful in this event; rather than having a
 bare identifier with no context, being able to see the metadata of the data that are no longer available at least allows an understanding of what was being used, even if it can no longer
 be accessed to use again.

-

![Interoperable](./images/interoperable.svg) <!-- .element: width="200px" -->

- I1. (Meta)data use a formal, accessible, shared, and broadly applicable language for knowledge representation.
- I2. (Meta)data use vocabularies that follow FAIR principles
- I3. (Meta)data include qualified references to other (meta)data

Script:
Next, we would like data and metadata from different sources to be able to interoperate and be used together. Without this, it is much harder for anyone else to build tools that work with it. [click] A step towards this is to use a common language for representing data&mdash;where possible, rather than inventing a new file format or data layout, using a commonly-used one will make the data much easier to work with. [click] They should also make use of existing vocabularies; if two datasets from different groups describe a quantity as "beta", it should be clear whether they are referring to the same quantity or not. Of course, if the vocabularies used are not themselves available openly under FAIR terms, then this will not provide as significant a benefit as it otherwise could. [click] Finally, data and metadata should make reference to other data and metadata where appropriate. For example, data describing measurements should refer back to the ensembles that were used, which will make it clear whether two different measurements at the same physics parameters used the same or different underlying ensembles.

-

![Reusable](./images/reusable.svg) <!-- .element: width="200px" -->

- R1. (Meta)data are richly described with a plurality of accurate and relevant attributes
  - R1.1. (Meta)data are released with a clear and accessible data usage license
  - R1.2. (Meta)data are associated with detailed provenance
  - R1.3. (Meta)data meet domain-relevant community standards

Script:
Last we don't share data just to be admired, but to be reused. [click] There are a number of different requirements to enable data to be reused. We've already discussed having full metadata&mdash;we can't easily reuse gauge configurations without knowing the physics parameters they represent, for example. Other, more specific requirements include [click] making sure that you specify a license for data&mdash;we discuss copyright in more detail in the video on open-access publications, but the short story is that unless you give explicit consent, nobody is actually allowed to do anything with the data you share (since this would require making a copy of the data to their machine, which requires being given permission). Appropriate licenses for data are the same Creative Commons licenses that are commonly used for publications. [click] Another aspect not to forget is the provenance of your data&mdash;when were the data made, by whom, what inputs were used, what processes or tools were used. We'll talk more about how to achieve this when we discuss reproducibility. [click] The data and metadata you publish should also meet standards relevant to the community. For example, we'll shortly discuss the International Lattice Data Grid, which defines standards for sharing gauge field configurations and their associated metadata. If you ignore these standards and publish in your own ad-hoc way, it becomes much harder for others to reuse your data using standard tooling, and interoperate them with others' data.
