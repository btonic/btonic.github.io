---
layout: post
title: Hiding in plain sight 🙈 - Abusing Kubernetes resource definition semantics
---

# TL;DR
Within Kubernetes, all resources and their configuration are represented as
objects. At a high level, a cluster administrator creates a resource
definition object, the object is merged into cluster state and persisted,
and the cluster components change their state to represent the persisted cluster
state. This workflow allows for complex state to be managed with relative ease because
resource definition objects no longer require an "order of operations." The expectation
is that the components of the cluster will reflect the cluster state, resulting
in the administrator's configuration intentions. If the cluster components
cannot reflect the cluster state, errors will be bubbled up to the operator.

However, the same semantics that make managing cluster resources easier, can
also come back to haunt us. In this writeup we will be covering basics of Custom
Resource Definitions, how they are typically used, and most importantly, how we
can abuse them. In the examples of abuse, we will be using Pod resource
definitions as a testbench resource definition. Other types of Custom Resource
Definitions may be possible to abuse using these techniques.

It is notable, these examples do require some level of control plane access by
an abuser, whether direct or indirect. The exact requirements may vary by
example.

# A day in the life of a CRD
## Defining a CRD
* What is a CRD
* CRD field validation

## Creating a CRD object
* Kubectl <-> kube-api

## Admission and validation of submitted CRD objects
* Kubectl <-> kube-api <-> \(ValidatingWebhook \| MutatingWebhook\)

## Indirect resource references
* fields which reference other objects by identifier

# Pods, sets, and deployments

# 






```go
function() {
    fmt.Println("test");
}
```