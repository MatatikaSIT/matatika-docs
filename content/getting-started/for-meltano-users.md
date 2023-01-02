---
title: For Meltano Users
permalink: /getting-started/for-meltano-users
nav_order: 2
parent: Getting Started

---

# Getting Started {{page.title}}

- Time required: *10 minutes*

---

## Overview

This getting started guide will get your Meltano project up and running with the Matatika Lab. During the set up a Matatika workspace will be generated for your project, with all of your plugins loaded and ready to be configured.

---

## Requirements

- Meltano installed - [How to get Meltano](https://docs.meltano.com/getting-started/installation){:target="_blank"}
- Docker installed - [How to get Docker](https://docs.docker.com/get-docker/){:target="_blank"}

---

## Install the Matatika plugin into your workspace

1. In your terminal `cd` into your Meltano project
1. In your terminal run:
```terminal
meltano add files files-matatika-lab
```
- If you plan on hosting the lab for other users to connect to, we suggest setting your own secret in the `docker-compose.yml` for the environment variable `MATATIKA_AUTH_LOCAL_SECRET`.
1. In your terminal run:
```terminal
docker compose up
``` 
(This may take some time to download the docker images for the first run).
1. Once everything is running, in your browser go to:
```
localhost:3443
```
1. You will now see a login screen. If you already have a Matatika account you can just login, otherwise sign up.

Congratulations, you now have the Matatika lab running against your Meltano project!

[Make Your First API Call]({{site.baseurl}}/how-to-guides/use-the-matatika-api/making-your-first-api-call){: .btn}
{: .text-center}

---

## Further Reading

- Find out how Matatika works with Meltano by reading about the Matatika concepts and artifacts: [Matatika Concepts]({{site.baseurl}}/concepts), [Matatika Glossary]({{site.baseurl}}/glossary) and [Matatika Technical Glossary](https://github.com/Matatika/matatika-examples/tree/master/matatika_technical_glossary){:target="_blank"}
- Create your first pipeline: [Create A Data Import Pipeline]({{site.baseurl}}/how-to-guides/import-data/create-a-data-import-pipeline)