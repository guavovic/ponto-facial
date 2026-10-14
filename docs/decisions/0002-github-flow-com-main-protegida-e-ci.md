# 2. GitHub Flow com main protegida e CI

Data: 01/10/2026

Status: Aceito

## Contexto

Toda mudança era commitada direto na `main`, sem nada conferindo se o código ainda compilava. O projeto tem uma pessoa só mantendo. A v1 é o sistema como foi entregue na faculdade, e as mudanças a partir desta decisão formam a v2.

## Opções consideradas

- **Git Flow**, com uma branch `develop` de vida longa, mais branches de release e hotfix. Feito para software com várias versões em suporte ao mesmo tempo e para times maiores.
- **GitHub Flow**: a `main` está sempre pronta, cada mudança vai numa branch curta e entra na `main` por pull request.
- **Trunk-based** com commit direto na `main`. Rápido, mas abre mão da PR como registro de cada mudança.

## Decisão

GitHub Flow.

- Toda mudança vai numa branch própria (`feat/...`, `fix/...`, `chore/...`) e entra na `main` por pull request.
- A `main` é protegida: pull request obrigatória, e o check `Build` precisa passar antes do merge. A regra vale também para administradores.
- O workflow de CI roda o build completo com o JDK 25 em toda pull request e em todo push na `main`. Aviso de compilação quebra o build.
- O CI roda só no Linux. O bytecode é o mesmo em qualquer sistema, então compilar em três não acrescenta nada por enquanto. Quando houver testes que dependem do sistema, como os de caminho de arquivo, o workflow ganha uma matriz com Windows e macOS.
- As dependências e o próprio workflow são atualizados de forma automática e periódica, com as mudanças agrupadas. As correções de segurança chegam pelos alertas do GitHub assim que saem.
- As versões são tags na `main` (`v1.0.0` marca o sistema da faculdade, e a v2 sai como tag quando a trilha fechar).

## Consequências

- A `main` só recebe código que compila sem avisos.
- Cada mudança tem uma pull request explicando o que faz e como foi testada.
- Os testes entram no workflow conforme forem escritos.
