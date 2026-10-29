# eks-gitops-config

Manifestos GitOps da plataforma [`eks-gitops-platform`](https://github.com/heldemfilipe/eks-gitops-platform), lidos
pelo Argo CD. Qualquer mudança no cluster entra por pull request neste repositório.

> **Status:** projeto de estudo, em construção. O cluster é um `kind` local; nada é aplicado na AWS.

## Estrutura

```text
eks-gitops-config/
├── root.yaml              Application raiz, aplicada uma vez (Etapa 1)
├── apps/                  uma Application por componente
└── workloads/
    └── pedidos/           Deployment, Service e Ingress (Kustomize)
```

## Ambientes

Um só (`workloads/pedidos/`), sem overlays: um laboratório não justifica `dev` e `prod`. A decisão final fica
registrada aqui na Etapa 4.

## Segredos

Nada de segredo no Git. O Secret da API é entregue pelo External Secrets (Etapa 3).

## Licença

MIT. Veja [LICENSE](LICENSE).
