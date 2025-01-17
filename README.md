<!-- [START AUTO UPDATE] -->
<!-- Please keep comment here to allow auto-update -->
## Updated Content
This is the updated content for the README.md file.

apiVersion: scaffolder.backstage.io/v1beta3
kind: Template
# some metadata about the template itself
metadata:
  name: backstage-systems
  title: Gitops filebeat
  description: This template will create filebeat in Backstage
  tags:
    - filebeat
spec:
  owner: filebeat
  type: service

  # these are the steps which are rendered in the frontend with the form input
  parameters:
    - title: Provide Needed Information
      required:
        - OCP_LOGSTASH_SERVER
        - OCP_CLUSTER_NAME
        - OCP_CLUSTER_URL
      properties:
        OCP_LOGSTASH_SERVER:
          title: OCP_LOGSTASH_SERVER
          type: string
          description: Select OCP_LOGSTASH_SERVER
          default: Dev_ocpplatform.logstash-logs.volvocars.net:5045
          enum:
            - Dev_ocpplatform.logstash-logs.volvocars.net:5045
            - Prod_ocpplatform.logstash-logs.volvocars.net:5045
            - Test_ocpplatform.logstash-logs.volvocars.net:5045
        dependencies:
          OCP_LOGSTASH_SERVER:
            oneOf:
              - properties:
                  OCP_LOGSTASH_SERVER:
                    enum:
                      - Dev_ocpplatform.logstash-logs.volvocars.net:5045

                  OCP_CLUSTER_NAME9:
                    title: OCP_CLUSTER_NAME
                    type: string
                    description: Select OCP_CLUSTER_NAME
                    default: test-net
                    enum:
                      - sandbox-net
                      - rnd-net
                      - test-net
                    enumNames:
                      - 'sandbox-net'
                      - 'rnd-net'
                      - 'test-net'

                  OCP_CLUSTER_URL9:
                    title: OCP_CLUSTER_URL
                    type: string
                    description: Enter your OCP_CLUSTER_URL
                    default: my cluster
        ################################################################################
              - properties:
                  OCP_LOGSTASH_SERVER:
                    enum:
                      - Prod_ocpplatform.logstash-logs.volvocars.net:5045

                  OCP_CLUSTER_NAME8:
                    title: OCP_CLUSTER_NAME
                    type: string
                    description: Select OCP_CLUSTER_NAME
                    default: rnd-net
                    enum:
                      - sandbox-net
                      - rnd-net
                      - test-net
                    enumNames:
                      - 'sandbox-net'
                      - 'rnd-net'
                      - 'test-net'

                  OCP_CLUSTER_URL8:
                    title: OCP_CLUSTER_URL
                    type: string
                    description: Enter your OCP_CLUSTER_URL
                    default: our cluster
        ################################################################################
              - properties:
                  OCP_LOGSTASH_SERVER:
                    enum:
                      - Test_ocpplatform.logstash-logs.volvocars.net:5045

                  OCP_CLUSTER_NAME7:
                    title: OCP_CLUSTER_NAME
                    type: string
                    description: Select OCP_CLUSTER_NAME
                    default: sandbox-net
                    enum:
                      - sandbox-net
                      - rnd-net
                      - test-net
                    enumNames:
                      - 'sandbox-net'
                      - 'rnd-net'
                      - 'test-net'

                  OCP_CLUSTER_URL7:
                    title: OCP_CLUSTER_URL
                    type: string
                    description: Enter your OCP_CLUSTER_URL
                    default: final cluster
<!-- [END AUTO UPDATE] -->
