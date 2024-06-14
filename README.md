# navigation

This project is based on the [tsnaketech/hugo-webstack](https://github.com/tsnaketech/hugo-webstack) custom theme.

## Website publication

The site is published using Github Actions. See [deployement.yaml](https://github.com/tsnaketech/navigation/blob/main/.github/workflows/deployment.yaml).

## Setup

### Deploy key

The workflows use deploy_key, so you'll need to create your own.
To get started, create your private and public key using the following command:

```bash
ssh-keygen -t ecdsa -b 521 -C "$(git config user.email)" -f gh-pages -N ""
```

You're free to change the key type, size, file name and so on.

Then, go to your repository settings, and add the public key as a deploy key with **Allow write access**.

Finally, add the private key as a **Repository secrets** in your repository settings, named `ACTIONS_DEPLOY_KEY`.

### Custom domain

If you want to access your navigation with a custom domain.

Go to your FQDN provider and add a **CNAME** entry. In my case `tsnaketech.github.io.`.

In the repository settings under **Page** add a **Custom domain**. In my case `nav.snaketech.net`. And click on **Save**.

|Domain            |Type |Target               |
|------------------|-----|---------------------|
|nav.snaketech.net.|CNAME|tsnaketech.github.io.|