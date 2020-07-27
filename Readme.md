Repo to give example of dependency issue I have with helm.

Step to reproduce
1. Clone the repo
2. Note that mysql.enabled value in values.yaml is set to false
3. Render chart and notice that mysql artifacts would be created in kubernetes

```$xslt
git clone https://github.com/pjastrzabek/helm_dependency_bug.git
cd helm_dependency_bug
helm package --dependency-update ./
helm upgrade --install --debug --dry-run goodly-guppy  -v 3 ./  | less
```
