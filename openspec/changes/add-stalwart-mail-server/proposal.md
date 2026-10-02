## Why

Jag vill ha en komplett, självhostad e-postlösning för min domän. Stalwart är ett modernt, open-source mail server-projekt som tillhandahåller SMTP, IMAP, JMAP och ett inbyggt webbinterface.

## What Changes

- Lägg till Stalwart Mail Server som ny produktionsapplikation
- Skapa egen CNPG PostgreSQL-databas för Stalwart (separat från andra tjänster)
- Konfigurera SMTP för inkommande/utgående mail på `simonbrundin.com`
- Exponera webbinterface via HTTPRoute på `mail.simonbrundin.com`
- Lägg till tjänsten i `environments/prod/kustomization.yaml`
- Konfigurera mail storage på Longhorn PVC

## Impact

- **Ny applikation**: `environments/prod/stalwart/`
- **Ny databas**: CNPG PostgreSQL Cluster för stalwart
- **Namespace**: `stalwart`
- **Hostname**: `mail.simonbrundin.com`
- **Påverkar**: `environments/prod/kustomization.yaml` (root kustomization)
- **Nytt HelmRepository**: `kgrubb/stalwart-helm` (om inte redan definierat)
