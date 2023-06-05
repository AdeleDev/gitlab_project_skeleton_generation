# Service Skeleton Generation

The job for auto-creation of service structure in gitlab

Set **NAME** variable for name of new service
Requirements to the name:

* must contain exactly the same words as mentioned in the Story which service is generated for
* must be named like tittle: Capitalize Each Word (words are separated by space).
* do not use numbers if they are not expected by Story requirements
* do not set "service" name in the end - it will be added to class names automatically

#### Example of good name: My Test Repo**

#### Wrong variants:

* myTestRepo
* MyTestRepo
* My_test_repo
* MyTestRepoService
* MyTestRepo1

### Built With

* [![Gitlab][Gitlab.io]][Gitlab-url]

## Pre-installations

#### Clone the repo:

```sh
git clone https://github.com/AdeleDev/gitlab_project_skeleton_generation.git
```

## Usage

#### Service structure:

```
NG-FS (group)

    <Service Name> (group)
        <service-name>-service
        <service-name>-api
        <service-name>-frontend (optional)
        <service-name>-b4f (optional)
```

#### Variables configuration:

You can specify variable **SHORT_NAME**. It used in database usernames and passwords.
If variable not set, then in generated skeleton need to set manually:

```
* flyway db names in file ".gitlab-ci.yml"
* datasource.username in file "src/main/resources/application.yaml"
* datasource.username in file "src/integration-test/resources/application.yaml"
* datasource.username in config maps app-config-dev.yaml, app-config-sit.yaml, app-config-prf.yaml
```

Also, you need manually set:

```
SSH_PRIVATE_KEY in Service env.variables in Gitlab
```

<!-- MARKDOWN LINKS & IMAGES -->

[Gitlab.io]: https://img.shields.io/badge/-GitLab-blueviolet?style=for-the-badge&logo=gitlab

[Gitlab-url]: https://about.gitlab.com/
