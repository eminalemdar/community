---
resource:
  apiVersion: v1alpha1
  description: ModelSpec defines the desired state of Model
  group: apigatewayv2.services.k8s.aws
  name: Model
  names:
    kind: Model
    listKind: ModelList
    plural: models
    singular: model
  scope: Namespaced
  service: apigatewayv2
  spec:
  - contains: null
    contains_description: null
    description: ''
    name: apiID
    required: true
    type: string
  - contains: null
    contains_description: null
    description: ''
    name: contentType
    required: false
    type: string
  - contains: null
    contains_description: null
    description: ''
    name: description
    required: false
    type: string
  - contains: null
    contains_description: null
    description: ''
    name: name
    required: true
    type: string
  - contains: null
    contains_description: null
    description: ''
    name: schema
    required: true
    type: string
  status:
  - contains:
    - contains: null
      contains_description: null
      description: 'ARN is the Amazon Resource Name for the resource. This is a globally-unique
        identifier and is set only by the ACK service controller once the controller
        has orchestrated the creation of the resource OR when it has verified that
        an "adopted" resource (a resource where the ARN annotation was set by the
        Kubernetes user on the CR) exists and matches the supplied CR''s Spec field
        values. TODO(vijat@): Find a better strategy for resources that do not have
        ARN in CreateOutputResponse https://github.com/aws/aws-controllers-k8s/issues/270'
      name: arn
      required: false
      type: string
    - contains: null
      contains_description: null
      description: OwnerAccountID is the AWS Account ID of the account that owns the
        backend AWS service API resource.
      name: ownerAccountID
      required: true
      type: string
    contains_description: null
    description: All CRs managed by ACK have a common `Status.ACKResourceMetadata`
      member that is used to contain resource sync state, account ownership, constructed
      ARN for the resource
    name: ackResourceMetadata
    required: true
    type: object
  - contains:
    - contains: null
      contains_description: null
      description: Last time the condition transitioned from one status to another.
      name: lastTransitionTime
      required: false
      type: string
    - contains: null
      contains_description: null
      description: A human readable message indicating details about the transition.
      name: message
      required: false
      type: string
    - contains: null
      contains_description: null
      description: The reason for the condition's last transition.
      name: reason
      required: false
      type: string
    - contains: null
      contains_description: null
      description: Status of the condition, one of True, False, Unknown.
      name: status
      required: false
      type: string
    - contains: null
      contains_description: null
      description: Type is the type of the Condition
      name: type
      required: false
      type: string
    contains_description: Condition is the common struct used by all CRDs managed
      by ACK service controllers to indicate terminal states  of the CR and its backend
      AWS service API resource
    description: All CRS managed by ACK have a common `Status.Conditions` member that
      contains a collection of `ackv1alpha1.Condition` objects that describe the various
      terminal states of the CR and its backend AWS service API resource
    name: conditions
    required: true
    type: array
  - contains: null
    contains_description: null
    description: ''
    name: modelID
    required: false
    type: string
---
{% include "reference.md" %}