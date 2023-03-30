# TailorShift

> It's me, hi!

## About

TailorShift is a project delivered by Atos (Evidian) as part of
the [RedHat EMEA Hackfest 2023](https://qiot-project.github.io/blog/usecase-retail/).

In a nutshell, TailorShift is a fashion company with many stores, that wants to use cutting edge technologies to
orchestrate the workflow from Point of Sale devices (edge), via the local shops (backoffice) to the datacenter.

More background information on the use case and the requirements of the challenge can be found on the page linked above.

We documented our solution approach separately here.

## Technologies used

The hackfest is mostly a proof of concept with affinity for RedHat technologies. As such we used quite a lot in this
project:

* OpenShift ARO cluster (backend) + Single Node OpenShift (backoffice)
* RHEL@Edge + Podman for running service on our PoS device
* CrunchyDB (PG Operator) for deploying Postgres
* AMQ Streams (Strimzi) for deploying Kafka & Kafka Connect clusters and related tooling
* Debezium as a Kafka Connect service to replicate Postgres data
* MirrorMaker2 to move Debezium messages across from backoffice into the datacenter (and vice versa)
* OpenShift GitOps (ArgoCD) for managing our infrastructure as code (deploying applications and resources in the
  cluster)
* OpenShift Data Science for creating sales predictions
* Grafana for visualizing sales predictions
* Cert Manager for setting up a PKI infrastructure and dynamic certificate generation
* Quarkus (with Java) as the only framework for backend application development
* Hibernate and Panache for accessing the database in Quarkus
* Patternfly Seed (with Typescript) for frontend application development
* GitHub for version control
* Flyway for database version control
* Schemaspy for visualizing the database schema (served by GitHub Actions & GitHub Pages)
* Tekton for CI pipelines
* Fido Device onboarding

## Contributions & Support

The hackfest was completed on 02.04.2023 and our project is finished. Please understand that we do not accept pull
requests for the project and cannot provide support.
