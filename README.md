# Cotoco · A ou B

Votação entre amigos: alguém cria uma pergunta com duas opções (A e B), manda o link, e cada pessoa escolhe uma opção **e justifica o voto**. Os votos e as justificativas aparecem para todo mundo.

- Página única: `index.html` (HTML + JS puro, sem build).
- Votos guardados no Supabase, tabelas `cotoco_votacoes` e `cotoco_votos`. A chave pública só permite ler e adicionar; ninguém consegue apagar nem alterar voto pelo site.
- Um voto por nome em cada votação.
- Publicado pelo GitHub Pages.
