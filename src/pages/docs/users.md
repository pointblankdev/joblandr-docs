---
title: Users, Roles, & Profiles
description: Quidem magni aut exercitationem maxime rerum eos.
---

The structures for handling candidates' metadata and authorizational access controls

---

## Overview

Users data is primarly for association to the candidate's questions and recordings in a one-to-many relationship, with a view fields for authorization controls and preferences.

### Users

All metadata for a user is shown below:

```go
type User struct {
	ID        string  `json:"id" dynamodbav:"id"`
	Email     string  `json:"email" dynamodbav:"email"`
	FirstName string  `json:"first_name" dynamodbav:"first_name"`
	LastName  string  `json:"last_name" dynamodbav:"last_name"`
	Profile   Profile `json:"profile" dynamodbav:"profile"`
	Roles     []Role  `json:"roles" dynamodbav:"roles"`

	ModelBase
}

```

The Profile field is used to store the users PinnedQuestions, which are relevant questions for that candidate.

The Roles field is used to store the roles the user has on the platform.
