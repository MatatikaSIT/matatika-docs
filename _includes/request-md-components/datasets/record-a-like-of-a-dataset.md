## Record a like of a dataset

PUT
{:.label .label-PUT}

/api/datasets/{dataset-id}/like
{:.path .path-PUT}

Records a like of the dataset `{dataset-id}` from the authenticated profile and increments its like count `likeCount` by 1.

### Prerequisites

- Dataset `{dataset-id}` must exist

### Request

#### cURL

{% include snippets/datasets/record-a-like-of-a-dataset/curl-request.md %}

#### Python (Requests)

{% include snippets/datasets/record-a-like-of-a-dataset/python-requests.md %}

### Response
{: .d-inline-block }

200
{:.label .label-PUT}

No response body provided.

---