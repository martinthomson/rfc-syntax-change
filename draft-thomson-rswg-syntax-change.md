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
is chosen for its ability to capture semantic details.  A policy governing how
the RFC XML format changes is described.

--- middle

# Rationale

The canonical format for published RFCs is XML {{!RFC7990}}.  Historically, the
published version of an RFC has been immutable ({{Section 7.6 of ?RFC9280}}).

The RFC XML format {{?RFC7991}} is not able to address use cases that were not
originally anticipated during its design.  It might also be possible to improve
the format to better capture meaning.

Though it might be possible to evolve the format and only use the new format for
the publication of new RFCs, this would mean that there would be no single
format across the series.  Tools that seek to process RFC XML would need to
understand all iterations of the format.


# Syntax Change Policy

The RFC Series Working Group (RSWG), constituted by {{!RFC9280}}, acts as
custodian for the RFC XML format.  If the RSWG reaches consensus, they can
propose a revision to the RFC XML format.

The RSWG publishes an RFC on the Editorial stream that describes the format
change.  An updated XML format is used for the publication of new RFCs.  Some
time might be necessary to implement those changes in tools and active
documents.

Existing RFCs can be updated to use the new format.  The RFC that describes
format changes can also describe how the XML of existing RFCs will be updated.

Updates to the RFC XML format need to ensure that any change to existing RFCs
preserves -- to the greatest extent possible -- the semantics expressed in the
original RFC.  That is, the intent is that changes only update the XML syntax,
they do not alter the semantics that are expressed using that syntax.

This process does not require that updates to XML avoid all risk of introducing
semantic changes to existing RFCs.  Instead, it only requires that the RSWG
carefully consider the potential for semantic changes, take steps to understand
the risk of a semantic change (either deliberate or inadvertent), and to limit
those risks.


## Canonical Version

When the RFC XML for an RFC is updated, the updated document becomes
the canonical version of that RFC.


## Archival

When the RFC XML of an RFC is updated, the updated document shall be archived in
addition to the existing version.

This document does not specify how archives are maintained or how archived RFC
XML might be located or identified.


## Publication Formats

Publication formats are produced from the RFC XML format.  As the RFC XML format
of a document changes, publication formats can change, even if this might not
result in observable differences.  Similarly, as production tools change,
publication formats can be regenerated to ensure a consistent presentation
across the series.

Publication formats -- or the contexts in which they are displayed -- can
optionally provide additional details of the specific RFC XML version that they
were generated from, or provide a means to discover alternative renderings.

This document does not stipulate whether publication formats are archived.


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
