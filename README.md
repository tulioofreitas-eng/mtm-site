# Site MTM Group

Site institucional da holding. Domínio já definido: mtmgroup.com.br.

## Decisão de conteúdo (17/jul)

A página **Empresas** mostra só as 5 empresas PRESENTES (Royal Splash,
Viabilix, Syon, Construtora, Tatu) — de propósito, não lista as empresas
futuras (Empreiteira, Projetos, Arka Gessos, etc.). Esse roadmap é
informação interna, não faz sentido expor publicamente antes de cada uma
existir de fato. Se quiser mudar isso, é só avisar.

**Syon aparece sem link** — o site dela está publicado mas não deve ser
divulgado ainda (só quando os 3 empreendimentos estiverem prontos, decisão
já registrada). Quando isso mudar, adiciona o link em `index.astro` e
`empresas.astro`, mesmo padrão do Royal Splash e Viabilix.

## Setup — igual aos outros projetos (WSL2, agora)

```bash
cd ~/projetos
git clone <url-do-repo> mtm-site
cd mtm-site
pnpm install
pnpm run build
```

Se pedir aprovação de build (`sharp`/`esbuild`): `pnpm approve-builds`.

Variáveis de ambiente (Vercel → Environment Variables, e `.env` local):
```
SUPABASE_URL=https://ndabjzvtuelpuooyngdw.supabase.co
SUPABASE_SERVICE_ROLE_KEY=<secret key do Supabase>
```

## Domínio

Esse é o primeiro site do grupo com domínio próprio já definido desde o
início — `mtmgroup.com.br` (já verificado no Resend). Depois de publicar no
Vercel, adiciona o domínio em **Project Settings → Domains** e aponta o DNS
(registro.br) pro Vercel — os registros exatos aparecem na própria tela do
Vercel quando você adiciona o domínio.

## Estrutura

```
src/pages/
  index.astro       → /
  empresas.astro    → /empresas
  sobre.astro       → /sobre
  contato.astro     → /contato
  api/lead.ts       → endpoint de captura de contato
```

## Pendências

- E-mail de contato ainda é placeholder (`contato@mtmgroup.com.br` — precisa
  ser criado de verdade no domínio)
- Apontar o DNS pro Vercel quando for publicar de vez
