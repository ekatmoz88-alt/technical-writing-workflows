# Tasks API overview

## Purpose

The Tasks API is a fictional example used to demonstrate how Markdown documentation can be checked as part of a Docs-as-Code workflow.

## List tasks

Use `GET /tasks` to retrieve the available tasks.

A successful response returns an array of task objects. Each task includes:

- `id`: the task identifier.
- `title`: the task title.
- `completed`: whether the task is complete.

## Create a task

Use `POST /tasks` to create a task. The request body must contain a non-empty `title`.

A successful request returns HTTP `201` and the created task object. An invalid request may return HTTP `400`.

## Source of truth

The [OpenAPI specification](../openapi/openapi.yaml) defines the endpoints, request body, response codes, and data schemas. Keep this overview consistent with that specification when making changes.

> This is illustrative sample content. It does not document a live service.
