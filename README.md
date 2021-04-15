# Guidelines to Authors of Internet-Drafts

## Table of Contents
  * [Introduction](#introduction)
  * [Background](#background)
  * [Internet-Draft Names](#internet-draft-names)
  * [The Submission Process](#the-submission-process)
  * [Content Considerations](#content-considerations)
    * [Required Content](#required-content)
  * [Format Considerations](#format-considerations)
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
component makes it hard to extract programatically. This forces many tools
to use heuristics when tying to locate the second component.


- [ ] Ensure the second component reasonably identifees the source of the I-D.

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

- [ ] Ensure adopted or group targetted I-Ds identify the group just after the
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

## Content Considerations

### Required Content

## Format Considerations

## References

[ID-REMOVAL](https://www.ietf.org/about/groups/iesg/statements/internet-draft-removal/)

## Acknowledgments

This document is based heavily on the work of Russ Housley, Ben Kaduk, 
Murray Kucherawy, Alvaro Retana, and the members of many IESGs.
