# Helm Charts
### How to create repository for helm charts
- Create a new repository in github
- Clone the repository to your local machine
- Add the helm charts to the repository by following the steps below
- Publish the repository to github `pages` from the `settings` of the repository
- Select the source as a `Deployment from branch`option and select the branch as `master` and the directory as `/(root)` and click on save
- This will publish the repository to the github pages and the `url` will be available in the settings of the repository .
- This url should be used in `Step 4` to create/update the `index.yaml` file

### Steps to add helm charts to the repository
- Step 1: Create a new directory for your chart in charts/ directory
- Step 2: Create a new chart using helm create command or copy an existing chart 
- Step 3: package the chart using helm package command in root directory
```yaml
helm package charts/<chart-name>
```
This will create a tarball in the current directory with the name <chart-name>-<version>.tgz

- Step 4: Update the index.yaml file using helm repo index command
```yaml
helm repo index --url https://<username>.github.io/<repo-name>/ .
```
### Add/update helm repository to the helm client
```yaml
helm repo add <repo-name> https://<username>.github.io/<repo-name>
```
```yaml
helm repo update
```