## View all received invitations

GET
{:.label .label-GET}

/api/invitations?email={user-email}
{:.path .path-GET}

Returns all invitations intended for the user.

### Request

- cURL
{: .tab .tabs-section-start}

{% include snippets/invitations/view-all-received-invitations/curl-request.md %}

- Python (requests)
{: .tab}

{% include snippets/invitations/view-all-received-invitations/python-requests.md %}
{: .tabs-section-end}

### Response
{: .d-inline-block }

200
{:.label .label-GET}

[Invitation object](invitations#invitation-object) collection with HAL links.

---