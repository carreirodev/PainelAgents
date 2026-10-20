# agents-panel

Painel lateral do Claude Code (no terminal) que mostra todos os agentes da sessão: o principal e cada subagente, com modelo, esforço, cronômetro, tokens e a ferramenta que está usando agora. Mostra também os shells abertos em segundo plano (Bash e PowerShell), até terminarem.

O painel abre sozinho quando a janela do terminal tem 144 colunas ou mais; em qualquer largura, `/painel-agentes` abre o painel. Foi feito e testado com `"tui": "fullscreen"` em `~/.claude/settings.json`.

## Instalar num computador novo

O agents-panel se instala a partir do [WPC Mods for Claude](https://github.com/carreirodev/wpc-mods-claude/blob/main/README.pt-BR.md), o marketplace com todos os meus mods.

1. Numa sessão do Claude Code, digite:

   ```
   /plugin install agents-panel --marketplace carreirodev/wpc-mods-claude
   ```

2. Responda `y` para adicionar o marketplace e escolha o escopo de usuário (o primeiro da lista) com Enter. A mensagem `Installed agents-panel` confirma; o painel funciona a partir daí, em toda sessão nova.

Para receber uma versão nova depois: `/plugin marketplace update wpc-mods-claude` numa sessão.

Instalou antes pelo marketplace deste repositório (`agents-panel@agents-panel`)? Essa cópia continua atualizando como antes. Para trocar, siga [estes passos](https://github.com/carreirodev/wpc-mods-claude/blob/main/README.pt-BR.md#se-você-já-instalou-um-mod-pelo-repositório-dele); não fique com as duas, porque só uma roda.

## Editar o mod

Para mexer no mod, use a pasta clonada em vez da instalação acima (um jeito ou o outro, não os dois):

1. Clone o repositório nessa pasta:

   ```
   git clone https://github.com/carreirodev/mod-painel-agents.git C:\Users\SEU_USUARIO\mods\agents-panel
   ```

2. Em `~/.claude/settings.json`, no bloco `env`, aponte para essa pasta:

   ```json
   "env": {
     "CLAUDE_CODE_PLUGIN_DIRS": "C:\\Users\\SEU_USUARIO\\mods\\agents-panel"
   }
   ```

3. Abra uma sessão nova. Daí em diante, cada mudança salva na pasta recarrega o mod ao fim da resposta do Claude.

Antes de subir uma mudança, rode na pasta do mod:

```
claude plugin validate .
claude plugin test .
```

E aumente `version` em `.claude-plugin/plugin.json`: os computadores que instalaram pelo marketplace só recebem a mudança quando a versão muda.
