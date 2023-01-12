---
title: Questions & Talking Points
description: Quidem magni aut exercitationem maxime rerum eos.
---

Questions and talking points are created by reviewers for candidates to answer.

---

## Overview

Questions are the prompts created by reviewers to learn more about candidates. Each question has many recordings associated to it from different candidates. Talking Points help structure the candidates' responses to best present their experience on a given question's subject material.

### Questions

All metadata for a question is shown below:

```go
type Question struct {
	ID            string   `json:"id" dynamodbav:"id"`
	Body          string   `json:"body" dynamodbav:"body"`
	Tip           string   `json:"tip" dynamodbav:"tip"`
	Industry      string   `json:"industry" dynamodbav:"industry"`
	Company       string   `json:"company" dynamodbav:"company"`
	Topic         string   `json:"topic" dynamodbav:"topic"`
	Role          string   `json:"role" dynamodbav:"role"`
	TalkingPoints []string `json:"talking_points" dynamodbav:"talking_points"`
	Active        bool     `json:"active" dynamodbav:"active"`
	Sample        bool     `json:"sample" dynamodbav:""`

	Metadata []QuestionMetadata `json:"metadata" dynamodbav:"-"`

	ModelBase
}
```

Question Metadata is a many-to-many association model to store the relationships between users and questions.
