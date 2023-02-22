# **OpenShift to MicroShift Resource Mapping**

Recently I was approached with the task of understanding what were the resource differences between OpenShift and MicroShift.  This is especially important if one is interested in applying governance policies and rules across a fleet of systems that might be a mix of both OpenShift and MicroShift.  Knowing the availability of specific resource definitions that might be common or disparate between the two Kubernetes experience can help an administrator know if they can use the same policy across both instances or if they need to specifically craft a policy for one or the other.  Given that this information might be important for administrators I decided to map it out.

Below is a table that shows the resource definition and then if defined in OpenShift, MicroShift or both, the corresponding API version.

| OpenShift Resource | API Version | Microshift Resource | API Version |
| ------------------ | ----------- | ------------------- | ----------- |
| alertmanagerconfigs | monitoring.coreos.com/v1alpha1, monitoring.coreos.com/v1beta1  | NA | NA   |
| alertmanagers | monitoring.coreos.com/v1   | NA | NA   |
| apirequestcounts | apiserver.openshift.io/v1   | NA | NA   |
| apiservers | config.openshift.io/v1   | NA | NA   |
| apiservices | apiregistration.k8s.io/v1   | apiservices | apiregistration.k8s.io/v1   |
| appliedclusterresourcequotas | quota.openshift.io/v1   | NA | NA   |
| authentications | config.openshift.io/v1, operator.openshift.io/v1  | NA | NA   |
| baremetalhosts | metal3.io/v1alpha1   | NA | NA   |
| bmceventsubscriptions | metal3.io/v1alpha1   | NA | NA   |
| brokertemplateinstances | template.openshift.io/v1   | NA | NA   |
| buildconfigs | build.openshift.io/v1   | NA | NA   |
| builds | build.openshift.io/v1, config.openshift.io/v1  | NA | NA   |
| catalogsources | operators.coreos.com/v1alpha1   | NA | NA   |
| certificatesigningrequests | certificates.k8s.io/v1   | certificatesigningrequests | certificates.k8s.io/v1   |
| cloudcredentials | operator.openshift.io/v1   | NA | NA   |
| clusterautoscalers | autoscaling.openshift.io/v1   | NA | NA   |
| clustercsidrivers | operator.openshift.io/v1   | NA | NA   |
| clusteroperators | config.openshift.io/v1   | NA | NA   |
| clusterresourcequotas | quota.openshift.io/v1   | NA | NA   |
| clusterrolebindings | authorization.openshift.io/v1, rbac.authorization.k8s.io/v1  | clusterrolebindings | rbac.authorization.k8s.io/v1   |
| clusterroles | authorization.openshift.io/v1, rbac.authorization.k8s.io/v1  | clusterroles | rbac.authorization.k8s.io/v1   |
| clusterserviceversions | operators.coreos.com/v1alpha1   | NA | NA   |
| clusterversions | config.openshift.io/v1   | NA | NA   |
| componentstatuses | v1   | componentstatuses | v1   |
| configmaps | v1   | configmaps | v1   |
| configs | imageregistry.operator.openshift.io/v1, operator.openshift.io/v1, samples.operator.openshift.io/v1 | NA | NA   |
| consoleclidownloads | console.openshift.io/v1   | NA | NA   |
| consoleexternalloglinks | console.openshift.io/v1   | NA | NA   |
| consolelinks | console.openshift.io/v1   | NA | NA   |
| consolenotifications | console.openshift.io/v1   | NA | NA   |
| consoleplugins | console.openshift.io/v1alpha1   | NA | NA   |
| consolequickstarts | console.openshift.io/v1   | NA | NA   |
| consoles | config.openshift.io/v1, operator.openshift.io/v1  | NA | NA   |
| consoleyamlsamples | console.openshift.io/v1   | NA | NA   |
| containerruntimeconfigs | machineconfiguration.openshift.io/v1   | NA | NA   |
| controllerconfigs | machineconfiguration.openshift.io/v1   | NA | NA   |
| controllerrevisions | apps/v1   | controllerrevisions | apps/v1   |
| credentialsrequests | cloudcredential.openshift.io/v1   | NA | NA   |
| cronjobs | batch/v1, batch/v1beta1  | cronjobs | batch/v1   |
| csidrivers | storage.k8s.io/v1   | csidrivers | storage.k8s.io/v1   |
| csinodes | storage.k8s.io/v1   | csinodes | storage.k8s.io/v1   |
| csisnapshotcontrollers | operator.openshift.io/v1   | NA | NA   |
| csistoragecapacities | storage.k8s.io/v1, storage.k8s.io/v1beta1  | csistoragecapacities | storage.k8s.io/v1, storage.k8s.io/v1beta1  |
| customresourcedefinitions | apiextensions.k8s.io/v1   | customresourcedefinitions | apiextensions.k8s.io/v1   |
| daemonsets | apps/v1   | daemonsets | apps/v1   |
| deploymentconfigs | apps.openshift.io/v1   | NA | NA   |
| deployments | apps/v1   | deployments | apps/v1   |
| dnses | config.openshift.io/v1, operator.openshift.io/v1  | NA | NA   |
| dnsrecords | ingress.operator.openshift.io/v1   | NA | NA   |
| egressfirewalls | k8s.ovn.org/v1   | NA | NA   |
| egressips | k8s.ovn.org/v1   | NA | NA   |
| egressqoses | k8s.ovn.org/v1   | NA | NA   |
| egressrouters | network.operator.openshift.io/v1   | NA | NA   |
| endpoints | v1   | endpoints | v1   |
| endpointslices | discovery.k8s.io/v1, discovery.k8s.io/v1beta1  | endpointslices | discovery.k8s.io/v1   |
| etcds | operator.openshift.io/v1   | NA | NA   |
| events | v1, events.k8s.io/v1, events.k8s.io/v1beta1 | events | v1, events.k8s.io/v1  |
| featuregates | config.openshift.io/v1   | NA | NA   |
| firmwareschemas | metal3.io/v1alpha1   | NA | NA   |
| flowschemas | flowcontrol.apiserver.k8s.io/v1beta1, flowcontrol.apiserver.k8s.io/v1beta2  | flowschemas | flowcontrol.apiserver.k8s.io/v1beta1, flowcontrol.apiserver.k8s.io/v1beta2  |
| groups | user.openshift.io/v1   | NA | NA   |
| helmchartrepositories | helm.openshift.io/v1beta1   | NA | NA   |
| horizontalpodautoscalers | autoscaling/v1, autoscaling/v2, autoscaling/v2beta1, | horizontalpodautoscalers | autoscaling/v1, autoscaling/v2, autoscaling/v2beta2 |
| hostfirmwaresettings | metal3.io/v1alpha1   | NA | NA   |
| identities | user.openshift.io/v1   | NA | NA   |
| imagecontentpolicies | config.openshift.io/v1   | NA | NA   |
| imagecontentsourcepolicies | operator.openshift.io/v1alpha1   | NA | NA   |
| imagepruners | imageregistry.operator.openshift.io/v1   | NA | NA   |
| images | config.openshift.io/v1, image.openshift.io/v1  | NA | NA   |
| imagesignatures | image.openshift.io/v1   | NA | NA   |
| imagestreams | image.openshift.io/v1   | NA | NA   |
| imagestreamtags | image.openshift.io/v1   | NA | NA   |
| imagetags | image.openshift.io/v1   | NA | NA   |
| infrastructures | config.openshift.io/v1   | NA | NA   |
| ingressclasses | networking.k8s.io/v1   | ingressclasses | networking.k8s.io/v1   |
| ingresscontrollers | operator.openshift.io/v1   | NA | NA   |
| ingresses | config.openshift.io/v1, networking.k8s.io/v1  | ingresses | networking.k8s.io/v1   |
| installplans | operators.coreos.com/v1alpha1   | NA | NA   |
| ippools | whereabouts.cni.cncf.io/v1alpha1   | NA | NA   |
| jobs | batch/v1   | jobs | batch/v1   |
| kubeapiservers | operator.openshift.io/v1   | NA | NA   |
| kubecontrollermanagers | operator.openshift.io/v1   | NA | NA   |
| kubeletconfigs | machineconfiguration.openshift.io/v1   | NA | NA   |
| kubeschedulers | operator.openshift.io/v1   | NA | NA   |
| kubestorageversionmigrators | operator.openshift.io/v1   | NA | NA   |
| leases | coordination.k8s.io/v1   | leases | coordination.k8s.io/v1   |
| limitranges | v1   | limitranges | v1   |
| machineautoscalers | autoscaling.openshift.io/v1beta1   | NA | NA   |
| machineconfigpools | machineconfiguration.openshift.io/v1   | NA | NA   |
| machineconfigs | machineconfiguration.openshift.io/v1   | NA | NA   |
| machinehealthchecks | machine.openshift.io/v1beta1   | NA | NA   |
| machines | machine.openshift.io/v1beta1   | NA | NA   |
| machinesets | machine.openshift.io/v1beta1   | NA | NA   |
| mutatingwebhookconfigurations | admissionregistration.k8s.io/v1   | mutatingwebhookconfigurations | admissionregistration.k8s.io/v1   |
| namespaces | v1   | namespaces | v1   |
| network-attachment-definitions | k8s.cni.cncf.io/v1   | NA | NA   |
| networkpolicies | networking.k8s.io/v1   | networkpolicies | networking.k8s.io/v1   |
| networks | config.openshift.io/v1, operator.openshift.io/v1  | NA | NA   |
| nodes | v1, config.openshift.io/v1, metrics.k8s.io/v1beta1 | nodes | v1   |
| oauthaccesstokens | oauth.openshift.io/v1   | NA | NA   |
| oauthauthorizetokens | oauth.openshift.io/v1   | NA | NA   |
| oauthclientauthorizations | oauth.openshift.io/v1   | NA | NA   |
| oauthclients | oauth.openshift.io/v1   | NA | NA   |
| oauths | config.openshift.io/v1   | NA | NA   |
| olmconfigs | operators.coreos.com/v1   | NA | NA   |
| openshiftapiservers | operator.openshift.io/v1   | NA | NA   |
| openshiftcontrollermanagers | operator.openshift.io/v1   | NA | NA   |
| operatorconditions | operators.coreos.com/v1, operators.coreos.com/v2  | NA | NA   |
| operatorgroups | operators.coreos.com/v1, operators.coreos.com/v1alpha2  | NA | NA   |
| operatorhubs | config.openshift.io/v1   | NA | NA   |
| operatorpkis | network.operator.openshift.io/v1   | NA | NA   |
| operators | operators.coreos.com/v1   | NA | NA   |
| overlappingrangeipreservations | whereabouts.cni.cncf.io/v1alpha1   | NA | NA   |
| packagemanifests | packages.operators.coreos.com/v1   | NA | NA   |
| performanceprofiles | performance.openshift.io/v1, performance.openshift.io/v1alpha1, performance.openshift.io/v2 | NA | NA   |
| persistentvolumeclaims | v1   | persistentvolumeclaims | v1   |
| persistentvolumes | v1   | persistentvolumes | v1   |
| poddisruptionbudgets | policy/v1, policy/v1beta1  | poddisruptionbudgets | policy/v1   |
| podmonitors | monitoring.coreos.com/v1   | NA | NA   |
| podnetworkconnectivitychecks | controlplane.operator.openshift.io/v1alpha1   | NA | NA   |
| pods | v1, metrics.k8s.io/v1beta1  | pods | v1   |
| podsecuritypolicies | policy/v1beta1   | NA | NA   |
| podtemplates | v1   | podtemplates | v1   |
| preprovisioningimages | metal3.io/v1alpha1   | NA | NA   |
| priorityclasses | scheduling.k8s.io/v1   | priorityclasses | scheduling.k8s.io/v1   |
| prioritylevelconfigurations | flowcontrol.apiserver.k8s.io/v1beta1, flowcontrol.apiserver.k8s.io/v1beta2  | prioritylevelconfigurations | flowcontrol.apiserver.k8s.io/v1beta1, flowcontrol.apiserver.k8s.io/v1beta2  |
| probes | monitoring.coreos.com/v1   | NA | NA   |
| profiles | tuned.openshift.io/v1   | NA | NA   |
| projecthelmchartrepositories | helm.openshift.io/v1beta1   | NA | NA   |
| projectrequests | project.openshift.io/v1   | NA | NA   |
| projects | config.openshift.io/v1, project.openshift.io/v1  | NA | NA   |
| prometheuses | monitoring.coreos.com/v1   | NA | NA   |
| prometheusrules | monitoring.coreos.com/v1   | NA | NA   |
| provisionings | metal3.io/v1alpha1   | NA | NA   |
| proxies | config.openshift.io/v1   | NA | NA   |
| rangeallocations | security.internal.openshift.io/v1, security.openshift.io/v1  | rangeallocations | security.internal.openshift.io/v1   |
| replicasets | apps/v1   | replicasets | apps/v1   |
| replicationcontrollers | v1   | replicationcontrollers | v1   |
| resourceaccessreviews | authorization.openshift.io/v1   | NA | NA   |
| resourcequotas | v1   | resourcequotas | v1   |
| rolebindingrestrictions | authorization.openshift.io/v1   | NA | NA   |
| rolebindings | authorization.openshift.io/v1, rbac.authorization.k8s.io/v1  | rolebindings | rbac.authorization.k8s.io/v1   |
| roles | authorization.openshift.io/v1, rbac.authorization.k8s.io/v1  | roles | rbac.authorization.k8s.io/v1   |
| routes | route.openshift.io/v1   | routes | route.openshift.io/v1   |
| runtimeclasses | node.k8s.io/v1, node.k8s.io/v1beta1  | runtimeclasses | node.k8s.io/v1   |
| schedulers | config.openshift.io/v1   | NA | NA   |
| secrets | v1   | secrets | v1   |
| securitycontextconstraints | security.openshift.io/v1   | securitycontextconstraints | security.openshift.io/v1   |
| selfsubjectaccessreviews | authorization.k8s.io/v1   | selfsubjectaccessreviews | authorization.k8s.io/v1   |
| selfsubjectrulesreviews | authorization.k8s.io/v1   | selfsubjectrulesreviews | authorization.k8s.io/v1   |
| serviceaccounts | v1   | serviceaccounts | v1   |
| servicecas | operator.openshift.io/v1   | NA | NA   |
| servicemonitors | monitoring.coreos.com/v1   | NA | NA   |
| services | v1   | services | v1   |
| statefulsets | apps/v1   | statefulsets | apps/v1   |
| storageclasses | storage.k8s.io/v1   | storageclasses | storage.k8s.io/v1   |
| storages | operator.openshift.io/v1   | NA | NA   |
| storagestates | migration.k8s.io/v1alpha1   | NA | NA   |
| storageversionmigrations | migration.k8s.io/v1alpha1   | NA | NA   |
| subjectaccessreviews | authorization.k8s.io/v1, authorization.openshift.io/v1  | subjectaccessreviews | authorization.k8s.io/v1   |
| subscriptions | operators.coreos.com/v1alpha1   | NA | NA   |
| templateinstances | template.openshift.io/v1   | NA | NA   |
| templates | template.openshift.io/v1   | NA | NA   |
| thanosrulers | monitoring.coreos.com/v1   | NA | NA   |
| tokenreviews | authentication.k8s.io/v1, oauth.openshift.io/v1  | tokenreviews | authentication.k8s.io/v1   |
| tuneds | tuned.openshift.io/v1   | NA | NA   |
| useridentitymappings | user.openshift.io/v1   | NA | NA   |
| useroauthaccesstokens | oauth.openshift.io/v1   | NA | NA   |
| users | user.openshift.io/v1   | NA | NA   |
| validatingwebhookconfigurations | admissionregistration.k8s.io/v1   | validatingwebhookconfigurations | admissionregistration.k8s.io/v1   |
| volumeattachments | storage.k8s.io/v1   | volumeattachments | storage.k8s.io/v1   |
| volumesnapshotclasses | snapshot.storage.k8s.io/v1   | NA | NA   |
| volumesnapshotcontents | snapshot.storage.k8s.io/v1   | NA | NA   |
| volumesnapshots | snapshot.storage.k8s.io/v1   | NA | NA   |


