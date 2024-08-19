---
title: "Update to the IANA PCEP Registration Procedures"
abbrev: "PCEP-IANA"
category: std

docname: draft-ietf-pce-iana-update-latest
submissiontype: IETF  # also: "independent", "editorial", "IAB", or "IRTF"
number:
date: {DATE}
consensus: true
v: 3
area: "Routing"
workgroup: "Path Computation Element"
updates: 8231, 8233, 8281, 8623, 8664, 8685, 8697, 8745, 8733, 8779, 8780, 8800, 8934, 9050, 9059, 9168, 9357, 9504, 9603

author:
 -
  ins: D. Dhody
  name: Dhruv Dhody
  org: Huawei
  country: IN
  email: dhruv.ietf@gmail.com

normative:
  RFC8126:
  RFC8231:
  RFC8233:
  RFC8281:
  RFC8623:
  RFC8664:
  RFC8685:
  RFC8697:
  RFC8733:
  RFC8745:
  RFC8779:
  RFC8780:
  RFC8800:
  RFC8934:
  RFC9050:
  RFC9059:
  RFC9168:
  RFC9357:
  RFC9504:
  RFC9603:
  I-D.ietf-pce-binding-label-sid:
informative:


--- abstract

This document updates the registration procedure within the IANA "Path Computation Element Protocol (PCEP) Numbers" group of registries. This specification changes some of the registries with Standards Action to IETF Review as defined in RFC 8126.  This memo updates RFCs 8231, 8233, 8281, 8623, 8664, 8685, 8697, 8733, 8745, 8779, 8780, 8800, 8934, 9050, 9059, 9168, 9357, 9504, and 9603.


--- middle

# Introduction

The IANA "Path Computation Element Protocol (PCEP) Numbers" registry group was populated by several RFCs produced by the Path Computation Element (PCE) working group. Most of the registries include the "IETF Review" {{RFC8126}} as registration procedures. There are a few registries that use "Standards Action". Thus the values in those registries can be assigned only through Standards Track or Best Current Practice RFCs in the IETF Stream. This memo changes the policy from Standards Action to IETF Review to allow any type of RFC under the IETF stream to make the allocation request.

# PCEP Registries Affected

The following table lists the "Path Computation Element Protocol (PCEP) Numbers" registries whose registration policy has changed from Standards Action to IETF Review.   Affected registries now list this document as a reference. Where this change is applied to a specific range of values within the particular registry, that range is given in the Remarks column.

| Registry | RFC             | Remarks       |
| :---     |    :----:       |          ---: |
| BU Object Type Field  | {{RFC8233}} | |
| LSP Object Flag Field | {{RFC8231}} | |
| STATEFUL-PCE-CAPABILITY TLV Flag Field | {{RFC8231}} | |
| LSP-ERROR-CODE TLV Error Code Field | {{RFC8231}} | |
| SRP Object Flag Field | {{RFC8281}} | |
| SR-ERO Flag Field | {{RFC8664}} | |
| PATH-SETUP-TYPE-CAPABILITY Sub-TLV Type Indicators | {{RFC8664}} | |
| SR Capability Flag Field | {{RFC8664}} | |
| WA Object Flag Field | {{RFC8780}} | |
| Wavelength Restriction TLV Action Values | {{RFC8780}} | |
| Wavelength Allocation TLV Flag Field | {{RFC8780}} | |
| S2LS Object Flag Field | {{RFC8623}} | |
| H-PCE-CAPABILITY TLV Flag Field | {{RFC8685}} | |
| H-PCE-FLAG TLV Flag Field | {{RFC8685}} | |
| ASSOCIATION Flag Field | {{RFC8697}} | |
| ASSOCIATION Type Field | {{RFC8697}} | |
| AUTO-BANDWIDTH-CAPABILITY TLV Flag Field | {{RFC8733}} | |
| Path Protection Association Group TLV Flag Field | {{RFC8745}} | |
| Generalized Endpoint Types | {{RFC8779}} | 0-244 |
| GMPLS-CAPABILITY TLV Flag Field | {{RFC8779}} | |
| DISJOINTNESS-CONFIGURATION TLV Flag Field | {{RFC8800}} | |
| SCHED-PD-LSP-ATTRIBUTE TLV Opt Field | {{RFC8934}} | |
| Schedule TLVs Flag Field | {{RFC8934}} | |
| FLOWSPEC Object Flag Field | {{RFC9168}} | |
| Bidirectional LSP Association Group TLV Flag Field | {{RFC9059}} | |
| PCECC-CAPABILITY sub-TLV | {{RFC9050}} | |
| CCI Object Flag Field for MPLS Label | {{RFC9050}} | |
| TE-PATH-BINDING TLV BT Field | {{RFC9050}} | |
| TE-PATH-BINDING TLV Flag Field | {{I-D.ietf-pce-binding-label-sid}} | |
| LSP-EXTENDED-FLAG TLV Flag Field | {{RFC9357}} | |
| LSP Exclusion Subobject Flag Field | {{RFC9504}} | |
| SRv6-ERO Flag Field | {{RFC9603}} | |
| SRv6 Capability Flag Field | {{RFC9603}} | |
{: title="PCEP Registries Affected"}

~~~
Question to the WG: The current document updates all
the registries. Should we keep "Standards Action" for
some of them such as flag fields with limited bits?

Rationale: There are some registries where the space
is tight but the IETF-review is fine -- our WG and
LC process should be enough to handle the case of fewer
bits which ideally require creating a new field/registry
as we did in the past.
~~~

# Security Considerations

This memo does not change the Security Considerations for any of the updated RFCs.

# IANA Considerations

This memo is entirely about updating the IANA "Path Computation Element Protocol (PCEP) Numbers" registry.


--- back

# Acknowledgments

Thanks to John Scudder for the initial discussion behind this document.
