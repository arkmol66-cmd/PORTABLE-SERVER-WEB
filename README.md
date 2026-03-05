# 🌐 Portable Web Server

[![.NET](https://img.shields.io/badge/.NET-8.0-512BD4?logo=dotnet)](https://dotnet.microsoft.com/)
[![Windows](https://img.shields.io/badge/Windows-7%2B-0078D6?logo=windows)](https://www.microsoft.com/windows)
[![Android](https://img.shields.io/badge/Android-5.0%2B-3DDC84?logo=android)](https://www.android.com/)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

Servidor web portátil completo que funciona em pen-drive, Windows e Android. Hospede sites estáticos sem instalação, com suporte a HTTPS, DNS local, sincronização USB e chat em tempo real.
AVISO O APP ANDROID NÃO FOI LANÇADO

## ✨ Características

### 🖥️ Versão Windows (PC)
- ✅ **Servidor HTTP/HTTPS** com certificado SSL automático
- ✅ **DNS Local** para domínios customizados
- ✅ **Auto-start** com o Windows
- ✅ **Cache inteligente** de arquivos (HTML, CSS, JS, JSON)
- ✅ **Configuração de HOSTS** automática
- ✅ **Conexão USB** com Android via WiFi
- ✅ **Sistema de código** para pareamento seguro
- ✅ **Interface gráfica** moderna com logs em tempo real
- ✅ **Suporte a reCAPTCHA** v2 integrado
- ✅ **Chat com persistência** em JSON

### 📱 Versão Android
- ✅ **Servidor HTTP** embutido
- ✅ **Código de conexão** (3 letras + 3 números)
- ✅ **Recebimento via USB/WiFi** do PC
- ✅ **Armazenamento local** em `user_server_dados/`
- ✅ **Interface MAUI** moderna
- ✅ **Broadcast UDP** para descoberta automática
- ✅ **Suporte a POST** para chat e dados

### 💬 Sistema de Chat
- ✅ **Usuários sequenciais** (user_1, user_2, etc.)
- ✅ **Mensagens persistentes** em JSON
- ✅ **Registro de dispositivos** com verificação
- ✅ **Admin integrado** com credenciais padrão
- ✅ **Sincronização automática** entre PC e Android

## 🚀 Início Rápido

### Windows

#### Opção 1: Usar Executável Pronto
1. Baixe o executável da [última release](../../releases)
2. Copie `PortableWebServer.exe` para o pen-drive
3. Crie a pasta `pen-drive/` ao lado do executável
4. Execute como **Administrador**
5. Clique em "Iniciar Servidor"
6. Acesse `https://seudominio.local`

### Android

## 📁 Estrutura do Pen-Drive

```
pen-drive/
├── htmls_site/              # Arquivos HTML
│   ├── index.html
│   ├── chapter1.html
│   ├── chapter2.html
│   └── ...
├── css_site/                # Arquivos CSS
│   └── style.css
├── js_site/                 # Arquivos JavaScript
│   └── script.js
├── audio_site/              # Arquivos de áudio
│   └── intro_cap1.mp3
├── chat_data/               # Dados do chat (JSON)
│   ├── users.json
│   ├── messages.json
│   ├── register.json
│   └── check_device.json
├── config.site.config       # Configuração do site
├── config_home              # Configuração home
└── server.pfx               # Certificado SSL
```

## 🔗 Conectar Android ao Windows

### Método 1: Código de Conexão (Recomendado)

1. **No Android:**
   - Abra o app
   - Veja o código (ex: "ABC123")
   - Veja o IP exibido

2. **No Windows:**
   - Clique em "Conectar Android"
   - Digite o código do Android
   - Aguarde a conexão automática

3. **Transferência:**
   - Arquivos são enviados automaticamente
   - Progresso mostrado em tempo real
   - Chat data sincronizado

### Método 2: Broadcast Automático

1. Ambos na mesma rede WiFi
2. Android envia broadcast UDP (porta 8889)
3. Windows detecta automaticamente
4. Conexão estabelecida via código

## 🌐 Configuração de Domínio

### Domínio Público



### Credenciais Padrão

O sistema vem com um usuário admin pré-configurado. Altere as credenciais antes de usar em produção.

Veja a documentação interna para detalhes de configuração.

## 🔒 Segurança

### Conexão Android

- Código de 6 caracteres (3 letras + 3 números)
- Renovado a cada execução do app
- Timeout de 10 segundos para conexão
- Validação bidirecional

## 🛠️ Requisitos

### Windows
- Windows 7 SP1 ou superior
- .NET 8 Runtime (incluído no executável self-contained)
- Permissões de Administrador (para HTTPS e HOSTS)

### Android
- Android 5.0 (API 21) ou superior
- .NET 9 MAUI Runtime
- Permissões de rede e armazenamento

### Desenvolvimento
- .NET 8 SDK
- .NET 9 SDK (para Android)
- Visual Studio 2022 ou VS Code
- Android SDK (para compilar APK)

## 🐛 Troubleshooting

### Erro: "Porta 443 em uso"
O servidor usa fallback automático:
- HTTPS: 443 → 8443
- HTTP: 80 → 8080

### Erro: "Android não encontrado"
1. Verifique se estão na mesma rede WiFi
2. Desative VPN em ambos
3. Verifique firewall do Windows
4. Veja o IP no app Android e tente manualmente

### Erro: "Código incorreto"
1. Digite exatamente como aparece (case-sensitive)
2. Gere novo código reiniciando o app Android
3. Verifique logs em ambos os lados

### Erro: "Chat não salva"
1. Verifique permissões de escrita
2. Veja logs do servidor (POST requests)
3. Confirme que `chat_data/` existe
4. Teste com credenciais de admin configuradas


## 🎯 Casos de Uso

- 📚 **Educação:** Hospedar material didático offline
- 🎮 **Gaming:** Sites de jogos HTML5 portáteis
- 📖 **E-books:** Biblioteca digital interativa
- 💼 **Apresentações:** Slides e demos sem internet
- 🏢 **Corporativo:** Intranet portátil em pen-drive
- 🎨 **Portfolio:** Mostre seu trabalho offline
- 💬 **Chat Local:** Comunicação em rede local

## 🤝 Contribuindo

Contribuições são bem-vindas! Por favor:

1. Fork o projeto
2. Crie uma branch (`git checkout -b feature/nova-funcionalidade`)
3. Commit suas mudanças (`git commit -am 'Adiciona nova funcionalidade'`)
4. Push para a branch (`git push origin feature/nova-funcionalidade`)
5. Abra um Pull Request

## 📄 Licença

Este projeto está sob a licença MIT.
Este projeto está sob a licença net.

## 🙏 Agradecimentos

- [InTheHand.Net.Bluetooth](https://github.com/inthehand/32feet) - Biblioteca Bluetooth
- [.NET MAUI](https://dotnet.microsoft.com/apps/maui) - Framework Android

**Desenvolvido por one mapas apps office e kiro ia com amor para a comunidade open source**
