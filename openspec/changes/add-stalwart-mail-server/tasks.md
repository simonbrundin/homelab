## 1. Förberedelser

- [x] 1.1 Skapa katalog `environments/prod/stalwart/`

## 2. PostgreSQL-databas

- [x] 2.1 Skapa `environments/prod/stalwart/database.yaml` (CNPG Cluster)
- [x] 2.2 Skapa `environments/prod/stalwart/database-secret.yaml` (SOPS-krypterad)
- [x] 2.3 Skapa `environments/prod/stalwart/namespace.yaml`

## 3. HelmRepository

- [x] 3.1 Skapa `environments/prod/stalwart/helmrepository.yaml` (kgrubb/stalwart-helm)

## 4. HelmRelease

- [x] 4.1 Skapa `environments/prod/stalwart/helmrelease.yaml`
  - [x] 4.1.1 Konfigurera storage (Longhorn PVC)
  - [x] 4.1.2 Konfigurera SMTP-portar (25, 465, 587)
  - [x] 4.1.3 Konfigurera IMAP-portar (143, 993)
  - [x] 4.1.4 Konfigurera JMAP (8080)
  - [x] 4.1.5 Sätt `recoveryAdmin` för initial admin
  - [ ] 4.1.6 Konfigurera PostgreSQL-backend (skjut upp till senare)
  - [x] 4.1.7 Använd RocksDB istället (enklare för homelab)

## 5. Ingress/routing

- [x] 5.1 Skapa `environments/prod/stalwart/http-route.yaml` för `mail.simonbrundin.com`

## 6. Kustomization

- [x] 6.1 Skapa `environments/prod/stalwart/kustomization.yaml`
- [x] 6.2 Lägg till `stalwart` till `environments/prod/kustomization.yaml`

## 7. Verifiering

- [x] 7.1 Kör `kubectl kustomize environments/prod/stalwart` (validerar ✓)

## 8. Deployment & Setup

- [ ] 8.1 Push ändringar till Git
- [ ] 8.2 Verifiera Flux-rekonsiliation
- [ ] 8.3 Verifiera att podden startar korrekt
- [ ] 8.4 Logga in på webbinterface `https://mail.simonbrundin.com`
- [ ] 8.5 Ändra recoveryAdmin-lösenordet
- [ ] 8.6 Konfigurera domän `simonbrundin.com`
- [ ] 8.7 Skapa mail-användare (t.ex. alfred@simonbrundin.com)

## 9. DNS (krävs för mail att fungera)

- [ ] 9.1 Lägg till MX-record: `simonbrundin.com -> mail.simonbrundin.com`
- [ ] 9.2 Lägg till SPF-record
- [ ] 9.3 Konfigurera DKIM (via Stalwart admin)
- [ ] 9.4 Konfigurera DMARC
