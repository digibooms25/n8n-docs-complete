# Jenkins node documentation

**Source:** https://docs.n8n.io/integrations/builtin/app-nodes/n8n-nodes-base.jenkins/

---

# Jenkins node

Use the Jenkins node to automate work in Jenkins, and integrate Jenkins with other applications. n8n has built-in support for a wide range of Jenkins features, including listing builds, managing instances, and creating and copying jobs.

Credentials

Refer to [Jenkins credentials](../../credentials/jenkins/) for guidance on setting up authentication.

This node can be used as an AI tool

This node can be used to enhance the capabilities of an AI agent. When used in this way, many parameters can be set automatically, or with information directed by AI - find out more in the [AI tool parameters documentation](../../../../advanced-ai/examples/using-the-fromai-function/).

## Operations

- Build
  - List Builds
- Instance
  - Cancel quiet down state
  - Put Jenkins in quiet mode, no builds can be started, Jenkins is ready for shutdown
  - Restart Jenkins immediately on environments where it's possible
  - Restart Jenkins once no jobs are running on environments where it's possible
  - Shutdown once no jobs are running
  - Shutdown Jenkins immediately
- Job
  - Copy a specific job
  - Create a new job
  - Trigger a specific job
  - Trigger a specific job

## Templates and examples

[Browse Jenkins integration templates](https://n8n.io/integrations/jenkins/), or [search all templates](https://n8n.io/workflows/)
