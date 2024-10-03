# NIAD-2872 Analysis
## FHIR Resources
### AllergyIntolerance
#### The `recorder` field

* *PS Adaptor* - The `recorder` field is mapped from the `ObservationStatement / Author` field. If the `Author` value is not provided, it is taken from the `Participant` field, referencing the mapped [Practitioner](https://github.com/NHSDigital/patient-switching-adaptors-mapping-documentation/blob/main/practitioners/README.md).
* *GPC 1.6.0* - [Who recorded the allergy in the clinical system](https://developer.nhs.uk/apis/gpconnect-1-6-0/accessrecord_structured_development_allergyintolerance.html#recorder).

#### The `asserter` field

* *PS Adaptor* - The `asserter` field is a reference to the mapped [Practitioner](https://github.com/NHSDigital/patient-switching-adaptors-mapping-documentation/blob/main/practitioners/README.md).
* *GPC 1.6.0* - [Source of the information about the allergy](https://developer.nhs.uk/apis/gpconnect-1-6-0/accessrecord_structured_development_allergyintolerance.html#asserter).

⚠️ **Note** - The description provided by the PS adaptor in its mapping documentation for the `asserter` field appears to contrast with the definition outlined in the GPC 1.6.0 standard for the `asserter` field within the `AllergyIntolerance` resource. This discrepancy warrants further clarification to ensure alignment with established standards.

### ReferralRequest

#### The `requester.agent` field

* *PS Adaptor* - reference to mapped [Practitioner](https://github.com/NHSDigital/patient-switching-adaptors-mapping-documentation/blob/main/practitioners/README.md) from `RequestStatement / Participent / agentRef` or `Composition / Participent / agentRef`.
* *GPC 1.6.0* - [The preferred agent is the practitioner responsible for the decision to refer the patient. If the referral is not attributed to a practitioner, then any of the other resource options **MAY** be used as most appropriate. If the referral does not clearly identify responsibility for the referral decision or action, this **MUST** be the user who recorded the referral](https://developer.nhs.uk/apis/gpconnect-1-6-0/accessrecord_structured_development_referralrequest.html#requesteragent).

#### The `recipient` field

* *PS Adaptor* - reference to mapped [Practitioner](https://github.com/NHSDigital/patient-switching-adaptors-mapping-documentation/blob/main/practitioners/README.md) or [Organization](https://github.com/NHSDigital/patient-switching-adaptors-mapping-documentation/blob/main/organizations/README.md) from `RequestStatement / responsibleParty / agentRef`.
* *GPC 1.6.0* - [This **MUST** be populated with the practitioner and/or organisation the patient has been referred to, if that is recorded in a suitable coded format. If the referral recipient details are in a form which cannot be returned as a referenced resource, the details **MUST** be populated to the `note` as key value pairs](https://developer.nhs.uk/apis/gpconnect-1-6-0/accessrecord_structured_development_referralrequest.html#recipient).