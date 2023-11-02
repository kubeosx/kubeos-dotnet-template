
## Getting started with Template

### STEP 1. First create a secrets in vault

```

vault login <token>

vault kv put kubeos/dev/<app-name-in-k8> foo=bar

```

you should replace `<app-name-in-k8>` with the project name you will use in kubernetes.

### STEP 2. Create Dotnet Application using the tempalte
---------------------------------------------------


enter the details requried by the tempalte, rember keeper some in mind

- The name of the kuberneter project should be in lowercase and no spaces
- The name of the Dotnet project should be in PascalCase
- The name of the namespace should be in lowercase and no spaces
- The name of the vault secret should be in lowercase and no spaces
- The tmeplate has the annotation for vault secret, this is the name of the secret in vault.
- The templete ues kustomize to create the project, service account, role and role binding.
- Flux related manifest are created in the flux repo `kubeos-cluster`

This will create the repo, the namespace, the vault secret, the project, the service account, the role and the role binding.

### STEP 3. Deploy the application to kubernetes
---------------------------------------------------


The project repo has the For this a PR will automtically be created.

The PR will have Flux related manifest and are created in the flux repo `kubeos-cluster`, you could reach out to the maintainer to merge the PR.

The vault PR will be created in the vault repo `kubeos-vault-manger`, you can reach out to security team to merge the PR.

### Advantages of using a standard
One Deployment will be created in the namespace you created, the project will be visible in kubeos,

The user can now access the project in kubeos.
- see the project readme for more details
- See the project documentation for more details
- See the project cicd pipeline adn can run it.
- the developer can see the project in kubernetes. and the pod and service related to the project will be visible in kubeos.
- See prometheus metrics for the project.
- could be extended to see the logs of the project.
- Will be able to access pod directly fromt he project.


### Project structure




## Support

That's it. If you need support, make an issue in this repository.
