# ci-deploy-action
GitHub Action to setup and run the deployment script on AWS

## How To Use
```yml
name: deploy

on:
  push:
    branches:
      - release
      - staging

jobs:
  deployment:
    runs-on: ubuntu-latest
    steps:
      - name: deploy
        uses: eco-trip/ci-deploy-action@v1.0
        with:
          AWS_ACCESS_KEY_ID: ${{ secrets.AWS_ACCESS_KEY_ID }}
          AWS_SECRET_ACCESS_KEY: ${{ secrets.AWS_SECRET_ACCESS_KEY }}
          token: ${{ secrets.MEBBOT }}
          # script: cd deploy || bash deploy.sh -e ${{ steps.extract_env.outputs.ENV }} [default]
```
