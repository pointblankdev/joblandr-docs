---
title: Recordings & Feedback
description: Quidem magni aut exercitationem maxime rerum eos.
---

Recordings are created by candidates, and feedback is created by reviewers, associated to a specific recording.

---

## Overview

Recordings are the core of JobLandr. Each recording is a piece of data referencing a audio file containing a recorded answer to a specific question. A candidate's best recordings can be shown on their candidate page for hiring managers to review and see if the candidate has the right experience for the role.

### Recordings

All metadata for a recording is shown below:

```go
type Recording struct {
	ID         string `json:"id" dynamodbav:"id"`
	Title      string `json:"title" dynamodbav:"title"`
	Name       string `json:"name" dynamodbav:"name"`
	UserID     string `json:"user_id" dynamodbav:"user_id"`
	QuestionID string `json:"question_id" dynamodbav:"question_id"`
	Path       string `json:"path" dynamodbav:"path"`
	File       string `json:"file" dynamodbav:"file"`
	Complete   bool   `json:"complete" dynamodbav:"complete"`

	ModelBase
}
```

Path marks the location of the audio file in AWS S3 cloud storage.
