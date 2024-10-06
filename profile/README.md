# Resona - The Simple Job Scheduler

Resona allows you to register jobs that will call your API with the given parameters at a specified time.

> [!important]
> Disclaimer: This is currently a proof of concept. Use at own risk.

## Features

- Register a job for a specific time
- Register a job to be triggered after some delay
- Register recurring jobs (cron)
- Dockerfiles available for self hosting
- Console frontend to manage all jobs

## Example: Register a job

5 seconds after sending this Request to the Resona API, a POST request will be sent to `http://example.com/endpoint` with `{ "message": "Hello World" }` as the body.

```json
POST /jobs
Content-Type: application/json

{
  "name": "My Job",
  "request": {
    "url": "http://example.com/endpoint",
    "method": "POST",
    "headers": {},
    "body": {
        "message": "Hello World"
    }
  },
  "trigger": {
    "delay": 5
  }
}
```

For more information about the API, see [the repo](https://github.com/resona-dev/resona-api)

## Demo

> [!warning]
> The Demo is public and not secure. Just use it as a playground and dont submit any sensitive data as everything is visible to everyone.

There is a Demo available at <https://resona-console-production.up.railway.app/>. This will show the Console frontend which interacts with the API in the background.

## Available Repositories

- **[API Repository](https://github.com/resona-dev/resona-api)**: Contains the backend API for Resona.
- **[Console Repository](https://github.com/resona-dev/resona-console)**: Contains the frontend console for managing jobs.
