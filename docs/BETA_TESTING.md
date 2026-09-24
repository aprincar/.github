# Testando o beta do Aprincar

O Aprincar está disponível para exploração pública em:

**https://aprincar.github.io/platform/**

## O que validar

Ao testar, priorize problemas observáveis:

1. carregamento e navegação da aplicação;
2. entrada, saída e reinício de jogos;
3. clareza das instruções para a criança;
4. coerência entre desafio, resposta esperada e feedback;
5. controles por toque, mouse e teclado quando aplicável;
6. travamentos, estados sem saída ou interações que deixam de responder;
7. comportamento offline depois que os recursos já foram carregados;
8. regressões visuais em celular, tablet e desktop.

## Estado do beta

A infraestrutura da V1 está publicada, mas o catálogo de jogos está em hardening. Alguns jogos podem apresentar regras pouco claras, desafios imprecisos ou comportamento inconsistente.

Por isso, nesta fase:

- feedback de funcionamento real tem prioridade;
- precisão pedagógica deve ser revisada jogo a jogo;
- problemas reproduzíveis devem virar issues específicas;
- alterações estruturais no runtime devem ser justificadas por evidência, não por preferência estética.

## Como reportar

Abra uma issue no repositório correspondente:

- problemas da aplicação, navegação, instalação, progresso ou runtime: [aprincar/platform](https://github.com/aprincar/platform/issues);
- bugs, regras, interação ou precisão de jogos oficiais: [aprincar/games-official](https://github.com/aprincar/games-official/issues);
- problemas de templates ou autoria: use o repositório do template correspondente.

Inclua, quando possível:

- jogo ou tela;
- dispositivo e navegador;
- passos para reproduzir;
- resultado observado;
- resultado esperado;
- captura de tela ou vídeo curto;
- se o problema ocorre sempre ou de forma intermitente.

## O que o beta não promete ainda

O beta não deve ser tratado como validação pedagógica final de todo o catálogo oficial. A arquitetura, os contratos e a distribuição estão estabilizados na V1; a qualidade de experiência e a precisão dos jogos passam agora por uma sprint dedicada.
