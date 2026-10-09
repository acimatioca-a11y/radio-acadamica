RÁDIO ACADÉMICA — PORTAL MULTIMÉDIA PARTILHADO
================================================

Inclui o emblema enviado, painel personalizado, publicações de fotografia/áudio/vídeo, gostos, comentários, quatro espaços publicitários com transições e estatísticas agregadas de visitas.

Código de administrador inicial: RosaAmarela@700
Abrir painel: clicar 15 vezes seguidas no botão “Publicidade” do rodapé.
IMPORTANTE: altera o código ADMIN_CODE em netlify/functions/content.mjs antes de publicar, para um código só teu.

COMO FUNCIONA A PARTILHA
A lista de publicações, gostos, comentários, anúncios e estatísticas é guardada em Netlify Blobs, através da função netlify/functions/content.mjs. Os ficheiros de media são enviados para o Cloudinary. Assim, todos os visitantes do mesmo site consultam a mesma lista de publicações.

PASSO 1 — CONFIGURAR CLOUDINARY (necessário para publicar media)
1. Cria conta em https://cloudinary.com/.
2. No painel, copia o “Cloud name”.
3. Em Settings > Upload > Upload presets, cria um preset com modo “Unsigned”.
4. Abre config.js e substitui COLOCA_AQUI_O_CLOUD_NAME e COLOCA_AQUI_O_UPLOAD_PRESET pelos teus valores.
5. Nunca coloques uma API Secret no config.js. Um preset unsigned pode ser utilizado por terceiros se for descoberto; limita formatos e vigia a quota da conta.

LIMITES configurados na interface: fotografias até 10 MB, áudio até 40 MB, vídeo até 70 MB. O limite efetivo depende da conta e das políticas do Cloudinary. Cada áudio/vídeo pode receber imagem de capa.

PASSO 2 — PUBLICAR NA NETLIFY COM FUNÇÕES ATIVAS
1. Extrai o ZIP para uma pasta.
2. Cria um repositório no GitHub e envia TODOS os ficheiros/pastas, incluindo netlify/functions, package.json e netlify.toml.
3. Abre https://app.netlify.com/ e importa o repositório do GitHub como um novo site.
4. Mantém as definições de build de netlify.toml. A Netlify instala @netlify/blobs e publica a função.
5. Espera pelo deploy e abre o endereço do site. A opção de arrastar e largar apenas ficheiros estáticos não ativa a função de servidor.

FUNÇÕES
- Gostos e comentários guardados no servidor.
- Painel para gerir publicações e moderar comentários.
- Quatro anúncios, com imagem e ligação opcional, geridos no painel.
- Controlo de visitas com totais agregados e contagem aproximada de visitantes por identificador aleatório no navegador. Não identifica pessoas pelo nome nem recolhe localização precisa.
- Atualização automática da página a cada 30 segundos.

SEGURANÇA E LIMITAÇÕES
- O código de administrador é verificado no servidor, mas usa um código partilhado fixo. Troca-o antes de publicar e não partilhes o ZIP publicamente.
- Os 15 cliques escondem a entrada, mas não são uma medida de segurança.
- O upload unsigned do Cloudinary é simples para iniciantes, mas não é tão seguro como uploads assinados. Não guardes dados pessoais sensíveis no site.
- A contagem de visitas é indicativa, pode incluir acessos repetidos de navegadores diferentes e não é uma ferramenta de análise profissional.
- Os conteúdos ficam partilhados entre visitantes do mesmo site apenas depois de configurar o Cloudinary e publicar corretamente a função Netlify.
