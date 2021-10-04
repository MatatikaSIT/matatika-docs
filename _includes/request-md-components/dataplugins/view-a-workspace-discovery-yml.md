## View a workspace `discovery.yml`

GET
{:.label .label-GET}

/api/workspaces/{workspace-id}/discovery.yml
{:.path .path-GET}

Returns a [Meltano `discovery.yml`](https://meltano.com/docs/plugins.html#discoverable-plugins) containing all dataplugins available to the workspace `{workspace-id}`.

### Prerequisites
- Workspace `{workspace-id}` must exist

### Request
#### Example Snippets
- cURL
{: .tab .tabs-section-start}

{% include snippets/api/dataplugins/view-a-workspace-discovery-yml/curl-request.md %}

- Python (requests)
{: .tab}

{% include snippets/api/dataplugins/view-a-workspace-discovery-yml/python-requests.md %}
{: .tabs-section-end}

### Response
{: .d-inline-block }

### `200 OK`
{: .fs-4 .path-GET }

[Meltano `discovery.yml`](https://meltano.com/docs/plugins.html#discoverable-plugins).

{% include snippets/api/dataplugins/view-a-workspace-discovery-yml/response-body.md %}

---