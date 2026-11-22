---
name: sinais-de-escrita-ia
description: Analisa um texto em busca de sinais de escrita gerada por IA, com base no catálogo "Signs of AI writing" do WikiProject AI Cleanup da Wikipédia, ou reescreve um texto para remover esses padrões. Use sempre que o usuário pedir para revisar, checar, auditar ou "detectar" se um texto parece escrito por IA, perguntar quais são os sinais ou vícios de escrita de IA, pedir para deixar um texto com cara humana, ou colar um rascunho e perguntar se "soa como IA", mesmo que não mencione a Wikipédia. Também serve para revisar o próprio texto de Claude antes de entregar.
---

# Sinais de escrita de IA

Esta skill aplica o catálogo de padrões que os editores da Wikipédia (WikiProject AI Cleanup) montaram a partir de milhares de casos reais de texto gerado por IA. O catálogo completo está em `references/patterns.md`. Leia esse arquivo antes de analisar qualquer texto, porque ele traz as categorias, as expressões típicas e o quanto cada sinal pesa.

## A ideia que governa tudo

Nenhum sinal prova autoria. Os modelos aprenderam com escrita humana, então jornalistas, redatores e estudantes também usam regra de três, travessão e tom promocional. A própria página da Wikipédia diz isso e pede que os sinais sejam lidos em conjunto. Por isso a skill nunca dá veredito de "é IA" ou "é humano". Ela mostra evidências, diz o quanto cada uma pesa e deixa a conclusão com o usuário.

Dois motivos práticos para respeitar isso. Primeiro, acusar alguém de usar IA com base em estilo gera falsos positivos, e escritores que não são nativos no idioma são os mais afetados. Segundo, consertar só a superfície esconde o problema de fundo (fato inventado, fonte que não existe, análise vazia) e torna a detecção mais difícil, não o texto melhor.

## Como analisar um texto

1. Leia `references/patterns.md`.
2. Leia o texto inteiro uma vez antes de marcar qualquer coisa, para entender o gênero e o propósito. Um texto de marketing é feito para vender, então tom promocional ali pesa pouco. O mesmo tom numa matéria ou verbete pesa muito.
3. Procure os sinais por categoria e anote o trecho exato de cada ocorrência.
4. Pese o conjunto. Um sinal isolado e fraco não vale um aviso. Vários sinais de categorias diferentes no mesmo trecho valem. Sinais fortes (sobras de chat, marcação de citação de chatbot, referências que não existem) valem sozinhos, mas dizem de onde o texto veio, não se o conteúdo está certo.
5. Verifique o que dá para verificar: abra links, confira se as fontes dizem o que o texto afirma, desconfie de números sem origem. Citação falsa é o problema mais sério da lista porque é erro seja quem for o autor.

## Formato da resposta

Comece pela conclusão em uma ou duas frases: quantos sinais relevantes apareceram, de quais categorias, e se o conjunto é forte ou fraco. Depois liste só o que foi encontrado, agrupado por categoria, cada item com o trecho citado entre aspas e uma frase sobre por que ele pesa ou não. Não liste categorias em que nada apareceu. Feche com os problemas de fundo que merecem checagem (fontes, números, afirmações vagas), porque é isso que o usuário de fato precisa resolver.

Se o idioma do texto for outro que não o inglês, adapte. O catálogo foi observado em inglês, mas os mecanismos se repetem: conclusão inflada, atribuição vaga, paralelismo negativo, tríades, tom de propaganda. As palavras exatas mudam, e uma lista de palavras traduzidas não funciona como régua.

## Quando o pedido for reescrever

Reescrever é diferente de detectar. Corrija primeiro a substância: troque elogio por fato verificável, nomeie a fonte ou corte a afirmação, apague a oração final que só comenta importância, escreva "é" e "tem" onde fizer sentido, transforme "não é X, é Y" numa afirmação direta. Depois cuide da forma: tire marcação que o destino não usa, negrito decorativo e emoji. Preserve o que o texto diz e o jeito do autor. Não troque uma palavra suspeita por um sinônimo igualmente suspeito, e não procure zerar a lista: texto com todos os sinais removidos mecanicamente fica rígido e soa artificial do mesmo jeito. Avise o usuário se algum fato do original não pôde ser confirmado, em vez de deixá-lo passar limpo.

## Limites desta skill

O catálogo é específico da Wikipédia e muda com frequência, porque os modelos mudam. Sinais antigos (como o travessão) já foram movidos para a seção de indicadores históricos. Se o usuário precisar citar a página ou depender de um sinal específico, diga que a lista pode ter mudado e sugira conferir a página original: Wikipedia:Signs of AI writing. Ferramentas automáticas de detecção têm taxa de erro relevante, então esta skill não as usa nem as substitui. Ela ajuda um leitor humano a olhar nos lugares certos.
