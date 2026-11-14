# Cotoco · A ou B

Votação entre amigos em sessões. Quem organiza cria uma sessão e recebe dois links fixos:

- **Link da galera** (`?s=ID`): cada pessoa coloca o nome uma vez e espera o admin liberar a entrada. Depois vota na pergunta da vez (A ou B) com justificativa obrigatória e espera. As próximas perguntas aparecem sozinhas na tela.
- **Link de admin** (`?s=ID&admin=CHAVE`): lança as perguntas, acompanha quem já votou e os votos, encerra a votação e escolhe o que a galera vê depois (nada, quem venceu, ou quem venceu e as justificativas). Também libera quem pede para entrar, libera nomes de quem trocou de aparelho e expulsa quem trapacear (apagando os votos).

## Como funciona por dentro

- Página única: `index.html` (HTML + JS puro, sem build), publicada pelo GitHub Pages.
- Dados no Supabase, tabelas `cotoco_sessoes`, `cotoco_participantes`, `cotoco_perguntas` e `cotoco_votos`. As tabelas ficam fechadas: o site só usa as funções `cotoco_*` do banco.
- Cada jogador recebe um token guardado no aparelho. O admin é reconhecido pela chave do link. As chaves e os tokens ficam salvos só como hash.
- Votos e resultados só saem do banco para quem pode ver: o admin vê tudo, a galera vê o resultado só quando o admin libera.

## Contra trapaça

- Um voto por pessoa em cada pergunta, garantido pelo banco.
- Quem entra só vota depois que o admin libera, então criar um segundo nome não adianta sozinho.
- O admin pode expulsar alguém e apagar todos os votos dessa pessoa.
- O resultado escondido não sai do banco antes da hora, nem para quem mexer no navegador.
