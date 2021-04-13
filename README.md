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

Internet-Drafts are used by all of the RFC Streams [RFC 8279]. The guidance in
this document applies to all streams unless it is identified as specific to a
particular stream.

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
review by the Independent Series Editor (ISE) for publication in the Independent
Submission Stream.

Internet-Drafts are not removed from the Archive when they are removed from
the Repository. Removing an I-D from the Archive occurs only in exceptional
circumstances, described in this IESG Statement [ID-REMOVAL].

Even though Internet-Drafts are kept in the Archive, they are not an archival
series, and should not be cited or quoted as anything other than "work in
progress".

## Internet-Draft Names



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

The submission tool will double-check many, but not all, of the guidance
points called out in this document. Authors are expected to have manually
applied the guidance before submission.

While many of the requirements pointed to by this document are for RFCs,
Internet-Drafts are expected to adhere to them to the extent possible. In
particular, IETF stream I-Ds submitted to the IESG for must follow all of the
guidance. Working groups are encouraged to require the guidance be followed for
I-Ds entering Working Group Last Call. I-Ds will progress through the review
and publication process more efficiently the earlier the guidance is followed
in the I-D.

If authors are unable to submit an I-D through the Datatracker, they may make a
manual-post request by sending the I-D via email to support@ietf.org.  The
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

This document is based heavily on the work of Russ Housley, Ben Kaduk, Murray Kucherawy, Alvaro Retana, and the members of many IESGs.
