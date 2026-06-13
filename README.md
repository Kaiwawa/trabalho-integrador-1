# Trabalho Integrador 1
### Configurar pipeline para:
	- Validar CIS Docker Benchmark via Dockle
	- Integrar trivy para bloquear caso haja vulnerabilidade Critica
	- Assinar a imagem com Cosign
	- Publicar SBOM CycloneDX

### Verificar cosing:
```
cosign verify ghcr.io/kaiwawa/trabalho-integrador-1@sha256:995242544c2bd60b5dd69c0d83e57087f6b95ac7739e89a9ac5127a4044a21d5   --certificate-identity-regexp "https://github.com/Kaiwawa/.*"   --certificate-oidc-issuer "https://token.actions.githubusercontent.com"
```
