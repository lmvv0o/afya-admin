# Verificação da atividade

Data: 5 de outubro de 2026. SDK 10.0.112, pacotes Blazor 10.0.12 e MudBlazor 9.11.0.

## Compilação e execução

- Compilação final: **zero erros e zero avisos**.
- `dotnet watch`: aplicação iniciou em `http://localhost:5147`; Hot Reload foi observado ao salvar alterações Razor.
- No ambiente de execução, foi usado `DOTNET_USE_POLLING_FILE_WATCHER=1` após atingir o limite de inotify.
- Dashboard na rota `/` e página NotFound em `/pagina-inexistente` verificados no navegador.
- Console consultado após renderização e navegação: nenhuma mensagem de erro ou aviso capturada.
- Restauração e compilação de um clone separado: verificação em andamento.

## Interações verificadas

| Verificação | Resultado |
|---|---|
| Seletor de período | Escolher 7 dias alterou o rótulo; retorno para 30 dias funcionou. |
| Notificações | Menu abriu e mostrou as três notificações fictícias. |
| Usuário | Menu abriu com Perfil, Configurações e Sair. |
| Opções dos cards | Menu de Receita abriu com Exportar dados e Ver relatório completo. |
| Ações da tabela | Menu do Portal Institucional abriu com Ver detalhes, Editar e Excluir. |
| Sidebar mobile | Gaveta abriu sobre o conteúdo e fechou. |
| Tema | Alternância claro/escuro funcionou; texto central da rosca ficou legível. |
| Gráficos | Quatro sparklines, duas séries mensais e rosca foram renderizados. |
| Dados | KPIs, 1.842 clientes, quatro projetos de performance, quatro atividades e quatro linhas de tabela conferidos. |
| Legenda | Segmentos de clientes totalizam 100%. |

Busca, Novo Projeto, exportação, cadastro e edição são apenas demonstrativos, conforme o escopo obrigatório.

## Responsividade

| Largura solicitada | KPIs por linha |
|---:|---:|
| 390px | 1 |
| 599px | 1 |
| 600px | 2 |
| 768px | 2 |
| 1279px | 2 |
| 1280px | 4 |
| 1440px | 4 |

- Em 390px, busca e identificação textual do usuário ficam ocultas; avatar e botões permanecem visíveis.
- Tabela mobile mostra rótulos gerados a partir de `DataLabel`, com cabeçalho tradicional oculto.
- Não foi encontrada rolagem horizontal da página nas larguras testadas.
- Sidebar: conteúdo e área disponível têm a mesma largura de 280px após corrigir margens dos divisores.
- Receita reserva espaço inferior para os meses; performance distribui as linhas pela altura disponível.
- A legenda da rosca recebe mais espaço em `lg`, mantendo a proporção 8/4 do tutorial em `sm`.

## Código e Git

- Nove componentes Razor em `Components`; modelos e dados em `Data`.
- Sem arquivos `.razor.css`, blocos `<style>`, parâmetros `Style` ou atributos `style` escritos nos componentes.
- `wwwroot/css/app.css` é o arquivo original do template, sem modificações.
- MudBlazor pode gerar estilos inline no HTML; isso é saída dos componentes, documentada na inspeção do card.
- `git check-ignore` confirmou que a DLL em `bin/` e `obj/project.assets.json` estão ignorados.
- `git ls-files bin obj` não retornou arquivos versionados.
- Commits foram feitos durante cada etapa, com verificações de compilação.

## Evidências e pendências

- Prints reais da página: `tema-claro.png`, `tema-escuro.png` e `mobile.png`.
- Fragmento HTML realmente obtido do DOM: `docs/html-dashboard-card.html`.
- **Falta capturar o print da interface Elements do DevTools** e salvar como `docs/prints/devtools.png`. A interface DevTools não é exposta pelo navegador integrado; o fragmento HTML não substitui o print exigido.
- O aluno deve revisar e reescrever as respostas de aprendizado com suas palavras. O README identifica que o desenvolvimento e as explicações foram assistidos.
- Confirmar com o professor o peso não informado do último critério e o horário de entrega, caso haja.
