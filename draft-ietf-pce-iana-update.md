---
title: "Update to the IANA PCE Communication Protocol (PCEP) Registration Procedures and Allowing Experimental Error Codes"
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
updates: 5440, 8231, 8233, 8281, 8623, 8664, 8685, 8697, 8745, 8733, 8779, 8780, 8800, 8934, 9050, 9059, 9168, 9357, 9504, 9603, 9604

author:
 -
  ins: D. Dhody
  name: Dhruv Dhody
  org: Huawei
  country: IN
  email: dhruv.ietf@gmail.com
 -
  ins: A. Farrel
  name: Adrian Farrel
  org: Old Dog Consulting
  email: adrian@olddog.co.uk

normative:
  RFC5440:
  RFC8126:
  RFC8231:
  RFC8233:
  RFC8281:
  RFC8356:
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
  RFC9604:
informative:
  RFC3692:
  RFC6709:
  I-D.ietf-pce-pceps-tls13:


--- abstract

This document updates the registration procedure within the IANA "Path Computation Element Protocol (PCEP) Numbers" group of registries. This specification changes some of the registries with Standards Action to IETF Review as defined in RFC 8126.  This memo updates RFCs 8231, 8233, 8281, 8623, 8664, 8685, 8697, 8733, 8745, 8779, 8780, 8800, 8934, 9050, 9059, 9168, 9357, 9504, 9603, and 9604 for the same.

Designating "experimental use" sub-ranges within code point registries is often beneficial for protocol experimentation in controlled environments. Although the registries for PCEP messages, objects, and TLV types have sub-ranges assigned for Experimental Use, the registry for PCEP Error-Types and Error-values currently does not. This document updates RFC 5440 by designating a specific range of PCEP Error-Types for Experimental Use.


--- middle

# Introduction

The IANA "Path Computation Element Protocol (PCEP) Numbers" registry group was populated by several RFCs produced by the Path Computation Element (PCE) working group. Most of the registries include the "IETF Review" {{RFC8126}} as registration procedures. There are a few registries that use "Standards Action". Thus, the values in those registries can be assigned only through the Standards Track or Best Current Practice RFCs in the IETF Stream. This memo changes the policy from Standards Action to IETF Review to allow any type of RFC under the IETF stream to make the allocation request.

Further, in Section 9 of {{RFC5440}}, IANA assigns values to the PCEP parameters.  The allocation policy for each of these parameters specified in RFC 5440 is IETF Review {{RFC8126}}. In consideration of the benefits of conducting experiments with PCEP and the utility of experimental codepoints {{RFC3692}}, codepoint ranges for PCEP messages, objects, and TLV types for Experimental Use {{RFC8126}} are designated in {{RFC8356}}. However, protocol experiments may also need to return protocol error messages indicating experiment-specific error cases.  It will often be the case that previously assigned error codes (in the PCEP-ERROR Object Error Types and Values sub-registry) can be used to indicate the error cases within an experiment, but there may also be cases where new, experimental error codes are needed. In order to run experiments, it is important that the codepoint values used in the experiments do not collide with existing codepoints or any future allocations. This document updates {{RFC5440}} by changing the allocation policy for the registry of PCEP Error-Types to mark some of the codepoints as assigned for Experimental Use.  As stated in {{RFC3692}}, experiments using these codepoints are not intended to be used in general deployments, and due care must be taken to ensure that two experiments using the same codepoints are not run in the same environment.

# Standards Action PCEP Registries Affected

The following table lists the "Path Computation Element Protocol (PCEP) Numbers" registries whose registration policy will be changed from Standards Action to IETF Review. Affected registries will list this document as a reference. Where this change is applied to a specific range of values within the particular registry, that range is given in the Remarks column.

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
| TE-PATH-BINDING TLV Flag Field | {{RFC9604}} | |
| LSP-EXTENDED-FLAG TLV Flag Field | {{RFC9357}} | |
| LSP Exclusion Subobject Flag Field | {{RFC9504}} | |
| SRv6-ERO Flag Field | {{RFC9603}} | |
| SRv6 Capability Flag Field | {{RFC9603}} | |
{: title="PCEP Registries Affected"}

Future registries in the "Path Computation Element Protocol (PCEP) Numbers" registry group should prefer to use "IETF Review" over "Standards Action".

# Experimental Error-Types

This document requests IANA for the designation of four PCEP Error-Type codepoints (252-255) for Experimental Use.

IANA maintains a registry group called "Path Computation Element Protocol (PCEP) Numbers" with a registry named "PCEP-ERROR Object Error Types and Values".  IANA is requested to change the assignment policy for this registry to read:

- Error-Types
  - 0-251 : IETF Review
  - 252-255 : Experimental Use
- Error-value
  - For all IETF Review Error-Types : IETF Review
  - For all Experimental Use Error-Types : Experimental Use

Additionally, IANA is requested to make an entry in the table as follows:

| Error-Type | Meaning             | Error-value       | Reference |
| :---     |    :----:       |    :----:  |               ---: |
| 252-255    | Experimental Use | 0-255 Experimental Use | This I-D |

## Advice on Experimentation

An experiment that wishes to return experimental error codes should use one of the experimental Error-Type values as defined in this document. The experiment should agree, between all participating parties, on which Error-Type to use and which Error-values to use within that Error-Type. The experiment will describe what the meanings of those Error-Type / Error-value pairs are. Those Error-Type and Error-values should not be recorded in any public (especially any IETF) documentation. Textual or symbolic names for the Error-Types and Error-values may be used to help keep the documentation clear.

If multiple experiments are taking place at the same time using the same implementations, care must be taken to keep the sets of Error-Type / Error-value distinct.

Note that there is no scope for experimental Error-values within existing non-experimental Error-Types. This reduces the complexity of the registry and implementations. Experiments should place all experimental Error-values under the chosen experimental Error-Types.

If, at some future time, the experiment is declared a success and moved to IETF work targeting publication on the Standards Track, each pair of Error-Type / Error-value will need to be assigned by IANA from the registry. In some cases, this will involve assigning a new Error-Type with its subtended Error-values. In other cases, use may be made of an existing Error-Type with new subtended Error-values being assigned. The resulting change to code in an implementation is as simple as changing the numeric values of the Error-Types and Error-values.

## Handling of Unknown Experimentation

A PCEP implementation that receives an experimental Error-Type in a PCEP message and does not recognize the Error-Type (i.e., is not part of the experiment) will treat the error as it would treat any other unknown Error-Type (such as from a new protocol extension). An implementation that is notified of a PCEP error will normally close the PCEP session (see [RFC5440]). In general, PCEP implementations are not required to take specific action based on Error-Types but may log the errors for diagnostic purposes.

An implementation that is part of an experiment may receive an experimental Error-Type, but not recognize the Error-value. This could happen because of any of:

- A faulty implementation.
- Two implementations not being synchronized with respect to which Error-values to use in the experiment.
- More than one experiment being run at the same time.

As with unknown Error-Types, an implementation receiving an unknown Error-value is not expected to do more than log the received error and may close the PCEP session.

# IANA Considerations

This memo is entirely about updating the IANA "Path Computation Element Protocol (PCEP) Numbers" registry.

# Security Considerations

This memo does not change the Security Considerations for any of the updated RFCs. Refer to {{RFC5440}} and {{I-D.ietf-pce-pceps-tls13}} for further details of the specific security measures applicable to PCEP.

{{RFC3692}} asserts that the existence of experimental codepoints introduces no new security considerations. However, implementations accepting experimental error codepoints need to consider how they parse and process them in case they come, accidentally, from another experiment. Further, an implementation accepting experimental codepoints needs to consider the security aspects of the experimental extensions. {{RFC6709}} provides various design considerations for protocol extensions (including those designated as experimental).


--- back

# Acknowledgments

Thanks to John Scudder for the initial discussion behind this document. Thanks to Ketan Talaulikar, Andrew Stone, Samuel Sidor, Quan Xiong, Cheng Li, and Aijun Wang for the review comments. Thanks to Carlos Pignataro for the OPSDIR review. Thanks to Meral Shirazipour for GENART review. Thanks to Paul Kyzivat for ArtArt review. Thanks to Alexey Melnikov for SECDIR review.

# Rationale for updating all registries with Standards Action

This specification updates all the registries with the "Standards Action" policy. WG considered keeping "Standards Action" for some registries such as flag fields with limited bits, where the space is tight but decided against it. The WG's last call and IETF's last call process should be enough to handle the case of frivolous experiments taking over the few code points. The working group could also create a new protocol field and registry for future use as done in the past (see {{RFC9357}}).

# Consideration of RFC 8356

It is worth noting that {{RFC8356}} deliberately chose to make experimental codepoints available only in the PCEP messages, objects, and TLV type registries.  Appendix A of that document gives a brief explanation of why that decision was taken stating that:

{:quote}
> The justification for this decision is that, if an
> experiment finds that it wants to use a new codepoint in another PCEP
> sub-registry, it can implement the same function using a new
> experimental object or TLV instead.

While it is true that an experimental implementation could assign an experimental PCEP object and designate it the "experimental errors object", using it to carry arbitrary contents including experimental error codes, such an approach would cause unnecessary divergence in the code.  The allowance of experimental Error-Types is a better approach that will more easily enable the migration of successful experiments onto the Standards Track.

# Contributor

Haomian Zheng <br />
Huawei Technologies <br />
Email: zhenghaomian@huawei.com <br />
