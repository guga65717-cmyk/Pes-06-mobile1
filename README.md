# PES6 Mobile — starter Android

Este repositório contém o primeiro esqueleto Android: seletor de imagem ISO/CSO,
tela horizontal e protótipo visual de controles de futebol.

## Estado real desta versão

**Ainda não é um emulador funcional.** O seletor apenas recebe a URI da imagem;
o protótipo desenha controles, mas eles ainda não enviam comandos a um núcleo PS2.
Não instale esperando que o PES já abra.

## Próxima integração do emulador

O núcleo escolhido para avaliação é [Play!](https://github.com/jpd002/Play-).
O projeto oficial possui uma aplicação Android em `build_android/` e documenta
a compilação com Gradle. A documentação do núcleo lista ISO e CSO entre os
formatos suportados pelo core Libretro; validar suporte no frontend Android
e a API de controle é uma etapa obrigatória antes de afirmar compatibilidade.

Plano técnico:
1. Fixar uma revisão do Play! e incluir seus submódulos.
2. Compilar o núcleo nativo para `arm64-v8a` com NDK/CMake.
3. Integrar a superfície de vídeo e o ciclo de vida do emulador à Activity.
4. Converter toques do `SoccerPadView` em eventos do controle PS2 (D-pad,
   Cross, Circle, Square, Triangle, L1/L2/R1/R2, Start/Select e analógicos).
5. Testar imagens próprias e legalmente obtidas; medir compatibilidade e FPS.

## Compilar a estrutura pela nuvem

1. Crie um repositório GitHub vazio chamado `PES6-Mobile`.
2. Envie todos os arquivos desta pasta para a branch `main`.
3. Abra **Actions** e execute **Build Android APK** (ou faça um push).
4. Baixe o artefato `PES6-Mobile-debug` no fim da execução.

O APK gerado nesta etapa é somente o protótipo da interface.

## Requisitos

- Android 8.0 ou superior (minSdk 26).
- Java 17, Gradle 8.9, Android SDK 35.
- Jogos não são incluídos. Use somente dumps de discos que você tenha direito de usar.
- Este projeto não inclui BIOS proprietário; o Play! declara usar HLE BIOS integrado.

## Controles pretendidos para futebol

- Analógico esquerdo / D-pad: movimentação
- X: passe
- Quadrado: chute
- Triângulo: enfiada
- Círculo: carrinho / ação contextual
- L1/L2/R1/R2: corrida, proteção e táticas (mapeamento final configurável)

## Licenças

O código deste esqueleto é fornecido como material de partida. Antes de redistribuir
uma versão que incorpore Play!, leia e cumpra a licença e os avisos de terceiros
do repositório original.
