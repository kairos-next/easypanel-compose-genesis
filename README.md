# easypanel-compose-genesis

Compose do Supabase self-hosted do **Genesis CRM** no EasyPanel (VPS 187.77.47.91, projeto `genesis`).
Base: `kairos-next/easypanel-compose-lojistacar` (branch `18-05-2026`), que vem do modelo oficial do
EasyPanel/Supabase, com estas diferenças:

- Postgres **17.6** (`supabase/postgres:17.6.1.084`), igual ao Supabase Cloud de origem.
- Serviço `functions` repassa os segredos do Genesis (não os da LojistaCar).
- Sem `ports` publicados no servidor: o EasyPanel liga só o `kong` à rede `easypanel` pelo domínio.
  Nomes de container ficam `genesis_supabase-*`, sem conflito com `lojista-car_supabase-*`.

Configuração no EasyPanel (serviço `supabase` do projeto `genesis`): Fonte = **Git**, este repositório,
Ramo `main`, Caminho de Build `/supabase/code`. **Nunca trocar a Fonte para docker-compose colado.**
Senhas e chaves só na aba Ambiente (nunca neste repositório).
