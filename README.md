from zipfile import ZipFile
import os

# Conteúdo HTML do site com a carta, fotos, botão e música
html_content = """
<!DOCTYPE html>
<html lang="pt-br">
<head>
  <meta charset="UTF-8" />
  <title>FELIZ 09 MESES PARA NÓS</title>
  <style>
    body {
      background-color: #f5f3e7;
      color: #1f1f1f;
      font-family: 'Arial', sans-serif;
      text-align: center;
      padding: 20px;
    }
    h1 {
      color: #1f1f1f;
    }
    .highlight {
      color: #3b6b4c;
      font-weight: bold;
    }
    img {
      max-width: 90%;
      margin: 20px 0;
      border-radius: 12px;
    }
    .button {
      background-color: #3b6b4c;
      color: white;
      padding: 12px 24px;
      border: none;
      border-radius: 10px;
      font-size: 16px;
      cursor: pointer;
      margin-top: 30px;
    }
    .footer {
      margin-top: 40px;
      font-size: 14px;
      color: #444;
    }
  </style>
</head>
<body>
  <h1 class="highlight">FELIZ 09 MESES PARA NÓS</h1>
  <p>Meu amor,</p>
  <p>Hoje completamos nove meses… cada vez mais perto do nosso primeiro ano. E em todos os dias até aqui, você me fez feliz.</p>
  <p>Com todas as primeiras fases que vivemos, todas as nossas primeiras vezes — tudo ainda é tão novo e experimental… e mesmo assim, temos ido tão bem.</p>
  <p>Obrigada por me fazer feliz todos os dias, sem exceção.<br>O meu amor por você é real, bonito e especial — e, acima de tudo, abençoado por Deus.</p>
  <p>Eu te amo demais.<br><strong>Feliz nove meses para nós 💛</strong></p>
  <p><em>“So let’s call it forever,<br>
  'Cause I know in my heart<br>
  There’ll never be another<br>
  Who loves me the way that you are.”</em><br>— Mark Barlow 🎵</p>
  
  <img src="foto1.jpg" alt="Foto 1" />
  <img src="foto2.jpg" alt="Foto 2" />
  <img src="foto3.jpg" alt="Foto 3" />

  <br><button class="button">Te amo 💚</button>

  <div class="footer">
    <h3>Tradução da música "Let's Call It Forever" 💚</h3>
    <p>
      Você me encontrou<br>
      No meio de uma ligação perdida<br>
      E tudo o que eu ouvi<br>
      Foi o som do seu sorriso<br>
      E eu sabia que era você<br><br>

      Eu tentei esquecer<br>
      Mas você fez questão de ser lembrado<br>
      Então como eu poderia me arrepender<br>
      De correr atrás do que me faz melhor?<br><br>

      <strong>Então vamos chamar isso de para sempre</strong><br>
      Porque eu sei, no meu coração<br>
      Que nunca haverá outro<br>
      Que me ame do jeito que você é<br><br>

      Sim, você é tudo<br>
      Eu nem sei como comecei<br>
      A viver antes de você<br>
      Mas agora estou aqui de verdade<br>
      E eu não vou mais embora
    </p>
  </div>

  <audio autoplay loop>
    <source src="music.mp3" type="audio/mpeg">
    Seu navegador não suporta áudio.
  </audio>
</body>
</html>
"""

# Caminhos de destino
site_dir = "/mnt/data/romantic_9months_github"
os.makedirs(site_dir, exist_ok=True)

# Salvar HTML
with open(os.path.join(site_dir, "index.html"), "w", encoding="utf-8") as f:
    f.write(html_content)

# Copiar as imagens e música
shutil.copy("/mnt/data/file-3yuHaZQBAUvS5vJysnzwTs", os.path.join(site_dir, "foto1.jpg"))
shutil.copy("/mnt/data/file-FA6AmvnyQ3dyJR43cKKh6R", os.path.join(site_dir, "foto2.jpg"))
shutil.copy("/mnt/data/file-7yfzxoPcG5MLsqHhFztQfE", os.path.join(site_dir, "foto3.jpg"))
shutil.copy("/mnt/data/lets_call_it_forever.mp3", os.path.join(site_dir, "music.mp3"))

# Criar ZIP final
zip_path = "/mnt/data/site_romantico_github.zip"
shutil.make_archive(zip_path.replace(".zip", ""), 'zip', site_dir)

zip_path
