# Guidelines to Authors of Internet-Drafts

## Table of Contents
  * [Introduction](#introduction)
  * [Background](#background)
  * [Internet-Draft Names](#internet-draft-names)
  * [The Submission Process](#the-submission-process)
  * [Content](#content)
    * [Required Content](#required-content)
    * [Content Considerations](#content-considerations)
  * [Format](#format)
  * [References](#references)
  * [Acknowledgments](#acknowledgments)

## Introduction

Internet-Drafts (I-Ds) are the basic work item of the IETF. They are the
primary inputs into what may eventually be published as a Request for Comment
(RFC).

Internet-Drafts are used by all of the RFC Streams [RFC 8279]. The guidance
in this document applies to all streams unless it is identified as specific
to a particular stream.

Internet-Drafts are prepared by people acting in possibly several roles, such
as an author or an editor. This guidance uses the term "author", but the
guidance applies to people acting in any role.

This document collects and summarizes requirements and guidance from
many sources. The following resources should be consulted
for definitive details:

  * The IETF Standards Process is described in [RFC 2026].
  * The IETF rules concerning copyright are described in [BCP 78]
  * The IETF rules on IPR are described in [BCP 79]
  * The IETF Trust Legal Provisions Relating to IETF Documents [TLP], called
    "the TLP" for short, provides many details about copyright policy and
    practice.

Much of the guidance in this document is in the form of something that can be
inspected, or checked, to see whether changes should be made before submitting
an I-D. These items are marked with checkboxes ([ ]). However, authors are
expected to be familiar with and to apply the full guidance in this document.

## Background

All versions of Internet-Drafts are kept in the Internet-Draft Archive
[ARCHIVE]. Active versions of Internet-Drafts are also placed in the
Internet-Draft Repository [REPOSITORY].

Versions of Internet-Drafts are removed from the Repository when any of the
following occur:

  * the I-D is updated with a new version
  * the I-D is replaced by another Internet-Draft
  * the I-D is published as an RFC
  * the I-D expires.

An I-D expires 185 days after the draft was placed in the repository unless it
is in a state that prevents it from expiring. Examples of such states include
being processed by the IESG for publication in the IETF stream, or being under
review by the Independent Series Editor (ISE) for publication in the
Independent Submission Stream.

Internet-Drafts are not removed from the Archive when they are removed from
the Repository. Removing an I-D from the Archive occurs only in exceptional
circumstances, described in this IESG Statement [ID-REMOVAL].

Even though Internet-Drafts are kept in the Archive, they are not an archival
series, and should not be cited or quoted as anything other than "work in
progress".

## Internet-Draft Names

Internet-Draft names appear inside the I-D, and are used as components of
filenames for the various formats the I-D may appear in. The characters
that may appear in an I-D name are restricted:

- [ ] Ensure that the I-D name consist only of the lower case letters a-z,
      the digits 0-9, and hyphens.

The name of an I-D consists of several components, separated by a hyphen.
No empty components are allowed. That is, consecutive hyphens may not appear
in an I-D name.

The first component identifies the I-D as a draft (as opposed to other
document types, such as charters or reviews).

- [ ] Verify that the I-D name begins with "draft-"

The second component identifies the source of a draft. If an I-D  has
been adopted into any stream other than the Independent Submission Stream,
this component will identify the stream.

If the I-D has not been adopted into any stream or is being considered for
publication in the Independent Submission Stream, the second component should
consist of a string related to the names(s) of the author(s). There are no
mechanical rules for this string beyond consisting only of the allowed
characters.  However, objectionable or misleading strings are subject to change
or removal.  The string is typically the last name of the lead author or
editor.

The second component must not be easily confused with a group acronym. The
following strings for the second component are reserved for their respective
organizations (some of which are historic):
  * iana
  * iaoc
  * iesg
  * ietf-trust
  * rfc-editor

The second component should not contain a hyphen. Legacy uses and edge cases
such as hyphenated last names are allowed. Having a hyphen in the second
component makes it hard to extract programmatically. This forces many tools
to use heuristics when tying to locate the second component.

- [ ] Ensure the second component reasonably identifies the source of the I-D.

      If the I-D has been adopted by a stream, ensure the second component is
        * ietf for the IETF stream
        * iab for the IAB stream
        * irtf for the IRTF stream
      Otherwise, ensure that the second component is not a group acronym or a
      reserved string, is not objectionable, and does not introduce confusion.

Note that any I-D submitted with one of these stream identifiers in the second
component that has not been adopted by the indicated stream will either be
rejected or replaced.

If the I-D is targeted at or has been adopted by a group, the group's acronym
should be added to the name just after the second component, separated by a
hyphen.

- [ ] Ensure adopted or group targeted I-Ds identify the group just after the
      second component by including the group's acronym.

Note again that if the I-D has not been adopted into a stream, and identifies a
stream in the second component, it will be rejected or replaced. In particular
for IETF stream documents, the first version of a draft with a name that begins
with 'draft-ietf-acronym-' for any working group acronym must be approved by
the working group's chairs before it will be posted.

The remainder of the name describes the purpose of the I-D, usually in just a
few words. Each word is separated by a hyphen.

- [ ] Ensure the name reasonably reflects the purpose of the I-D.

Internet-Drafts are versioned with two digits, separated from the name with a
hyphen. The initial version of an I-D must be '00', and subsequent updates must
increment the version number by one.

If the I-D is submitted as XML, the name and version of the document will be
declared in the appropriate "name" and "version" attributes [RFC 7991], and the
filename submitted must be of the form "name-version.xml".

If the I-D is submitted as plain text, the name and version will appear on the
documents first page, and the filename submitted must be of the form
"name-version.txt".

Convention dictates that an individual submission seeking adoption by a
working group will include the working group's acronym just after the
second component. For example, a person or group identified as "foo"
seeking to get a document about "specific-subject" adopted by the "bar"
working group might chose the name "draft-foo-bar-specific-subject", and
submit the file "draft-foo-bar-specific-subject-00.xml". If the document is
later adopted by the working group, the authors will usually create a new
I-D named "draft-ietf-bar-specific-subject" and submit it as
"draft-ietf-bar-specific-subject-00.xml". Note that the version number of
this new I-D will always be "00".

## The Submission Process

Internet-Draft submissions are made using the IETF Datatracker's [DATATRACKER]
submission tool [IDST]. The submission should be provided as XML source.
XML2RFC Version 3 XML source [RFC 7991] is preferred, but Version 2 source
[RFC 7749] will be accepted. If XML source is not available, a plain-text
submission will be accepted.

Currently, the submission tool will accept both an XML and plain-text
submission, as well as PDF and PostScript versions of the document. In such
submissions, the XML is authoritative, if present, otherwise the plain-text is
authoritative. It is expected that the tool will change to allow only the
submission of XML or plain text, but not both, and to not accept other formats.

If XML source is submitted, the Datatracker will generate plain-text and place
it in the Archive. If v3 source is submitted, the Datatracker will also
generate HTML and place it in the Archive. The Datatracker also presents
on-demand generated html-ized views of the plain-text versions of I-Ds.

The submission tool will double-check many, but not all, of the guidance points
called out in this document. Authors are expected to have manually applied the
guidance before submission.

While many of the requirements pointed to by this document are for RFCs,
Internet-Drafts are expected to adhere to them to the extent possible. In
particular, IETF stream I-Ds submitted to the IESG for must follow all of the
guidance. Working groups are encouraged to require the guidance be followed for
I-Ds entering Working Group Last Call. I-Ds will progress through the review
and publication process more efficiently the earlier the guidance is followed
in the I-D.

If authors are unable to submit an I-D through the Datatracker, they may make a
manual-post request by sending the I-D via email to support@ietf.org. The
message may contain the I-D as an attachment, or a URL that will resolve to the
I-D. The I-D must be a stand-alone document in either XML or plain-text format.
Multiple files presented in containers such as zip or tar will not be accepted.
All other formats will be discarded without opening.

Be aware of the deadlines for submitting I-Ds before each IETF Meeting. The
important dates page [IMPORTANTDATES] will show the deadline for submitting
I-Ds. Some meetings may have an earlier deadline for initial versions of I-Ds
than for updates to existing I-Ds. After the deadlines, submissions will not
be accepted until the meeting begins. The leadership responsible for each
stream can override this submission blackout period when appropriate. Care
should be taken when submitting an I-D near the deadline, especially if
a manual post is requested. The steps to confirm and post the submission
take time.

When a submission is made through the submission tool, the authors will
receive email with a request to verify the submission. The submission will
not be accepted and posted until the action requested in that email is
performed. If the submitter is logged into the Datatracker and listed as
an author this step is bypassed.

If the I-D being submitted replaces another I-D (such as in the earlier
example discussing creating a new I-D when a working group adopts a
document), the submitter will be able to identify the replacement using
the submission tool. A group chair or the IETF Secretariat will verify
the replacement before the relationship is added to the Datatracker.

## Content

Internet-Drafts and RFCs have certain required content. I-Ds should take the
accrued knowledge on frequent and particularly important topics into
consideration as early in their life-cycle as possible.


### Required Content

If an Internet-Draft is prepared in XML, the tooling will ensure that
required content is present, automatically provide selected boilerplate
text, and handle the majority of formatting concerns. An Internet-Draft
prepared as plain text requires more effort to ensure that the required
content is present and in the right form.

As Internet-Drafts are inputs into what might eventually be published as
RFCs, their content requirements are based on what is required in an RFC.
Specifically, many of the documents defining these requirements are written
in terms of RFCs and do not mention Internet-Drafts, but these requirements,
with very few exceptions, apply to Internet-Drafts.

- [ ] Ensure that the I-D correctly provides the following:

      * The date the document was generated
      * A list of authors/editors and their affiliations
      * The group that originated the draft (if any)
      * The intended status of the document
      * The set of RFCs this I-D intends to update or replace, if any

See [RFC 7841] for specific details.

These required elements are represented explicitly in XML source. The tools
will automatically format the information when building a presentation format.
The format required for these items in plain-text submissions is discussed
in the Format section below.

- [ ] Ensure that the I-D contains each of the following sections:

      * IPR-Related Notices
      * Abstract
      * Introduction
      * Security Considerations
      * IANA Considerations
      * References
      * Authors' Addresses

- [ ] If the document uses [BCP 14] normative language, ensure the unchanged
      boilerplate text from BPC 14 is present in the I-D, and that BCP 14
      is normatively referenced.

         * Note that BCP 14 is made up of both [RFC 2119]
           and [RFC 8174], and they must be cited as described in the latter
           document. Please use the boilerplate text exactly as specified in
           RFC 8174.

- [ ] If the I-D intends to obsolete or update existing RFCs, ensure there
      is a "Summary of Changes" section.

#### IPR-Related Notices

[BCP 78] and [BCP 79] specify the IETF's Intellectual Property policies.
Among them is a requirement to include certain standardized text in each
Internet-Draft. This text is managed by the IAB. The current acceptable
boilerplate forms are described at [HEADERS-AND-BOILERPLATE] and fully expanded
forms of the boilerplate texts are maintained at [RFCEDITOR-MEMOSTATUS].

Authors preparing XML submissions indicate which boilerplate text to use by
providing one of a set of enumerated values to the ipr attribute of the rfc
element in the XML source. The tooling generates the actual required text. See
[RFC 7991] Appendix A1 for the available ipr attribute values. The majority
of IETF stream documents I-Ds indicate "trust200902" or "pre5378Trust200902"
as needed.

Authors preparing plain-text submissions must carefully reproduce the
text most appropriate for the Internet-Draft.

IETF stream documents authors must not select boilerplate that prohibits
publication as an RFC.

A standard Copyright Notice and Disclaimer must be included. This will be
generated automatically for authors preparing XML submissions. Authors of
plain-text submissions should refer to the [TLP] section 6 for exact text
to reproduce.

- [ ] Verify that one of the approved IPR boilerplate selections are
      indicated in XML submissions or exactly reproduced in plain-text
      submissions.

- [ ] Verify that the most appropriate IPR boilerplate for the I-D is
      indicated.

Any Internet-Draft submitted that does not select on of the required IPR
boilerplate statements will be rejected. The IETF Secretariat cannot add
a selection for the author.

If the submitter of a non-IETF stream I-D desires to eliminate the IETF's
right to make modifications and derivative works of the I-D, one of two
notices must be included after the IPR statement.

The first choice is used if the contributor intends for the I-D to be
published as an RFC:

      This document may not be modified, and derivative works of it may
      not be created, except to format it for publication as an RFC or
      to translate it into languages other than English.

This will be automatically generated by the tools from XML source if the
ipr attribute value "noModificationTrust200902" is selected.

The second choice is used when the contributor does not intend for the I-D
to be published as an RFC:

      This document may not be modified, and derivative works of it may
      not be created, and it may not be published except as an
      Internet-Draft.

This will be automatically generated by the tools from XML source if the
ipr attribute value "noDerivativesTrust200902" is selected.

These notices may not be used with any IETF standards-track document or with
most working group documents, except as discussed in [BCP 78], since the IETF
must retain change control over its documents and the ability to augment,
clarify, and enhance the original contribution in accordance with the IETF
Standards Process.

The first choice may be appropriate when republishing standards produced by a
standards body other than the IETF, industry consortia, or companies. These are
typically published as Informational RFCs and do not require that change
control be ceded to the IETF. Documents of this type convey information for the
Internet community.

The second choice may be used on I-Ds that are intended to provide background
information to educate and to facilitate discussions within IETF working groups
but are not intended to be published as RFCs.

If you think that you, your company, or anyone else owns a patent or other
Intellectual Property Rights (IPR) on the work described in the I-D, you should
carefully read [BCP 79].  The first notice required in an I-D, described
earlier in this section, obligates you to send an IPR disclosure statement
under certain circumstances.  In particular, when preparing a document intended
to be included in the IETF Stream, before submitting the I-D, discussing it
with the working group chairs or Area Directors is advised.

#### Abstract

Every Internet-Draft must have an Abstract section. The Abstract should provide
a concise and comprehensive overview of the purpose and contents of the entire
document. Its purpose is to give a technically knowledgeable reader a general
overview of the function of the document, to decide whether reading it will be
useful. In addition to its function in the document, the Abstract section is
used as a summary in publication announcements and in the online index of I-Ds
[INDEX].

Composing a useful Abstract is a non-trivial writing task. Often, a
satisfactory abstract can be constructed in part from material from the
Introduction section, but a good abstract will be shorter, less detailed, and
broader in scope than the Introduction. Simply copying and pasting the first
few paragraphs of the Introduction is tempting, but it generally results in an
Abstract that is both incomplete and redundant.  An Abstract will typically be
five to ten lines.  An Abstract of more than 20 lines or fewer than three lines
is generally not acceptable.

- [ ] Ensure the Internet-Draft contains an appropriate Abstract.

An Abstract should be complete in itself, so it should not contain no citations
unless they are completely defined within the Abstract. Abbreviations appearing
in the Abstract should generally be expanded in parentheses. There is a set of
reasonable exceptions to this rule; for example, readers don't need to be
reminded of what "IP" or "TCP" or "MIB" means. The RFC Editor maintains a list
of approved abbreviations that do not need to be expanded [ABBREV]. In the end,
this is a judgment call, but please err on the side of explicitness.

- [ ] Verify that the Abstract stands alone.
- [ ] Ensure abbreviations in the Acronym are expanded as appropriate.
- [ ] If the I-D intends to obsolete or update a previous RFC, ensure the
      Abstract says so explicitly.

[RFC 7322] includes further guidance about writing an Abstract section.

#### Introduction

- [ ] If the I-D intends to obsolete or update a previous RFC, ensure the
      Introduction briefly explains what is being updated and why.

#### Security Considerations

[RFC 3552] provides current best guidance about writing a Security
Considerations section.  This section is mandatory in all documents.

The text of this section must have a meaningful exploration of security issues
raised by the proposal, which should include both risks and da description of
solutions or workarounds.  It is rare that technical work can legitimately make
a claim like "This protocol introduces no security considerations," so it needs
to be fairly obvious for that to be believable, or the document will be
returned for further development.  Procedural documents, however, more commonly
can claim no added security risk.

Some other references that may be useful when crafting this section are:

  * Security glossary v2 [RFC 4949]
  * Use of IPsec v2 [RFC 5406]
  * Guidelines for Authors and Reviewers of MIB documents [RFC 4181]
  * YANG Security Considerations [YANG-SEC]

- [ ] Verify that a meaningful Security Consideration section is present

#### IANA Considerations

This section must be present to enumerate any actions IANA must take upon
publication of the document as an RFC.

- [ ] Verify this section contains clear instructions if IANA is expected
      to create a new registry or modify rules for an existing registry.

- [ ] Verify this section contains clear instructions if the document
      requires IANA to assign or update values in an IANA registry before
      RFC publication.

- [ ] Check the existing IANA registry for registration policy rules
      and any requirements for specific requests for registration of
      protocol parameters.  Individual RFCs have specific criteria and
      instructions that should be followed.

- [ ] If the registration policy is "Expert Review" or "Specification
      Required" and/or requires mailing list review, as soon as the
      requested parameter information is properly formed, consider
      initiating reviews with IANA or sending to the appropriate mailing
      list (where applicable; see the RFC for that the registry for
      instructions).  If there are any questions about what type of approval
      is needed from the Designated Expert (for example, if the registration
      should be made immediately or only pre-reviewed before publication),
      please contact IANA.

- [ ] If registrations are needed early for registries with "Specification
      Required", "RFC Required", "IETF Review", or "Standards Action" policies,
      consider using the early allocation process defined in [RFC 7120].

- [ ] Verify this section explicitly and clearly identifies any references
      to this document that should be added for any registrations and any
      that should replace existing references.

- [ ] If there is no action for IANA, verify that this section explicitly says
      “This document has no IANA actions.” It is often helpful for the IANA
      Considerations section to remain in place upon publication as an RFC
      even if there are no actions.

- [ ] If the document has considerable instructions for IANA actions, request
      an early review of the document by IANA.

For more specific guidelines regarding structure and content for writing IANA
Considerations sections, please see [RFC 8126] and [IANA].

#### Summary of Changes

As noted in the Abstract and Introduction sections above, the Abstract
and Introduction must call out any RFCs an I-D intends to obsolete
or update. There should also be a section providing greater detail about
the changes

- [ ] Ensure the I-D clearly summarizes any changes made from the RFCs
      being updated or obsoleted.

- [ ] Ensure any errata against RFCs that are being obsolated or updated
      have been considered, and that the I-D clearly identifies those that
      have been addressed.

#### References

A References section must be present and split into normative and informative
sections.  For guidance, see [RFC 7322] and [REFERENCE].

Normative and informative references to non-IETF documents are permitted.
However, it is best to minimize such normative references, because assessing
their status when the IETF document advances on the standards track is very
difficult. It is important to use the exact title, author name(s),
organization  and publication date. External specifications referenced by
Internet-Standard-level Technical Specifications or Applicability Statements
must be to open external standards, per [RFC 2026].

- [ ] Ensure all needed references are present, and correctly identified
      as normative or informative.

- [ ] Verify that references is stable and resolvable.

       A bare URI is not generally considered a stable reference.  For web-only
       documents, adding a reference number, title , and/or an author will help
       make the reference more stable.  See [RFC 7322] for specific guidance
       about URIs in Internet-Drafts.  Judgment can be used here; the stability
       of normative references is even more important than the stability of
       informative references.

- [ ] Verify that references to other Internet-Drafts use this format:
      author, "title", name-version (work in progress), date. For instance:

        Foo, "The Specific Subject", draft-foo-bar-specific-subject-00 (work
        in progress, April 2021.

Note that normative references to I-Ds will cause the referencing document to
wait in the RFC Editor queue for the referenced I-Ds to be published as RFCs.
They may in some cases become a cluster of documents [CLUSTER] that will be
published as RFCs simultaneously.

#### Authors' Addresses

- [ ] Verify that the I-D contains a section giving the name and contact
      information (postal mail, phone, and/or email) for the authors.

### Content Considerations

#### Normative Language

If [BCP 14] language (MUST, SHOULD, etc.) is used, the guidelines in RFC 2119,
especially those in Sections 6 and 7, should be followed. "SHOULD" is
especially problematic: it needs to be clear why SHOULD is used rather than
MUST, and what the implications are of varying from the recommendation.

#### Formal Languages

- [ ] Verify that any use of formal languages conforms with the IESG statement
      on the use of formal languages [IESG-FORMAL].

Some particular points to observe are enumerated below.

##### MIB modules

All MIB modules should have correct syntax, so they should compile cleanly
using the “smilint” tool, e.g.:

          smilint -m -s -l 6 -i namelength-32

An online service is available for MIB syntax checking at [LIBSMI]. This
allows you to extract the MIB module from a document for your own local use,
but you can also directly run a syntax check.

You can also download the libsmi tools for local use. In most cases , there
should be no errors or warnings present in the report. Please evaluate all
diagnostic messages before assuming that they are OK. If in doubt, feel free
to check on the ietfmibs@ietf.org mailing list or with the OPS ADs.

- [ ] Ensure that MIB modules compile cleanly

- [ ] Verify that I-D follows the guidelines in [RFC 4181] as updated by [RFC
      4841].

##### ABNF

- [ ] Ensure all ABNF in the I-D compiles cleanly. A tool is available at
      [ABNF-CHECK]. See [RFC 5234] for information about IETF ABNF.

- [ ] If ABNF is used, ensure the I-D contains a normative reference to
      [RFC 5234].

##### XML

Protocol specifications that use XML should always use well-formed XML at a
minimum. Sample XML instances included in a specification have to be
well-formed, and if the XML is supposed to be valid (according to the current
W3C definition of validity), the samples must reference and be validated using
an appropriate XML Schema, DTD, or another standard validation mechanism that
is structurally and syntactically correct.

Links to tools to check XML validity, including a schema checker and a
validating parser, can be found at [XML-CHECK].

Other guidelines for the use of XML in IETF protocols can be found in BCP 70
[RFC 3470].

- [ ] Verify that any XML in the I-D is well-formed, and if it is intended to
      be valid, confirm that it validates against the appropriate definition.

XML provides structures, such as the "<any>" element information item in XML
Schema, to allow element extensions.

- [ ] Ensure the I-D contains clear guidance on how, when, and where any
      extension structures, such as versioning, can be used.

- [ ] Check that any new or updated XML Schemas, Namespaces, and Resource
      Description Framework (RDF) Schemas are being registered with IANA using
      the procedures described in BCP 81 [RFC 3688].

#### Example Addresses

- [ ] Verify that examples use example FQDNs whenever possible

        Addresses used in examples should use fully qualified domain names
        instead of literal IP addresses, and should use example FQDNs such as
        "foo.example.com" instead of real-world FQDNs.  See [RFC 2606] for
        example domain names that can be used.  Note that the entire
        “.example” TLD is reserved, allowing for arbitrary subdomains (in
        particular, ones that are not considered same-origin on the Web).

- [ ] Verify that literal IP addresses are from the example ranges

        There are also ranges of IP addresses set aside for this purpose.  For
        IPv4, these are defined in [RFC 6890]; for IPv6, see [RFC 3849]. Per
        the IAB Statement on IPv6 [IAB-IPV6], IPv6 examples should be used.

- [ ] Verify that private addresses that would be used in the real world
      are not used in examples.

- [ ] Verify that real telephone numbers are not used in examples.

        Use those numbers that were reserved for examples or fictitious use.
        Available numbers for use in examples are:

          UK: +44-<geographic-area-code>-496-<0000-0999>
          USA: +1-<area code>-555-<0100-0199> (see
               https://www.nationalnanpa.com/pdf/NRUF/ATIS-0300115.pdf)

## Format

## References

[CLUSTER](https://www.rfc-editor.org/about/clusters/)

[ID-REMOVAL](https://www.ietf.org/about/groups/iesg/statements/internet-draft-removal/)

## Acknowledgments

This document is based heavily on the work of Russ Housley, Ben Kaduk,
Murray Kucherawy, Alvaro Retana, and the members of many IESGs.
