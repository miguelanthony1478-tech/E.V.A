# E.V.A. PWA — protótipo com alarmes

## O que foi incluído
- Agenda e prioridades do protótipo anterior.
- Botão para pedir permissão de notificações (por ação da usuária).
- Botão de teste de alarme.
- Verificação de tarefas vencidas a cada 10 segundos enquanto a página está ativa.
- Manifesto e service worker básico para instalação/cache da PWA.

## Como testar no computador
1. Extraia o ZIP.
2. Abra um terminal nesta pasta.
3. Execute `python -m http.server 8000`
4. Acesse `http://localhost:8000` no navegador.
5. Clique em **Ativar notificações** e permita.
6. Crie uma tarefa para 1 ou 2 minutos no futuro e mantenha a página aberta.
7. Clique em **Testar alarme** para verificar o aviso imediatamente.

Não abra apenas com `file://`: service workers e algumas permissões exigem HTTPS ou localhost.

## Como testar no Android
A maneira recomendada é publicar a pasta em um host HTTPS e abrir a URL no Chrome Android. Use o menu do navegador para instalar/adicionar à tela inicial. O site precisa estar em HTTPS.

## Limitações importantes
- O navegador pode suspender a página em segundo plano ou fechada. Este protótipo NÃO garante alarmes pontuais quando o app está fechado.
- O service worker aqui faz cache e trata cliques nas notificações; ele não agenda alarmes por conta própria.
- Para alertas confiáveis com o app fechado, a próxima etapa é integrar notificações push com servidor ou criar uma versão Android nativa (por exemplo, Capacitor + plugin de notificações locais).
- Ainda não há autenticação, sincronização entre dispositivos ou armazenamento criptografado.
- Os dados atuais ficam no armazenamento local do navegador. Não use este protótipo para informações médicas sensíveis em dispositivos compartilhados.
