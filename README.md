# 🏓 Classic Pong Game in Java

Uma recriação clássica e retro do famoso jogo **Pong**, desenvolvida em Java utilizando a biblioteca gráfica nativa (`java.awt` e `javax.swing`). O projeto aplica conceitos de desenvolvimento de jogos 2D, como loop principal (*game loop*), renderização em pixel art com dimensionamento (scale), inteligência artificial simples para o oponente e tratamento de colisões.

---

## 🎮 Sobre o Jogo

O jogo coloca o jogador em uma partida contra a CPU. A arena possui um estilo retrô em pixel art (resolução nativa de 160x120 pixels reescalada em 3x).

- **Jogador (Barra Azul):** Localizado na parte inferior da tela.
- **Inimigo / CPU (Barra Vermelha):** Localizado na parte superior da tela.
- **Bola (Quadrado Amarelo):** Movimenta-se pela tela rebatendo nas paredes laterais e nos raquetes.

---

## 🕹️ Controles

| Tecla | Ação |
| :--- | :--- |
| **Seta para a Esquerda (`←`)** | Move o jogador para a esquerda |
| **Seta para a Direita (`→`)** | Move o jogador para a direita |

---

## 🛠️ Tecnologias e Conceitos Utilizados

- **Linguagem:** Java (JDK 8+)
- **Interface Gráfica:** `JFrame`, `Canvas`, `Graphics` e `BufferStrategy` (com Triplo Buffering para evitar flickering).
- **Pixel Art Scaling:** Renderização interna em baixa resolução (`160x120`) desenhada em uma `BufferedImage` e reescalada na tela (`480x360`).
- **Game Loop:** Loop de execução com taxa de atualização de aproximadamente 60 FPS (`Thread.sleep(1000/60)`).
- **Inteligência Artificial (Oponente):** Segue a posição X da bola de forma suave através de interpolação linear simples.
- **Física & Colisão:**
  - Colisão com as bordas da tela e rebate automático.
  - Colisão via `java.awt.Rectangle` entre a bola, o jogador e o inimigo.
  - Cálculo de ângulo do rebate da bola utilizando funções trigonométricas (`Math.cos` e `Math.sin`).

---

## 📂 Estrutura do Projeto

```text
src/
 └── pong/
      ├── Game.java    # Classe principal, janela, game loop e gerenciamento dos eventos do teclado
      ├── Player.java  # Lógica de movimentação e renderização do jogador
      ├── Enemy.java   # Lógica e IA do oponente
      └── Ball.java    # Lógica de movimentação, angulação, colisões e pontuação da bola
