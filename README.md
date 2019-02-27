# skydive-sdn-openshift

https://github.com/skydive-project/skydive/tree/master/contrib/openshift

    oc adm new-project --node-selector='' skydive
    oc project skydive
    oc adm policy add-scc-to-user privileged -z default
    oc adm policy add-cluster-role-to-user cluster-reader -z default
    VERSION=master
    oc process -f https://raw.githubusercontent.com/skydive-project/skydive/${VERSION}/contrib/openshift/skydive-template.yaml | oc apply -f -
