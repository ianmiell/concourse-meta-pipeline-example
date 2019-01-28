

A pattern to implements a meta-pipeline that dynamically updates a pipeline
whenever the git source changes.

It uses the Concourse pipeline resource:

[Concourse pipeline resource link](https://github.com/concourse/concourse-pipeline-resource)

The files are:

pipeline-update.yml - The meta-pipeline that defines the pipeline to be
pipelines.yml       - The pipeline definition that is applied by the Concourse pipeline resource.
pipeline.yml        - A simple hello-world pipeline to run.

## Usage

To do the initial loading of the pipeline:

```
fly -t yourtarget set-pipeline -c pipeline-update.yml -p meta-pipeline
```

To delete it:

```
fly -t yourtarget destroy-pipeline -p meta-pipeline
```

