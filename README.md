# SiteForge (Lovable 2)

Aplicação com cadastro/login por e-mail, projetos por usuário, editor HTML/CSS, preview e publicação via Cloudflare Pages.

## 1. Firebase
1. Crie um projeto no Firebase Console.
2. Authentication > Sign-in method > ative Email/Password.
3. Crie o Firestore Database.
4. Registre um Web App e copie a configuração para `config.js`.
5. Publique as regras de `firestore.rules`.

## 2. Worker de publicação
Instale/configure Wrangler e publique a pasta `worker/`.
Defina os secrets `CLOUDFLARE_API_TOKEN`, `CLOUDFLARE_ACCOUNT_ID` e `FIREBASE_WEB_API_KEY`.
O token Cloudflare precisa de permissão para Cloudflare Pages. Nunca coloque o token em `config.js`.
Depois substitua `DEPLOY_API` em `config.js` pela URL do Worker.

## 3. Hospede o painel
Hospede os arquivos da raiz em qualquer host estático (inclusive Cloudflare Pages). O Firebase exige que o domínio usado esteja autorizado em Authentication > Settings > Authorized domains.

## Observação sobre “IA”
O botão Gerar deste pacote cria uma base local a partir do texto; ele não chama secretamente um modelo pago. Para geração de código por IA real, adicione uma rota protegida no Worker e mantenha a chave do provedor como secret do servidor.
