# css3-e-html5 projeto fictício para desenvolvimento real
🌿 VSM Visionária – Soluções Sustentáveis para Cidades InteligentesSomos uma empresa especializada em soluções de urbanismo ecológico e acessível. Desenvolvemos, fabricamos e implantamos **calçadas inteligentes, drenantes e sustentáveis**, substituindo o concreto por **materiais recicláveis, biotecnológicos e esteticamente inovadores**.

Nosso compromisso é transformar a paisagem urbana em um espaço mais bonito, acessível, seguro e preparado para o futuro climático.

✔️ 100% conformidade com as normas de acessibilidade  
✔️ Redução comprovada de enchentes urbanas  
✔️ Produtos com ciclo de vida ecológico e reaproveitamento  
✔️ Alinhados à Agenda 2030 (ODS 11 – Cidades Sustentáveis)
(Slogan: Inovando o presente. Moldando o futuro urbano.)🌿 Sem uso de cimento: 100% materiais alternativos  
♿ Acessibilidade universal com estética refinada  
💧 Calçadas drenantes que combatem enchentes  
📱 Soluções inteligentes com sensores, LED e QR Codes  
🎨 Design personalizado com mosaicos e cores naturais  
🚛 Baixa manutenção e logística eficiente  
🔒 Garantia técnica e plano de manutenção incluídos🏛️ B2G – Obras públicas e licitações: calçadas ecológicas para prefeituras.  
🏢 B2B – Parcerias com construtoras, loteadoras e escritórios de arquitetura.  
🏡 B2C – Instalações residenciais e comerciais sob medida.Nossa equipe multidisciplinar é formada por:

👷‍♂️ Engenheiros civis e de materiais  
🧪 Especialistas em sustentabilidade e drenagem urbana  
♿ Consultores em acessibilidade  
🏞️ Arquitetos urbanistas e paisagistas  
🧱 Técnicos em fabricação, obra e controle de qualidade

Contamos com uma **fábrica matriz equipada** com processos limpos, tecnologia de ponta e capacidade de produção de até **20.000 m²/mês de calçadas ecológicas**.- Conformidade com NBR 9050 (Acessibilidade)
- NBR 16416 (Calçadas e Mobilidade)
- ISO 14001 – Gestão Ambiental
- Licenciamento ambiental vigente
- Selo Verde de Produção Sustentável🏢 MATRIZ: Rua Olimpíadas universitárias , 360000 – Vila Americana Olímpia, São Alegrete –  CEP 04956-010  
📞 Telefone: (11) 9 9999-9999  
📧 E-mail: contato@vsmvisionaria.com.br  
🌐 Site: www.vsmvisionaria.com.br  
📱 Redes sociais: @vsmvisionaria

🗓️ Atendimento: Segunda a Sexta, das 8h às 18h🌱 Quer transformar sua rua, bairro ou cidade com inovação e respeito ao meio ambiente?

Solicite uma apresentação técnica ou agende uma visita com nossa equipe especializada.  
Juntos, vamos **redefinir o caminho das cidades para um futuro mais verde, acessível e inteligente.**<!DOCTYPE html><html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Assistente VSM Visionária</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>
  <header>
    <h1>Atendimento Virtual VSM</h1>
    <p>Sua assistente inteligente com voz e IA</p>
  </header>  <main>
    <section>
      <div style="display: flex; align-items: center; gap: 1rem;">
        <img id="avatar" src="avatar.png" alt="Avatar Feminina" width="140" style="border-radius: 10px;">
        <div>
          <p id="mensagem-ia">Olá! Como posso ajudar você hoje?</p>
          <button onclick="ativarMicrofone()">🎙️ Fale comigo</button>
        </div>
      </div>
      <br>
      <label for="entrada">Ou digite sua pergunta:</label>
      <input type="text" id="entrada" placeholder="Ex: Como funciona nosso sistema?" onkeydown="if(event.key==='Enter'){enviarPergunta()}">
      <button onclick="enviarPergunta()">Enviar</button>
    </section>
  </main>  <script>
    const reconhecimento = new (window.SpeechRecognition || window.webkitSpeechRecognition)();
    reconhecimento.lang = 'pt-BR';
    reconhecimento.onresult = function(event) {
      const texto = event.results[0][0].transcript;
      document.getElementById("entrada").value = texto;
      enviarPergunta();
    };

    function ativarMicrofone() {
      reconhecimento.start();
    }

    function falar(texto) {
      const sintese = window.speechSynthesis;
      const fala = new SpeechSynthesisUtterance(texto);
      fala.lang = 'pt-BR';
      fala.pitch = 1;
      fala.rate = 1;
      fala.voice = sintese.getVoices().find(v => v.lang === 'pt-BR' && v.name.includes("Luciana")) || null;
      sintese.speak(fala);
    }

    async function enviarPergunta() {
      const pergunta = document.getElementById("entrada").value;
      if (!pergunta) return;

      document.getElementById("mensagem-ia").textContent = "Pensando...";

      const resposta = await fetch("https://api.openai.com/v1/chat/completions", {
        method: "POST",
        headers: {
          "Content-Type": "application/json",
          "Authorization": "Bearer SUA_CHAVE_OPENAI"
        },
        body: JSON.stringify({
          model: "gpt-3.5-turbo",
          messages: [{ role: "user", content: pergunta }]
        })
      });

      const dados = await resposta.json();
      const texto = dados.choices[0].message.content;

      document.getElementById("mensagem-ia").textContent = texto;
      falar(texto);
    }
  </script></body>
</html>

um projeto com dados fictício 