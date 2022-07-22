<!-- start title -->

# GitHub Action:Publish NPM Package to Google Artifact Registry

<!-- end title -->
<!-- start description -->

Publishes an npm package to Google Artifact Registry

<!-- end description -->
<!-- start contents -->
<!-- end contents -->
<!-- start usage -->

```yaml
- uses: catalystsquad/action-npm-publish-artifact-registry@undefined
  with:
    # gcloud service account credentials json
    credentials-json: ""

    # gcloud project id
    project-id: ""

    # artifact registry region
    # Default: us-west1
    region: ""

    # artifact registry repository
    # Default: npm
    repository: ""

    # scope to use when publishing
    scope: ""
```

<!-- end usage -->
<!-- start inputs -->

| **Input**              | **Description**                         | **Default** | **Required** |
| :--------------------- | :-------------------------------------- | :---------: | :----------: |
| **`credentials-json`** | gcloud service account credentials json |             |   **true**   |
| **`project-id`**       | gcloud project id                       |             |   **true**   |
| **`region`**           | artifact registry region                | `us-west1`  |  **false**   |
| **`repository`**       | artifact registry repository            |    `npm`    |  **false**   |
| **`scope`**            | scope to use when publishing            |             |   **true**   |

<!-- end inputs -->
<!-- start outputs -->

| **Output**      | **Description** | **Default** | **Required** |
| :-------------- | :-------------- | ----------- | ------------ |
| `random-number` | Random number   |             |              |

<!-- end outputs -->
<!-- start examples -->

### Example usage

```yaml
on: [push]

jobs:
  hello_world_job:
    runs-on: ubuntu-latest
    name: A job to say hello
    steps:
      - uses: actions/checkout@v2
      - id: foo
        uses: actions/hello-world-composite-action@v1
        with:
          who-to-greet: "Mona the Octocat"
      - run: echo random-number ${{ steps.foo.outputs.random-number }}
        shell: bash
```

<!-- end examples -->
<!-- start [.github/ghdocs/examples/] -->
<!-- end [.github/ghdocs/examples/] -->
