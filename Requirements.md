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
#### Docker Hub
* Major Features
 * multiplatform, layered file system
 * push and pull container images
  * images are stored as tags
  * tags and size of image is listed
  * ability to search for images via command line by image name, username, or description
  * can bookmark favorite repositories
  * can create service accounts for automating build pipeline for containerized applications
 * manage access to private repositories of container images
  * need to be signed in with access to work with private repositories
  * private repositories are not available to search through top-level or docker search
  * manage collaborators and their access
  * organizations: collections of teams and repositories, can be managed together
   * teams: groups of users belonging to organization, users can not belong directly to orgs
 * pull and use high-quality container images provided by Docker
  * "Docker Official Images" - curated set of Docker repositories hosted on Docker Hub
   * provides essential base OS repositories, drop-in solutions, ensures regular security updates
 * pull and use high-quality container images provided by external vendors
 * automaticlaly build images from GitHub and Bitbucket and pushes to Docker Hub
 * trigger actions after success push to repository to integrate Docker Hub with other services
  * "webhooks" - post requests sent to a URL defined in docker hub, HTTP call-back
  * can view webhook delivery and status of webhook payloads
#### TreeScale
* Major Features
 * multiplatform 
 * distributed image layers
  * layers are split into multiple small chunks, distributed over servers
  * TreeScale Container Registry sends Layer chunks from multple sources, "gives about 2 times more performance" for network usage
 * full CLI API access
 * team collaboration
 * automated container builds
  * allows concurrent container image builds 
 * scalability - builds real-time publish/subscribe applications using Math Tree/Graph-based scalability
  * https://github.com/treescale/treescale/blob/4095f025aced6e49a27984cff91ac9f38b0153ad/README.md
  * TCP connections between apps and TreeScale are always "alive", avoids infinite request/response cycles, more secure
  * services are decentralized, apps are fully independent, communication made by event handle
  * platform and app technology stack independent, data transfer packaged 
 * Auth Tokens - password-less authentication
  * from TreeScale dashboard, create new Auth Token as password to pull a docker image (only allows *docker login*)
  * after use, Auth Token can be deleted
  * used to give access for push/pull images from CI/CD platforms, but no access to anything else
#### Gitlab
* Major Features
 * subgroups management, access restriction at group level to incoming traffic adhering to an IP address subnet
  * manage access of group members
  * add to-do items
  * view/edit issues, merge requests for all projects in group
  * group activity analytics (# merge requests, # issues, # members)
  * manage group data (transfer group path, transfer groups) 
  * 5 roles: guest, reporter, developer, maintainer, owner
 * Credentials inventory
  * keeps track of all credentials used to access the instance
  * view all personal access tokens, SSH keys and GPG keys in your GitLab instance (as well as manage them and view metadata on them) 
 * access to server - complete control of server/instance, allows additional software for security, performance, etc.
  * log system logs everything for file information
   *  information for Rails controller requests received from GitLab, also contains performance data
   *  all information about performed requests
   *  requests made directly to API
   *  events happening in instance such as user creation
   *  changes to group/project settings/memberships
   *  errors and failed requests from GitLab to Git repositories
   *  info about background jobs
 * threaded discussions for issues, merge requests, and epics
 * shows history of changes to issues, etc. with filter by comments or history
 * issues can be labeled/categorized and weighted for priority
* Nexus Repository Manager
* Cloud Registry Options:
 * Google Cloud Container Registry
 * Azure Container Registry 
* Jfrog Container Registry
* Github Container Registry (Beta)
#### GoHarbor
* Major Features
 * "secures artifacts with policies and role-based access control"
 * iamges are scanned for vulnerabilites
 * images are signed and validated
* Quay/Redhat
