# BoraFluent | domínio raiz GitHub Pages

Este repositório **público** cuida somente da raiz do domínio `https://mayconsouza93.github.io/` e da validação Android do BoraFluent.

O código-fonte do aplicativo permanece em `mayconsouza93/borafluent-ingles`, repositório **privado**. A interface web será publicada em `https://mayconsouza93.github.io/borafluent-ingles/`.

## Trusted Web Activity sem barra do Chrome

O navegador Chrome/Android verifica um documento público em:

`https://mayconsouza93.github.io/.well-known/assetlinks.json`

Esse arquivo deve listar `app.borafluent.ingles.pages` e a impressão **SHA-256 pública, REAL, do certificado permanente** que assina o APK. Ele ainda **não existe** porque não devemos publicar um SHA falso. O workflow no repositório privado recusa qualquer APK de Pages sem associação verificada.

A pasta `.well-known` e o arquivo vazio `.nojekyll` já estão preparados. Quando o certificado estiver disponível, o gerador no repositório privado (`scripts/android-pages-dal.mjs generate`) constrói um JSON válido. Copiar somente esse JSON público para `.well-known/assetlinks.json`.

**Nunca incluir keystore .jks, chaves privadas, senhas, Base64 da assinatura, credenciais Firebase ou GEMINI_API_KEY neste repositório.**

## GitHub Pages

Configurar **Settings > Pages > Build and deployment > Deploy from a branch > main > /(root)**. Não usar um workflow que publique o aplicativo completo nesta raiz: o app principal ocupa somente `/borafluent-ingles/`.

Este site é público por definição; a privacidade do repositório principal não é afetada.
