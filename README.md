# Registro de Ponto Facial

Trabalho de faculdade de 2022, retomado e finalizado em 2026. É um sistema de ponto em Java que identifica o funcionário comparando a foto tirada na hora com as fotos cadastradas e registra a hora de quem foi reconhecido.

A comparação é da imagem inteira, pixel a pixel, sem detectar rosto nem usar aprendizado de máquina. Por isso o resultado depende de luz e enquadramento parecidos entre o cadastro e a hora do ponto.

<img src="https://raw.githubusercontent.com/guavovic/registro-de-ponto-facial/main/docs/assets/ponto-facial.gif" alt="Tela do programa reconhecendo dois funcionários e recusando um rosto que não está cadastrado" width="100%">

<sub>Rostos de exemplo: avatares do <a href="https://www.dicebear.com">DiceBear</a> (estilo Lorelei), licença <a href="https://creativecommons.org/publicdomain/zero/1.0/">CC0</a>.</sub>

**Tecnologias:** Java 25, Swing, SQLite e OpenCV.

As decisões do projeto estão em [`docs/decisions`](docs/decisions).

---

<sub>Licença [MIT](LICENSE) · Feito por [Gustavo Victor](https://github.com/guavovic)</sub>
