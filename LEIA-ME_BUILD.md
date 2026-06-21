# CloneCut — Gerar APK pela nuvem (GitHub Actions)

Este projeto já vem pronto pra compilar o APK no GitHub, sem instalar nada
no seu computador (ideal pra Chromebook).

## Passo a passo

1. Crie um repositório novo no GitHub (ex: `clonecut-app`), **vazio**
   (sem README/gitignore).

2. Suba TODOS os arquivos desta pasta pro repositório. Como o projeto tem
   pastas ocultas (`.github`) e arquivos importantes, o jeito mais seguro
   no Chromebook é pela linha de comando do próprio GitHub (veja abaixo) OU
   garantindo que arquivos ocultos apareçam antes de arrastar.

3. Configure a chave do Gemini como segredo:
   - No repositório: **Settings → Secrets and variables → Actions**
   - Botão **New repository secret**
   - Name: `GEMINI_API_KEY`
   - Secret: cole sua chave do Gemini
   - **Add secret**

4. O build dispara sozinho ao subir os arquivos. Vá na aba **Actions**,
   espere ficar verde, e baixe o APK em **Artifacts → clonecut-apk**.

## Observações

- Este é um app nativo complexo (Kotlin/Compose, AGP 9.1, Gemini AI).
  O primeiro build pode falhar por algum detalhe de versão — se acontecer,
  o log na aba Actions diz o que ajustar.
- O `.env` (chave do Gemini) e o `debug.keystore` são gerados
  automaticamente pelo workflow; por isso não estão no repositório.
