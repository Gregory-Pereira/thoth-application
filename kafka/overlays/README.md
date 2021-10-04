# Strimzi ArgoCD Kafdrop Application

This is a bare minimum ArgoCD Application to get Strimzi deployed along with a Kafdrop instance.

## Prerequisites

- Have a namespace-wide strimzi-kafka-operator or amq-streams-operator installed on your OpenShift 4.3+ cluster.
- Use the namespace KAFKA_BOOTSTRAP_SERVER env variable in the kafdrop deployment to reflect the location of your kafka bootstrap servers

# Updating secrets

- The Strimzi Kafka operator is what generates new certificates. If a new user is wants access so they can be deployed with kafka on operate-first, they should open a new issue at [operate-first/support](https://github.com/operate-first/support/issues/new?assignees=&labels=user-support&template=kafka_user_topic_request.md&title=) requesting secrets access, which will then be emailed to them.

# Onboarding new users to Kafka

- When a new organization wants to use Kafka on the operate-first cluster, they need to create a new KafkaUser manfiest for thoth-application. This allows their instance of thoth to use the Kafka service, and allows it to be deployed by argo. An example of this can be found [here](https://github.com/operate-first/apps/blob/master/odh-manifests/smaug/kafka/overlays/users/thoth.yaml).