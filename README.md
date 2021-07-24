# example-multiservice-deploy

Example GitOps deployment repo for a corresponding microservice monorepo, [example-multiservice](https://github.com/codefresh-contrib/example-multiservice).

Organizes its environments within a single branch (main) using a monorepo structure. Each environment subdirectory contains a single umbrella chart with only 2 files: Chart.yaml and values.yaml. Each environment's microservices/versions are listed as subcharts in the `dependencies` section of its Chart.yaml

Benefits

- Subcharts are backed by a Helm Chart Repo, for much simpler version management than Git by itself
- A single branch / monorepo structure makes it very easy to automate promotions between environments
- All image tags can easily be viewed/updated in a single file per environment: the umbrella chart's values.yaml 
- Quickly and easily see all differences between environments with `diff`, for example `diff test/ qa/`
