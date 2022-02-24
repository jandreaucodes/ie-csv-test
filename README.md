# CSV Uploader

### About

This is an unsophisticated script to send rows of a CSV as payloads to a hook.

### Usage

Save your CSV file as `data.csv` in the root folder. The first row of the CSV must contain the headers, which will be sent "as is" in the payload.

Create a file named `.env`; you can do so by copying the provided `.env-example` file. Add your `HOOK_URL` and, optionally, a `HOOK_TOKEN` to the `.env` file.

Install dependencies:

```shell
npm i
```

And run the script:

```shell
node index.js
```

### Notes

By default, the script will send 5 webhooks per second (aprox). This is usually appropriate, but may vary depending on your case. Hooks API rate limit is 1.000 rpm (~16 per second). Workflow execution rate limit depends on the number of steps. Check the [documentation](https://help.kustomer.com/en_us/api-rate-limits-Sk2xoQgYX).

CSVs are usually large (more than 10.000 rows). This means a typical CSV will take 1 hour or more to be uploaded. Have this in mind when you run this script locally.
