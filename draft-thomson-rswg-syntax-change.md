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

The intent behind limiting changes to syntax only is that the goal is to
preserve the semantic meaning encoded in the RFC XML document.  While, stream
procedures formally establish agreement or consensus about a specific artifact
-- RFC XML in particular -- it is the semantic meaning expressed in that
document that is important.

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
addition to the existing version.  Any archive shall record the date that a
document was created or revised.

This document does not specify how archives are maintained or how archived RFC
XML might be located or identified.


## Publication Formats

Publication formats are produced from the RFC XML format.  As noted in {{Section
10.2 of !RFC7990}}, "publication formats may be republished as needed".

As the RFC XML format of a document changes, publication formats can change,
even if this might not result in observable differences.  Similarly, as
production tools change, publication formats can be regenerated to ensure a
consistent presentation across the series.

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

# Advice on Regenerating Publication Formats

This document does not include specific guidance regarding the generation of
publication formats from RFC XML source.  Decisions about how to maintain
publication formats are not a matter governed by policy as specified in RFC 9280
{{?RFC9280}}.  This section contains advice and considerations for the process
of regeneration that came out of discussions of the policy changes in this
document.

Changes to the RFC XML for existing documents might result in changes to the
documents rendered from that XML.  At the same time, the tools used to generate
renderings are under active maintenance.  Having it be possible for a fresh
rendering to replace existing publication formats is a goal supported by the
policy changes in this document.

This creates a risk that a rerendered documents change in unexpected ways when
they are regenerated.  This risk of unintentional change can be managed by
implementing validation processes:

1. Tools can be continuously checked by producing renderings for existing RFCs.
   Any change in the rendered document can then be compared with previous
   outputs and validated.  This will ensure that changes in tooling are
   deliberate and understood.

2. When a change to XML occurs, rendered documents can be regenerated and any
   change in the rendering can be validated.

Validation should be aided by automated tooling that is able to disregard
inconsequential changes in renderings, like changes in timestamps and other
annotations.  Validation of tooling can be continuous, for which automation is
essential.

In both cases, the decision to make renderings available as the publication
format for an RFC is a decision that can be made on a case-by-case basis.
Making fresh renderings available more often could mean a greater risk that
people seeking to read RFCs will obtain a copy that contains accidental errors.
At the same time, errors in publication formats might persist if they are not
replaced as tool quality and reliability improves.

Old copies of replaced publication formats could be retained to provide the
ability to isolate changes and understand the evolution of documents.


# Acknowledgments
{:numbered="false"}

Thanks to Paul Hoffman, Eliot Lear, John Levine, Pete Resnick, and Alexis Rossi
for constructive discussions about how the evolution of the RFC XML format might
be managed.
