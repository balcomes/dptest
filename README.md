Data Product dp_test1_us001
================

To build and deploy

### STEP 1: Activate the project

Clone the project, set working directory to project top folder and
activate

``` r
dpbuild::dp_activate(project_path = ".")
```

### STEP 2: Set environment variables

Set `GITHUB_PAT` as environment variable for
<https://github.com/balcomes/dptest.git>

``` r
Sys.setenv("GITHUB_PAT" = "<GIHTUB_PAT for the remote url>")
```

Set environment variables as needed to enable evaluation of

`creds_set_aws(key = Sys.getenv("AWS_KEY"), secret = Sys.getenv("AWS_SECRET"))`

and order to access the data board

| board_type | board_alias | bucket_name | region    |
|:-----------|:------------|:------------|:----------|
| s3_board   | cars_board  | jadecanary  | us-east-2 |

### STEP 3: Build

This by convention involves sourcing the main script `dp_make.R`

``` r
source("./dp_make.R")
```

### STEP 4: Deploy

Simple call to `dpdeploy`. By default expects you to be in the project
directory

``` r
dpdeploy()
```
