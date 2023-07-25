---
title: "Changing XML Syntax for RFCs"
category: info

docname: draft-thomson-rswg-syntax-change-latest
stream: editorial
number:
updates: 7990
date:
v: 3
area: "RFC Editor"
workgroup: "RFC Series Working Group"
keyword:
 - next generation
 - unicorn
 - sparkling distributed ledger
venue:
  group: "RFC Series Working Group"
  type: "Editorial Stream Working Group"
  mail: "rswg@rfc-editor.org"
  arch: "https://mailarchive.ietf.org/arch/browse/rswg/"
  github: "martinthomson/rfc-syntax-change"
  latest: "https://martinthomson.github.io/rfc-syntax-change/draft-thomson-rswg-syntax-change.html"

author:
 -
    fullname: Martin Thomson
    organization: Mozilla
    email: "mt@lowentropy.net"

normative:

informative:


--- abstract

The authoritative version of RFCs are published in an XML format.  This format
is chosen for its ability to capture semantic details.  A high-level process is
described for the revision of the RFC XML format.

--- middle

# Rationale

The canonical format for published RFCs is XML {{!RFC7990}}.  Historically, the
published version of an RFC has been immutable ({{Section 7.6 of ?RFC9280}}).

The RFC format {{?RFC7991}} is not able to address use cases that were not
originally anticipated.  It might also be possible to improve the format to
better capture meaning.

Though it might be possible to evolve the format and only use the new format for
the publication of new RFCs, this would mean that there would be no single
format across the series.  Tools that seek to process RFC XML would need to
understand all iterations of the format.


# Syntax Change Policy

The RFC Series Working Group (RSWG), constituted by {{!RFC9280}}, acts as
custodian for the RFC XML format.  If the RSWG reaches consensus, they can
propose a revision to the XML format.

The RSWG publishes an RFC on the Editorial stream that describes the format
change.  An updated XML format is used for the publication of new RFCs.  Some
time might be necessary to implement those changes in tools and active
documents.

Existing RFCs can be updated to use the new format.  The RFC that describes
format changes can also describe how the XML of existing RFCs will be updated.

Updates to the XML format need to ensure that any change to existing RFCs
preserves -- to the greatest extent possible -- the semantics expressed in the
original RFC.  That is, the intent is that changes only update the XML syntax,
they do not alter the semantics that are expressed using that syntax.

This process does not require that updates to XML avoid all risk of introducing
semantic changes to existing RFCs.  Instead, it only requires that the RSWG
carefully consider the potential for semantic changes, take steps to understand
the risk of a semantic change (either deliberate or inadvertent), and to limit
those risks.


## Canonical Version

When the XML for an existing RFC is updated, the updated XML becomes the
canonical version of that RFC.


## Archival

When RFC XML is updated, the updated version of the document shall be archived
in addition to the existing version.

This document does not specify how archives are maintained or how archived XML
might be located or identified.


## Publication Formats

Publication formats are produced from the XML format.  As XML changes,
publication formats necessarily change, even if this might not result in
observable differences.  Similarly, as production tools change, publication
formats can be regenerated to ensure a consistent presentation across the
series.

Publication formats -- or the contexts in which they are displayed -- can
optionally provide additional details of the specific XML version that they were
generated from, or provide a means to discover alternative renderings.

This document does not stipulate whether production formats are archived.


# Security Considerations

The RSWG are responsible for managing the risk of semantic changes that would
affect the interpretation of existing and future RFCs.  Changes to content that
has security implications would have security-relevant consequences.


# IANA Considerations

This document has no IANA actions.


--- back

# Acknowledgments
{:numbered="false"}

Thanks to Paul Hoffman, John Levine, Pete Resnick, and Alexis Rossi for
constructive discussions about how the evolution of the RFC XML format might be
managed.
