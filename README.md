# openshift2microshift-resource-mapping

Recently I was approached with the task of understanding what were the resource differences between OpenShift and MicroShift.  This is especially important if one is interested in applying governance policies and rules across a fleet of systems that might be a mix of both OpenShift and MicroShift.  Knowing the availability of specific resource definitions that might be common or disparate between the two Kubernetes experience can help an administrator know if they can use the same policy across both instances or if they need to specifically craft a policy for one or the other.  Given that this information might be important for administrators I decided to map it out.

Below is a table that shows the resource definition and then if defined in OpenShift, MicroShift or both, the corresponding API version.

| OpenShift Resource | API Version | Microshift Resource | API Version |
| ------------------ | ----------- | ------------------- | ----------- |
| alertmanagerconfigs | monitoring.coreos.com/v1alpha1, | NA | NA |

