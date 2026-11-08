# CTI Intelligence — MVP PWA (demonstração)

Aplicativo web progressivo **local-first**, com dados totalmente fictícios, para validação de interface e fluxos de trabalho no iPhone.

## Instalação no iPhone

1. Publique **todo o conteúdo desta pasta** em hospedagem HTTPS de arquivos estáticos (por exemplo, GitHub Pages, Cloudflare Pages ou Netlify). Não basta abrir o arquivo `index.html` diretamente no iPhone: instalação e service worker exigem origem HTTPS ou ambiente local apropriado.
2. No Safari do iPhone, abra o endereço HTTPS publicado.
3. Toque em **Compartilhar → Adicionar à Tela de Início** e confirme.
4. Abra pelo ícone CTI Intelligence. Após a primeira visita e armazenamento do cache, os arquivos do aplicativo podem funcionar offline, respeitadas as limitações do navegador.

## Funcionalidades implementadas

- Cartões individuais dos leitos 11–20, filtro e etiquetas visuais para via aérea e modo ventilatório.
- Seis seções na ordem aprovada: Infusões, Ventilação mecânica, Monitorização, Gasometria, Conduta, Intercorrências.
- Edição de campos (demais campos via diálogo; conduta diretamente no cartão); histórico de alterações no backup JSON.
- Gasometrias com horários e parâmetros, preservadas como lista; edição via JSON.
- Exportação da seleção visível para WhatsApp via área de transferência.
- Analytics descritivo, com indicadores de cobertura e distribuição ventilatória.
- Evidence: contextualização do leito e perguntas para discussão, **sem busca científica ou recomendação de conduta automatizada**.
- Persistência via `localStorage`, exportação e importação de backup demonstrativo, instalação PWA e cache offline.

## Limites do MVP

- Não contém captura de imagem nem leitura automática de fotos.
- Não contém integração com Claude/API, pesquisa PubMed, backend, login, sincronização, notificações, ou auditoria imutável.
- Os indicadores são descritivos; o campo livre de intercorrências não equivale a eventos estruturados com denominadores clínicos.
- Armazenamento local pode ser apagado pelo sistema ou usuário. Exportar backups regularmente.
- **Não utilizar com dados reais identificáveis de pacientes ou como prontuário.** Uma implantação assistencial requer análise de LGPD, governança institucional, controle de acesso, armazenamento seguro, trilhas de auditoria, validação clínica e plano de contingência.

## Referências do projeto anterior

A pasta `referencias-projeto/` contém os arquivos originais do projeto Claude/Skills fornecidos anteriormente, preservados como referência de arquitetura. A Skill Plantão original instalada no Claude não foi modificada.

## Desenvolvimento local

`python3 -m http.server 8080` dentro desta pasta e acesse `http://localhost:8080` no computador. Para instalar no iPhone, publique em HTTPS.
