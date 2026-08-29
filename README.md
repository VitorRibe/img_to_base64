# Conversor Local Base64 com Compressão

Aplicação web client-side de arquivo único (HTML/CSS/JS) que converte imagens para strings Base64. A ferramenta aplica redimensionamento e compressão automaticamente via **Canvas API** antes da codificação, otimizando o tamanho final da string gerada. 

Toda a operação ocorre no navegador (offline), sem envio de dados para servidores externos.

## 🛠️ Tecnologias Utilizadas
* **HTML5:** Utilização da `File API` e `<canvas>`.
* **CSS3:** Estilização responsiva sem frameworks ou dependências externas.
* **Vanilla JavaScript:** Lógica de manipulação de arquivo, processamento de imagem e interface.

## ⚙️ Funcionalidades e Detalhes Técnicos

* **Processamento Local (Offline):** Utiliza a classe `FileReader` para ler o binário da imagem diretamente da máquina do usuário.
* **Redimensionamento Proporcional:** Limita as dimensões máximas (largura ou altura) a **800px**, preservando o *aspect ratio*.
* **Compressão Dinâmica:** A imagem renderizada no canvas é exportada utilizando `canvas.toDataURL('image/jpeg', 0.7)`, forçando formato JPEG com **70% de qualidade visual**.
* **Tratamento de Canal Alfa (Transparência):** Preenche o canvas com fundo branco (`#FFFFFF`) para evitar que imagens PNG transparentes resultem em fundo preto.
* **Telemetria de Compressão:** Calcula e exibe o tamanho original vs. o tamanho final estimado em KB e a porcentagem de redução.
* **Clipboard API:** Botão para copiar a string Base64 resultante com feedback visual.

## 🚀 Como Executar

Nenhuma etapa de build é necessária.
1. Salve o código fonte em um arquivo com a extensão `.html` (ex: `index.html`).
2. Abra o arquivo diretamente em qualquer navegador web moderno.

## 🗂️ Formatos de Entrada Suportados
* `.JPG` / `.JPEG`
* `.PNG`
* `.WEBP`

*(Nota: Independentemente do formato de entrada, o output Base64 será codificado sob o MIME type `image/jpeg`)*.
