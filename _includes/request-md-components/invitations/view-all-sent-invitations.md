## View all sent invitations

GET
{:.label .label-GET}

/api/invitations
{:.path .path-GET}

Returns all invitations sent by the user.

### Request

- cURL
{: .tab .tabs-section-start}

{% include snippets/invitations/view-all-sent-invitations/curl-request.md %}

- Python (requests)
{: .tab}

{% include snippets/invitations/view-all-sent-invitations/python-requests.md %}
{: .tabs-section-end}

### Response
{: .d-inline-block }

200
{:.label .label-GET}

[Invitation object](invitations#invitation-object) collection with HAL links.

---