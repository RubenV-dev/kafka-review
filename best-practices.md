# Best practices for version control, ci/cd and deployment patterns

Prefereed is the branching strategy like git or githuv which uses trunk-based development which short lived branches and multiple merges to avoid conflicts

# Versioning

Semantic Versioning(SEMVER)
MAJOR.MINOR.PATCH
Tag releases in git for traceability

# CI/CD Pipeline Best practices

COntinuous integration means
every commit triggers a build, unit tests, and static analysis where a broken build shiould blocks merges
tools like jenkins. github actions or circleci

Continouse delivery/deployments
automate build -> Test -> Deploy

uses environment stages
DEV -> Staging -> Production

# Secrets and Security

Never store secrets in code, use secret managers or environment variables
scan for vulnerabilities

# Testing strategies

pyramid format
unit tests many
integration tests (some)
e2e tests few

run tests in parallel to speed up pipelines

# Artifact Management

Build it once and deploy same everywhere,
store artificats in registries like docker registries or package repo

# Deployment Patterns

Blue-Green two environments where blue is current and green is new to switch traffic instantely which can give you zero downtrime and easy rollbacks

canary deployment, release to small % of users first then gradually increase traffic which has pros like safer releases and real-world testing

feature-flags is where you deploty code without enabling features, you toggle features on/off dynamically

rolling deployments
geradually replace instances, which is common in kubernetes

immutable infrastructure
never modify running servers, deploy new versions instead like with tools like docker and kubernetes

# Dev Ops and cloud native best practices

Observability where you monitor everything
logs,metrics,traces using tools like prometheus and datadog

Infrastructure as code(IaC)
define infastructure in code and version it like application code using tools like terraform and aws cloudformation

gitops when git is used as the source of truth and deployments trigger by guit changes
