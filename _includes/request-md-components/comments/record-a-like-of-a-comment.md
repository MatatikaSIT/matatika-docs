## Record a like of a comment

PUT
{:.label .label-PUT}

/api/comment/{comment-id}/like
{:.path .path-PUT}

Records a like of the comment `{comment-id}` from the authenticated profile and increments its like count `likeCount` by 1.

### Prerequisites

- Comment `{comment-id}` must exist

### Request

#### cURL

{% include snippets/comments/record-a-like-of-a-comment/curl-request.md %}

#### Python (Requests)

{% include snippets/comments/record-a-like-of-a-comment/python-requests.md %}

### Response
{: .d-inline-block }

200
{:.label .label-PUT}

No response body provided.

---