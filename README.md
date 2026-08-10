# Raio-X do seu Evento Cristão

Quiz interativo, em uma única página HTML, que gera um diagnóstico personalizado sobre a maturidade organizacional de eventos cristãos (congressos, retiros, cultos especiais, etc). O usuário responde 22 perguntas objetivas divididas em 8 eixos, informa seus dados de contato e recebe um relatório completo com perfil geral, plano de ação e um "mini raio-x" para cada eixo avaliado.

🔗 **Demo:** abra o arquivo `index.html` em qualquer navegador, ou publique com GitHub Pages (veja abaixo).

## ✨ Funcionalidades

- Fluxo guiado por telas (intro → perguntas → captura de lead → resultado), com barra de progresso.
- 22 perguntas: 2 de abertura, 18 pontuadas distribuídas em 8 eixos, 1 de fechamento aberta e 1 de qualificação.
- Pontuação por eixo (Crítico / Em Desenvolvimento / Maduro) calculada no cliente, sem backend.
- Motor de perfis: 6 perfis específicos + 2 perfis de fallback, escolhidos por regras combinando os níveis dos eixos.
- Tela de resultado com plano de ação prioritário e "mini raio-x" expansível por eixo (sintomas + plano de ação detalhado).
- Captura de lead (nome, e-mail, WhatsApp) com validação antes de liberar o resultado.
- 100% front-end: HTML, CSS e JavaScript puro em um único arquivo, sem dependências além das fontes do Google Fonts.
- Responsivo, com ajustes de layout para telas pequenas.

## 🗂 Estrutura do projeto

```
raiox-evento-cristao/
├── index.html      # Aplicação completa (markup + estilos + lógica)
├── README.md        # Este arquivo
└── LICENSE           # Licença MIT
```

## 🚀 Como usar

### Localmente

1. Clone o repositório:
   ```bash
   git clone https://github.com/SEU_USUARIO/raiox-evento-cristao.git
   cd raiox-evento-cristao
   ```
2. Abra o `index.html` diretamente no navegador, ou sirva com um servidor local simples:
   ```bash
   python3 -m http.server 8000
   # depois acesse http://localhost:8000
   ```

### Publicando com GitHub Pages

1. Faça o push do repositório para o GitHub.
2. Vá em **Settings → Pages**.
3. Em "Build and deployment", selecione a branch `main` (ou `master`) e a pasta `/root`.
4. Salve. Em alguns minutos o quiz estará disponível em `https://SEU_USUARIO.github.io/raiox-evento-cristao/`.

## 🛠 Personalização

Todo o conteúdo (perguntas, textos dos eixos, perfis e planos de ação) está centralizado em duas constantes JavaScript no início do segundo `<script>` do `index.html`:

- `QUESTIONS` — lista das 22 perguntas, com tipo (`choice`/`text`), eixo associado e opções.
- `AXES` — nomes dos 8 eixos avaliados.
- `AXIS_DIAGNOSIS` — diagnóstico (headline, sintomas e plano de ação) para cada eixo em cada um dos 3 níveis.
- `PROFILES` — os 6 perfis gerais e suas regras de correspondência (`matches`).
- `FALLBACK_PROFILE_BUILDER` — perfil aplicado quando nenhuma regra específica é atendida.

Não é necessário nenhum build step: basta editar essas constantes e recarregar a página.

> ⚠️ **Nota sobre captura de dados:** este projeto captura nome, e-mail e WhatsApp apenas na memória do navegador (não há envio para nenhum backend/API). Se for usar em produção para capturar leads de verdade, será necessário integrar com um serviço de formulário, planilha ou CRM de sua escolha.

## 📄 Licença

Distribuído sob a licença MIT. Veja o arquivo [LICENSE](LICENSE) para mais detalhes.
