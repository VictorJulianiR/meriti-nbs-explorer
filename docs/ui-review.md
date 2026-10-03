# Prévia da interface de Meriti

Branch `codex/meriti-ui-review`, baseada na branch `main` deste repositório público. Usa os mesmos dados científicos. Para abrir, selecione a branch e execute `npm run dev -- --port 3109`; depois acesse http://localhost:3109. O link "Comparar com versão atual" abre https://meriti-nbs-explorer.vercel.app/. A alternativa permanece isolada da versão principal. Os registros de testes abaixo descrevem a revisão original; a transferência pública está documentada em [PUBLICACAO.md](PUBLICACAO.md).

| Before | After | Why |
| --- | --- | --- |
| Cartões largos ocupam parte da largura do mapa | Controles de 252 px e resultados de 328 px, mapa ocupando o espaço restante em computador | Ampliar a área de inspeção geográfica |
| Combinação de camadas feita em várias caixas de seleção | Seis atalhos, com data ou fonte explícita e estado pressionado | Comparar rapidamente vegetação recente, CBERS, copas de 2019, recorrência de 2025, rios e densidade |
| Navegação longa até o mapa no celular | Mapa antes dos controles, seguido pelos indicadores | Colocar a inspeção territorial no início da página |
| Várias caixas e superfícies dentro dos painéis | Divisórias simples, cor de seleção e rolagem independente em computador | Reduzir a repetição de molduras e manter o mapa visível |
| Comparação visual exige alternar pastas | Link direto para a versão atual | Avaliar a proposta sem substituir a interface anterior |

Datas, fontes, limitações, cálculos, geometrias e fichas científicas são idênticos nas duas branches. Os atalhos apenas selecionam conjuntos de camadas. A decisão de não usar pontuação composta permanece.

## Verificação

Em 03/10/2026, a análise estática, 19 testes unitários e build de produção passaram. Os dez testes de navegador passaram em computador e celular. Eles incluem os oito cenários funcionais da versão principal e o cenário adicional de comparações e validação em dois tamanhos de tela. Capturas em `test-results/meriti-20261003-024224/`.

A primeira rodada encontrou compressão vertical dos painéis no celular, com sobreposição que bloqueava cliques. O fluxo responsivo foi corrigido antes da rodada aprovada. A inspeção visual também corrigiu o contraste do distrito no território selecionado e aumentou o texto das camadas. As imagens de referência foram examinadas após o download completo.

A validação geográfica passou também neste worktree, incluindo todos os hashes. O Git preserva os bytes dos dados científicos sem converter quebras de linha. A revisão adversarial Astra High aprovou o código, a integração científica e a apresentação em computador e celular.
