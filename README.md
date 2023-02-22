# **OpenShift to MicroShift Resource Mapping**

Recently I was approached with the task of understanding what were the resource differences between OpenShift and MicroShift.  This is especially important if one is interested in applying governance policies and rules across a fleet of systems that might be a mix of both OpenShift and MicroShift.  Knowing the availability of specific resource definitions that might be common or disparate between the two Kubernetes experience can help an administrator know if they can use the same policy across both instances or if they need to specifically craft a policy for one or the other.  Given that this information might be important for administrators I decided to map it out.

Below is a table that shows the resource definition and then if defined in OpenShift, MicroShift or both, the corresponding API version.

| Resource | OpenShift 4.11 | Microshift 4.12 | API Version |
| ------------------ | ----------- | ------------------- | ----------- |
| alertmanagerconfigs | Yes | No | monitoring.coreos.com/v1alpha1, monitoring.coreos.com/v1beta1  |
| alertmanagers | Yes | No | monitoring.coreos.com/v1   |
| apirequestcounts | Yes | No | apiserver.openshift.io/v1   |
| apiservers | Yes | No | config.openshift.io/v1   |
| apiservices | Yes | Yes | apiregistration.k8s.io/v1   |
| appliedclusterresourcequotas | Yes | No | quota.openshift.io/v1   |
| authentications | Yes | No | config.openshift.io/v1, operator.openshift.io/v1  |
| baremetalhosts | Yes | No | metal3.io/v1alpha1   |
| bmceventsubscriptions | Yes | No | metal3.io/v1alpha1   |
| brokertemplateinstances | Yes | No | template.openshift.io/v1   |
| buildconfigs | Yes | No | build.openshift.io/v1   |
| builds | Yes | No | build.openshift.io/v1, config.openshift.io/v1  |
| catalogsources | Yes | No | operators.coreos.com/v1alpha1   |
| certificatesigningrequests | Yes | Yes | certificates.k8s.io/v1   |
| cloudcredentials | Yes | No | operator.openshift.io/v1   |
| clusterautoscalers | Yes | No | autoscaling.openshift.io/v1   |
| clustercsidrivers | Yes | No | operator.openshift.io/v1   |
| clusteroperators | Yes | No | config.openshift.io/v1   |
| clusterresourcequotas | Yes | No | quota.openshift.io/v1   |
| clusterrolebindings | Yes | Yes | authorization.openshift.io/v1, rbac.authorization.k8s.io/v1  |
| clusterroles | Yes | Yes | authorization.openshift.io/v1, rbac.authorization.k8s.io/v1  |
| clusterserviceversions | Yes | No | operators.coreos.com/v1alpha1   |
| clusterversions | Yes | No | config.openshift.io/v1   |
| componentstatuses | Yes | Yes | v1   |
| configmaps | Yes | Yes | v1   |
| configs | Yes | No | imageregistry.operator.openshift.io/v1, operator.openshift.io/v1, samples.operator.openshift.io/v1 |
| consoleclidownloads | Yes | No | console.openshift.io/v1   |
| consoleexternalloglinks | Yes | No | console.openshift.io/v1   |
| consolelinks | Yes | No | console.openshift.io/v1   |
| consolenotifications | Yes | No | console.openshift.io/v1   |
| consoleplugins | Yes | No | console.openshift.io/v1alpha1   |
| consolequickstarts | Yes | No | console.openshift.io/v1   |
| consoles | Yes | No | config.openshift.io/v1, operator.openshift.io/v1  |
| consoleyamlsamples | Yes | No | console.openshift.io/v1   |
| containerruntimeconfigs | Yes | No | machineconfiguration.openshift.io/v1   |
| controllerconfigs | Yes | No | machineconfiguration.openshift.io/v1   |
| controllerrevisions | Yes | Yes | apps/v1   |
| credentialsrequests | Yes | No | cloudcredential.openshift.io/v1   |
| cronjobs | Yes | Yes | batch/v1, batch/v1beta1  |
| csidrivers | Yes | Yes | storage.k8s.io/v1   |
| csinodes | Yes | Yes | storage.k8s.io/v1   |
| csisnapshotcontrollers | Yes | No | operator.openshift.io/v1   |
| csistoragecapacities | Yes | Yes | storage.k8s.io/v1, storage.k8s.io/v1beta1  |
| customresourcedefinitions | Yes | Yes | apiextensions.k8s.io/v1   |
| daemonsets | Yes | Yes | apps/v1   |
| deploymentconfigs | Yes | No | apps.openshift.io/v1   |
| deployments | Yes | Yes | apps/v1   |
| dnses | Yes | No | config.openshift.io/v1, operator.openshift.io/v1  |
| dnsrecords | Yes | No | ingress.operator.openshift.io/v1   |
| egressfirewalls | Yes | No | k8s.ovn.org/v1   |
| egressips | Yes | No | k8s.ovn.org/v1   |
| egressqoses | Yes | No | k8s.ovn.org/v1   |
| egressrouters | Yes | No | network.operator.openshift.io/v1   |
| endpoints | Yes | Yes | v1   |
| endpointslices | Yes | Yes | discovery.k8s.io/v1, discovery.k8s.io/v1beta1  |
| etcds | Yes | No | operator.openshift.io/v1   |
| events | Yes | Yes | v1, events.k8s.io/v1, events.k8s.io/v1beta1 |
| featuregates | Yes | No | config.openshift.io/v1   |
| firmwareschemas | Yes | No | metal3.io/v1alpha1   |
| flowschemas | Yes | Yes | flowcontrol.apiserver.k8s.io/v1beta1, flowcontrol.apiserver.k8s.io/v1beta2  |
| groups | Yes | No | user.openshift.io/v1   |
| helmchartrepositories | Yes | No | helm.openshift.io/v1beta1   |
| horizontalpodautoscalers | Yes | Yes | autoscaling/v1, autoscaling/v2, autoscaling/v2beta1, |
| hostfirmwaresettings | Yes | No | metal3.io/v1alpha1   |
| identities | Yes | No | user.openshift.io/v1   |
| imagecontentpolicies | Yes | No | config.openshift.io/v1   |
| imagecontentsourcepolicies | Yes | No | operator.openshift.io/v1alpha1   |
| imagepruners | Yes | No | imageregistry.operator.openshift.io/v1   |
| images | Yes | No | config.openshift.io/v1, image.openshift.io/v1  |
| imagesignatures | Yes | No | image.openshift.io/v1   |
| imagestreams | Yes | No | image.openshift.io/v1   |
| imagestreamtags | Yes | No | image.openshift.io/v1   |
| imagetags | Yes | No | image.openshift.io/v1   |
| infrastructures | Yes | No | config.openshift.io/v1   |
| ingressclasses | Yes | Yes | networking.k8s.io/v1   |
| ingresscontrollers | Yes | No | operator.openshift.io/v1   |
| ingresses | Yes | Yes | config.openshift.io/v1, networking.k8s.io/v1  |
| installplans | Yes | No | operators.coreos.com/v1alpha1   |
| ippools | Yes | No | whereabouts.cni.cncf.io/v1alpha1   |
| jobs | Yes | Yes | batch/v1   |
| kubeapiservers | Yes | No | operator.openshift.io/v1   |
| kubecontrollermanagers | Yes | No | operator.openshift.io/v1   |
| kubeletconfigs | Yes | No | machineconfiguration.openshift.io/v1   |
| kubeschedulers | Yes | No | operator.openshift.io/v1   |
| kubestorageversionmigrators | Yes | No | operator.openshift.io/v1   |
| leases | Yes | Yes | coordination.k8s.io/v1   |
| limitranges | Yes | Yes | v1   |
| machineautoscalers | Yes | No | autoscaling.openshift.io/v1beta1   |
| machineconfigpools | Yes | No | machineconfiguration.openshift.io/v1   |
| machineconfigs | Yes | No | machineconfiguration.openshift.io/v1   |
| machinehealthchecks | Yes | No | machine.openshift.io/v1beta1   |
| machines | Yes | No | machine.openshift.io/v1beta1   |
| machinesets | Yes | No | machine.openshift.io/v1beta1   |
| mutatingwebhookconfigurations | Yes | Yes | admissionregistration.k8s.io/v1   |
| namespaces | Yes | Yes | v1   |
| network-attachment-definitions | Yes | No | k8s.cni.cncf.io/v1   |
| networkpolicies | Yes | Yes | networking.k8s.io/v1   |
| networks | Yes | No | config.openshift.io/v1, operator.openshift.io/v1  |
| nodes | Yes | Yes | v1, config.openshift.io/v1, metrics.k8s.io/v1beta1 |
| oauthaccesstokens | Yes | No | oauth.openshift.io/v1   |
| oauthauthorizetokens | Yes | No | oauth.openshift.io/v1   |
| oauthclientauthorizations | Yes | No | oauth.openshift.io/v1   |
| oauthclients | Yes | No | oauth.openshift.io/v1   |
| oauths | Yes | No | config.openshift.io/v1   |
| olmconfigs | Yes | No | operators.coreos.com/v1   |
| openshiftapiservers | Yes | No | operator.openshift.io/v1   |
| openshiftcontrollermanagers | Yes | No | operator.openshift.io/v1   |
| operatorconditions | Yes | No | operators.coreos.com/v1, operators.coreos.com/v2  |
| operatorgroups | Yes | No | operators.coreos.com/v1, operators.coreos.com/v1alpha2  |
| operatorhubs | Yes | No | config.openshift.io/v1   |
| operatorpkis | Yes | No | network.operator.openshift.io/v1   |
| operators | Yes | No | operators.coreos.com/v1   |
| overlappingrangeipreservations | Yes | No | whereabouts.cni.cncf.io/v1alpha1   |
| packagemanifests | Yes | No | packages.operators.coreos.com/v1   |
| performanceprofiles | Yes | No | performance.openshift.io/v1, performance.openshift.io/v1alpha1, performance.openshift.io/v2 |
| persistentvolumeclaims | Yes | Yes | v1   |
| persistentvolumes | Yes | Yes | v1   |
| poddisruptionbudgets | Yes | Yes | policy/v1, policy/v1beta1  |
| podmonitors | Yes | No | monitoring.coreos.com/v1   |
| podnetworkconnectivitychecks | Yes | No | controlplane.operator.openshift.io/v1alpha1   |
| pods | Yes | Yes | v1, metrics.k8s.io/v1beta1  |
| podsecuritypolicies | Yes | No | policy/v1beta1   |
| podtemplates | Yes | Yes | v1   |
| preprovisioningimages | Yes | No | metal3.io/v1alpha1   |
| priorityclasses | Yes | Yes | scheduling.k8s.io/v1   |
| prioritylevelconfigurations | Yes | Yes | flowcontrol.apiserver.k8s.io/v1beta1, flowcontrol.apiserver.k8s.io/v1beta2  |
| probes | Yes | No | monitoring.coreos.com/v1   |
| profiles | Yes | No | tuned.openshift.io/v1   |
| projecthelmchartrepositories | Yes | No | helm.openshift.io/v1beta1   |
| projectrequests | Yes | No | project.openshift.io/v1   |
| projects | Yes | No | config.openshift.io/v1, project.openshift.io/v1  |
| prometheuses | Yes | No | monitoring.coreos.com/v1   |
| prometheusrules | Yes | No | monitoring.coreos.com/v1   |
| provisionings | Yes | No | metal3.io/v1alpha1   |
| proxies | Yes | No | config.openshift.io/v1   |
| rangeallocations | Yes | Yes | security.internal.openshift.io/v1, security.openshift.io/v1  |
| replicasets | Yes | Yes | apps/v1   |
| replicationcontrollers | Yes | Yes | v1   |
| resourceaccessreviews | Yes | No | authorization.openshift.io/v1   |
| resourcequotas | Yes | Yes | v1   |
| rolebindingrestrictions | Yes | No | authorization.openshift.io/v1   |
| rolebindings | Yes | Yes | authorization.openshift.io/v1, rbac.authorization.k8s.io/v1  |
| roles | Yes | Yes | authorization.openshift.io/v1, rbac.authorization.k8s.io/v1  |
| routes | Yes | Yes | route.openshift.io/v1   |
| runtimeclasses | Yes | Yes | node.k8s.io/v1, node.k8s.io/v1beta1  |
| schedulers | Yes | No | config.openshift.io/v1   |
| secrets | Yes | Yes | v1   |
| securitycontextconstraints | Yes | Yes | security.openshift.io/v1   |
| selfsubjectaccessreviews | Yes | Yes | authorization.k8s.io/v1   |
| selfsubjectrulesreviews | Yes | Yes | authorization.k8s.io/v1   |
| serviceaccounts | Yes | Yes | v1   |
| servicecas | Yes | No | operator.openshift.io/v1   |
| servicemonitors | Yes | No | monitoring.coreos.com/v1   |
| services | Yes | Yes | v1   |
| statefulsets | Yes | Yes | apps/v1   |
| storageclasses | Yes | Yes | storage.k8s.io/v1   |
| storages | Yes | No | operator.openshift.io/v1   |
| storagestates | Yes | No | migration.k8s.io/v1alpha1   |
| storageversionmigrations | Yes | No | migration.k8s.io/v1alpha1   |
| subjectaccessreviews | Yes | Yes | authorization.k8s.io/v1, authorization.openshift.io/v1  |
| subscriptions | Yes | No | operators.coreos.com/v1alpha1   |
| templateinstances | Yes | No | template.openshift.io/v1   |
| templates | Yes | No | template.openshift.io/v1   |
| thanosrulers | Yes | No | monitoring.coreos.com/v1   |
| tokenreviews | Yes | Yes | authentication.k8s.io/v1, oauth.openshift.io/v1  |
| tuneds | Yes | No | tuned.openshift.io/v1   |
| useridentitymappings | Yes | No | user.openshift.io/v1   |
| useroauthaccesstokens | Yes | No | oauth.openshift.io/v1   |
| users | Yes | No | user.openshift.io/v1   |
| validatingwebhookconfigurations | Yes | Yes | admissionregistration.k8s.io/v1   |
| volumeattachments | Yes | Yes | storage.k8s.io/v1   |
| volumesnapshotclasses | Yes | No | snapshot.storage.k8s.io/v1   |
| volumesnapshotcontents | Yes | No | snapshot.storage.k8s.io/v1   |
| volumesnapshots | Yes | No | snapshot.storage.k8s.io/v1   |


