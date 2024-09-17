<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Compartilhe para desbloquear</title>
    <style>
        #progress-container {
            width: 100%;
            background-color: #ddd;
            height: 30px;
            margin: 10px 0;
        }

        #progress-bar {
            height: 100%;
            background-color: #4caf50;
            width: 0%;
        }

        #link-container {
            display: none;
        }
    </style>
</head>
<body>
    <h1>Compartilhe com 5 pessoas para desbloquear o conteúdo!</h1>
    
    <div id="progress-container">
        <div id="progress-bar"></div>
    </div>
    <p id="share-count">0 de 5 compartilhamentos</p>

    <a id="share-btn" href="" target="_blank">
        <button>Compartilhar no WhatsApp</button>
    </a>

    <div id="link-container">
        <h2>Link desbloqueado!</h2>
        <a href="https://go.tribopay.net/wamjb" target="_blank">Acesse o conteúdo</a>
    </div>

    <script>
        let shareCount = 0;

        document.getElementById('share-btn').addEventListener('click', function() {
            if (shareCount < 5) {
                shareCount++;
                let progress = (shareCount / 5) * 100;
                document.getElementById('progress-bar').style.width = progress + '%';
                document.getElementById('share-count').innerText = shareCount + ' de 5 compartilhamentos';

                if (shareCount >= 5) {
                    document.getElementById('link-container').style.display = 'block';
                }
            }

            // Cria a URL de compartilhamento do WhatsApp
            let message = "Eu preciso de sua ajuda para desbloquear esse conteúdo incrível! Clique aqui: https://go.tribopay.net/wamjb";
            let whatsappURL = "https://api.whatsapp.com/send?text=" + encodeURIComponent(message);

            // Atualiza o link do botão para redirecionar ao WhatsApp
            document.getElementById('share-btn').setAttribute('href', whatsappURL);
        });
    </script>
</body>
</html>
