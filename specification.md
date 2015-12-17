-   [Scholarly HTML
    core](http://scholarlyhtml.org/2011/05/03/scholarly-html-core-3/)

<!-- -->

-   This latest version of this document is available at
    <http://scholarlyhtml.org/core-specification/>

    The document is community-edited here:
    <http://pad.okfn.org/p/schtml-core> using asciidoc conventions,
    documented here: <http://powerman.name/doc/asciidoc>

    ## Requirements

    It MUST have [1]

    -   well formed HTML

    -   a URI identifying the document/fragment as ScHTML – this could
        be on a sub part of the document – at, say the \<article\> level
        or on a \<div\>. (Examples below are using
        <http://scholarly-html.org/schtml> – should this contain a
        version number?)

    -   one or more creators – which may be machines

    -   a date (or a set of revision dates)

    It SHOULD have

    -   a title

    It MAY have:

    -   an XML declaration

    -   a \<!DOCTYPE html\> declaration

    -   one or more identifiers

    [1] this implies that a validator can be built to test these
    requirements

    ## Examples

    Creator (Author) & Title

         <h1 property="http://purl.org/dc/terms/title">My Really Interesting Article</h1>
         <h2 rel="http://purl.org/dc/terms/creator" resource="http://people.cam.ac.uk/sea36">
             <span property="http://xmlns.com/foaf/spec/foaf:name">Sam Adams</span>
        </h2>

         <span rel="http://purl.org/dc/terms/creator">
             <span property="http://xmlns.com/foaf/spec/name">Sam Adams</span>
        </span>

        <span rel="http://purl.org/dc/terms/creator">Sam Adams</span>

         <span resource="http://people.cam.ac.uk/sea36">
            <span property="foaf:name" content="Samuel E. Adams">S.E.Adams</span>
        </span>

         <span rel="http://purl.org/dc/terms/creator" resource="http://cameronneylon.net">
             <span property="http://xmlns.com/foaf/spec/name">Cameron Neylon</span>
        </span>

    ### The following are valid ScHTML documents (possibly)

    Minimal ScHTML document

        <html property="http://scholarly-html.org/schtml">
        <body>
            <span property="http://purl.org/dc/terms/title">Title</span>
            <span property="http://purl.org/dc/terms/creator">Author</span>
            <span type=xsd:date>2011-03-12</span>
        </body>
        </html>

    Document with more author semantics

        <html property="http://scholarly-html.org/schtml">
        <body>
            <h1 property="http://purl.org/dc/terms/title">Title</h1>
            <h2 rel="http://purl.org/dc/terms/creator"
                  resource="http://identityservice.com/0000001>
                      <span property="http://xmlns.com/foaf/0.1/Author">Name</span>
            </h2>
            <span type=xsd:date>2011-03-12</span>
        </body>
        </html>

Document with some references and other items
 
        <html property="http://scholarly-html.org/schtml">
        <body>
            <span property="http://purl.org/dc/terms/title">Title</span>
            <span property="http://purl.org/dc/terms/creator">Author</span>
            <span type=xsd:date>2011-03-12</span>

            <p>Some text which then refers to a cited work
                  <a   rel="http://purl.org/spar/cito/obtainsBackgroundFrom"
                         resource="http://dx.doi.org/10.1039/B411699M">[citation]</a>
                  but it would still be valid if the citation had been formatted and something along the
                  lines of
                  <a   rel="http://purl.org/spar/cito/obtainsBackgroundFrom"
                         resource="http://dx.doi.org/10.1039/B411699M">Adams, 2007</a> is also
                  allowable.
            </p>
            <p>References can also involve explicitly declaring the elements of the reference entry.
                  So the following is also allowable.
                  <a rel="http://purl.org/spar/cito/parodies"
                       resource="#citation">[citation]</a> In this case the information needs to be
                  provided elsewhere in the document, possibly in a separate div for the reference list
                  entries such as below.
            </p>

        <div id="biblography" property="http://purl.org/spar/biro/ReferenceList">
          <span name="citation" property="http://purl.org/spar/biro/BibliographicRecord"
                                about="http://dx.doi.org/10.1039/B411699M">
            <span property="http://purl.org/dc/terms/title">
              Experimental data checker: better information for organic chemists</span>
            <span rel="http://purl.org/dc/terms/creator">
                <span resource="http://people.cam.ac.uk/sea36">
                    <span property="http://xmlns.com/foaf/spec/name"
                          content="Samuel E. Adams">S. E. Adams</span>
                </span>,
                <span resource="http://people.cam.ac.uk/jmg">
                    <span property="http://xmlns.com/foaf/spec/name">J. M. Goodman</span>
                </span>,
            </span>
            <span rel="http://purl.org/dc/terms/isPartOf" resource="[http://purl.org/dc/terms/journal]">
                <span property="http://purl.org/dc/terms/title"
                          content="Organic &amp; Biomolecular Chemistry">
                </span>
                <span property="http://purl.org/ontology/bibo/shortTitle">Org. Biomol. Chem.</span>
            </span>
            <span property="http://purl.org/dc/terms/date">2004</span>,
            <span property="http://purl.org/ontology/bibo/volume">2</span>
            (<span property="http://purl.org/ontology/bibo/issue">21</span>),
            <span property="http://purl.org/ontology/bibo/pageStart">3067</span>-
            <span property="http://purl.org/ontology/bibo/pageEnd">3070</span>            <br/>
                DOI: <a href="http://dx.doi.org/10.1039/B411699M"
                            property="http://purl.org/ontology/bibo/doi">10.1039/B411699M</a>
          </span>
        </div>
        </body>
        </html>

 
