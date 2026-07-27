# move-tech-comp5-h1-lab1

Ponto de partida do **Lab H1 — Fazer deploy e observar os logs**.

Parte do curso **Move Tech** — Magalu × Prósper Digital Skills
Formação em Cloud Computing para iniciantes

---

## Contexto

A aplicação já emite logs em formato JSON e expõe os endpoints `/health`, `/stats` e `/metrics`. O pipeline de deploy está pronto.

Seu trabalho neste lab é fazer o deploy no cluster Kubernetes e observar os logs em tempo real.

---

## O que você vai fazer

- [ ] Configurar os Secrets do repositório no GitHub
- [ ] Disparar o deploy via GitHub Actions
- [ ] Acompanhar os pods ficarem Running
- [ ] Ler os logs em tempo real com `kubectl logs`
- [ ] Criar um pedido e observar o evento `order_created` nos logs
- [ ] Provocar um erro e filtrá-lo com `jq`

---

## Secrets necessários no GitHub

Configure em **Settings → Secrets and variables → Actions**:

| Secret | Descrição |
|---|---|
| `MGC_REGISTRY_USER` | Usuário do Container Registry da MGC |
| `MGC_REGISTRY_PASSWORD` | Senha do Container Registry da MGC |
| `MGC_REGISTRY_NAME` | Nome do registry na MGC |
| `MGC_KUBECONFIG` | Conteúdo do kubeconfig (`~/k3s.sh kubernetes cluster kubeconfig --cluster-id <ID> --raw`) |
| `DATABASE_URL` | String de conexão do PostgreSQL (`postgresql://user:pass@host/orders`) |

---

## Como rodar localmente

**Pré-requisito:** [Docker Desktop](https://www.docker.com/products/docker-desktop/) instalado (Mac e Windows) ou [Docker Engine](https://docs.docker.com/engine/install/) (Linux).

```bash
docker compose up --build
```

Acesse a documentação interativa em: http://localhost:8000/docs
