## Requirements
* Scalability (across Docker daemons)
* Contains tools for managing multiple containers (Docker Compose)
  * Ability to cluster containers and treat as one entity

From "Building Containerized Environments for Reproducibiity and Traceability of Scientific Workflows" by Paula Fernanda Olaya
* Ability to automatically annotate containers to create record trail within workflows
  * Ability to find/record workflow history to create a certain container using its id
  * Ability to tightly connect data and metadata of workflows
  * Ability to address metadata from within the system-level for full visibility into system-wide behavior
* Ability to store both data containers as well as application containers
  * Support for read/write file system
  * Ability to transfer data between containers readily
  * Ability to allow easy communication between containers (zero-copy data transfer, direct paths)
* Ability to run/utilize containers without administrative privileges
* Strong security model
* Ability to have immutable applications machine-agnostic
* Ability to control isolation of containers and group processes
* Ability to minimize time/space overhead for containers, allowing several simulaneous containers and large workflows

## List of Container Hubs
* Docker registries
 * Docker Hub
 * TreeScale
* Gitlab
* Nexus Repository Manager
* Cloud Registry Options:
 * Google Cloud Container Registry
 * Azure Container Registry 
* Jfrog Container Registry

