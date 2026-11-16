# The Supreme Shooting Range — Trabalho Final de FCG

Jogo 3D de tiro ao alvo em primeira pessoa desenvolvido em **C++** e **OpenGL 3.3** como trabalho final da disciplina **INF01047 - Fundamentos de Computação Gráfica** na Universidade Federal do Rio Grande do Sul (UFRGS).

## Autores

- **Andrei Pochmann Koenich**
- **Gustavo Spellmeier Neves**

## Sobre o Projeto

O jogo consiste em um campo de treinamento de tiro ao alvo em 3D. O objetivo do jogador é destruir todos os alvos terrestres e esferas flutuantes espalhados pelo cenário. Ao destruir todos os alvos, o jogador é transportado para a cena final de vitória para visualizar o troféu.

### Conceitos de Computação Gráfica Aplicados

- **Transformações Geométricas e Modelagem 3D:** posicionamento, rotação e escala de malhas poligonais carregadas via arquivos `.obj`, além de projéteis alinhados dinamicamente ao vetor *view*.
- **Câmeras Virtuais:**
  - *Free Camera* em primeira pessoa no cenário principal (com HUD de arma e mira *crosshair* renderizados em coordenadas de tela).
  - *Look-At Camera* controlada pelo mouse no cenário final de exibição do troféu.
- **Iluminação e Sombreamento:**
  - Modelo de iluminação **Blinn-Phong** com interpolação de **Gouraud** nas esferas flutuantes.
  - Iluminação difusa (**Lambert**) nos demais objetos do cenário.
- **Mapeamento de Texturas:** projeção esférica para as *skyboxes* e projeção planar/UV para objetos do cenário e tela inicial.
- **Animações Baseadas no Tempo:** movimentação linear independente de taxa de quadros (*delta time*) e trajetória parametrizada por **Curva de Bézier Cúbica**.
- **Testes de Colisão/Intersecção:**
  - *Ponto-Cubo (AABB):* colisão dos projéteis com alvos e obstáculos (caixas de madeira, paletes e barreiras de concreto).
  - *Ponto-Esfera:* colisão dos projéteis com as esferas flutuantes.
  - *Linha-Plano:* limitação da área de movimentação do jogador no cenário.

## Controles

| Comando | Ação |
| :--- | :--- |
| `ENTER` | Inicia o jogo na tela inicial |
| `W`, `A`, `S`, `D` | Movimenta o jogador pelo cenário |
| `Mouse` | Movimenta a câmera / mira (ou orbita o troféu na cena final com o botão esquerdo pressionado) |
| `Botão Esquerdo do Mouse` | Dispara projéteis |
| `Scroll do Mouse` | Zoom da câmera (aproxima/afasta) |
| `ESC` | Encerra a aplicação |

## Compilação e Execução

### Windows (Code::Blocks)
1. Abra o arquivo `Trabalho Final.cbp` no **Code::Blocks**.
2. Selecione o *build target* apropriado (`Debug` / `Release`, ou a variante `CBlocks 17.12 32-bit` caso utilize o compilador MinGW 32 bits do Code::Blocks 17.12).
3. Pressione **Build and run (F9)**.

### Linux
```bash
make run
```

### macOS
```bash
make -f Makefile.macOS run
```

## Demonstração

- [Vídeo de apresentação no YouTube](https://www.youtube.com/watch?v=g1PKVuQvBYw)
