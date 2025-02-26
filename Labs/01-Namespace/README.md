![](../../resources/k8s-logos.png)

# K8S Hands-on

![Visitor Badge](https://visitor-badge.laobi.icu/badge?page_id=nirgeier)

---

# Namespaces

- Kubernetes supports **multiple virtual clusters** backed by the same **physical cluster**.
- These virtual clusters are called namespaces.
- Namespaces are the default way for Kubernetes to separate resources.
- Using name spaces we can isolate the development, improve security and more.
- Kubernetes clusters has a build in namespace called **default** and might contain more namespaces like like `kube-system` for example.

<!-- inPage TOC start -->

---
## Lab Highlights:
- [K8S Hands-on](#k8s-hands-on)
- [Namespaces](#namespaces)
  - [Lab Highlights:](#lab-highlights)
    - [Pre-Requirements](#pre-requirements)
    - [01. Create Namespace](#01-create-namespace)
    - [01.01. Create Namespace](#0101-create-namespace)
    - [02. Setting the default Namespace for `kubectl`](#02-setting-the-default-namespace-for-kubectl)
    - [03. Verify that you've updated the namespace](#03-verify-that-youve-updated-the-namespace)
    - [Note:](#note)

---

<!-- inPage TOC end -->

### Pre-Requirements

- K8S cluster - <a href="../00-VerifyCluster">Setting up minikube cluster instruction</a>

[![Open in Cloud Shell](https://gstatic.com/cloudssh/images/open-btn.svg)](https://console.cloud.google.com/cloudshell/editor?cloudshell_git_repo=https://github.com/nirgeier/KubernetesLabs)  
**<kbd>CTRL</kbd> + <kbd>click</kbd> to open in new window**

---

### 01. Create Namespace

### 01.01. Create Namespace

```sh
# In this sample `codewizard` is the desired name space
$ kubectl create namespace codewizard
namespace "codewizard" created

### !!! Try to create the following name space (with _ & -):
$ kubectl create namespace my_namespace-
```

### 02. Setting the default Namespace for `kubectl`

- To set the default namespace run:

```sh
$ kubectl config set-context $(kubectl config current-context) --namespace=codewizard

Context minikube modified.
```

### 03. Verify that you've updated the namespace

```sh
$ kubectl config get-contexts
CURRENT     NAME                 CLUSTER          AUTHINFO         NAMESPACE
            docker-desktop       docker-desktop   docker-desktop
            docker-for-desktop   docker-desktop   docker-desktop
*           minikube             minikube         minikube         codewizard
```

### Note:

- When using `kubectl` you can pass the `-n` flag in order to execute the `kubectl` command on a desired namespace
- For example:

```sh
# get resources of a specific workspace
$ kubectl get pods -n <namespace>
```

<!-- navigation start -->

---

<div align="center">

  [:arrow_left: &nbsp; 00-VerifyCluster](../00-VerifyCluster)&nbsp;&nbsp;||&nbsp;&nbsp;
  [02-Deployments-Imperative &nbsp; :arrow_right:](../02-Deployments-Imperative)
</div>

---

<div align="center">
  <small>&copy;CodeWizard LTD</small>
</div>

![Visitor Badge](https://visitor-badge.laobi.icu/badge?page_id=nirgeier)

<!-- navigation end -->
