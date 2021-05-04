## Start a job from a pipeline

POST
{:.label .label-POST}

/api/pipeline/{pipeline-id}/jobs
{:.path .path-POST}

Starts a new job from the pipeline `{pipeline-id}`.

### Prerequisites
- Pipeline `{pipeline-id}` must exist and not already be running

### Request
#### Headers

Key | Value | Description
--- | ----- | -----------
`enable-task-details` | `true` | Enables detailed task information in the resulting [Job](#job) object response
`enable-task-details` | `false` (default) | Disables detailed task information in the resulting [Job](#job) object response

#### Example Snippets
- cURL
{: .tab .tabs-section-start}

{% include snippets/api/jobs/start-a-job-from-a-pipeline/curl-request.md %}

- Python (requests)
{: .tab}

{% include snippets/api/jobs/start-a-job-from-a-pipeline/python-requests.md %}
{: .tabs-section-end}

### Response
{: .d-inline-block }

201
{:.label .label-POST}

[Job](#job) object with HAL links.

---