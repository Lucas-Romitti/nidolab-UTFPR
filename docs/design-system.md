# 🎨 Design System - Roubank

Neste projeto, utilizamos um framework UI e aplicamos customizações pontuais para refletir a identidade visual.

### 1. Framework Base

- **Framework escolhido:** Bootstrap 
- **Motivação:** Oferece componentes baseados no Material Design, permitindo uma prototipagem rápida e um visual corporativo, limpo e confiável.

### 2. Paleta de Cores (Customização)

As variáveis de cor do framework foram escolhidas para induzir o usuário ao erro ou alertá-lo (tarde demais) sobre as taxas:

- **Cor Primária (Atenção/Taxas):** `#D32F2F` _(Red darken-2)_
  - _Uso:_ Botões de confirmação de transações (saque, depósito), ícones de taxas no extrato e alertas. Representa o perigo constante para o bolso do cliente.
- **Cor Secundária (Base):** `#212121` _(Grey darken-4)_
  - _Uso:_ Barra de navegação (Navbar), rodapé e textos de destaque. Transmite frieza institucional.
- **Cor de Fundo (Background):** `#F5F5F5` _(Grey lighten-4)_
  - _Uso:_ Fundo de todas as páginas para destacar os painéis brancos flutuantes.
- **Cor de Sucesso:** `#388E3C` _(Green darken-2)_
  - _Uso:_ Extremamente restrito. Usado apenas em mensagens onde o _banco_ leva vantagem (ex: "Taxa cobrada com sucesso!").

### 3. Tipografia

Importada via Google Fonts para substituir a fonte padrão do navegador e dar um ar mais moderno:

- **Títulos (H1 a H6) e Destaques numéricos (Saldo):** `Roboto, sans-serif` (Peso: 700).
- **Textos Corridos, Inputs e Tabelas de Extrato:** `Open Sans, sans-serif` (Peso: 400).

### 4. Diretrizes de Uso de Componentes

Regras para a aplicação dos componentes do MaterializeCSS dentro da lógica predatória do Roubank:

- **Botões de Ação (`.btn`):** Ações que resultam em cobrança de taxas devem usar o modificador `.btn-large` e a cor primária (vermelho), para chamar atenção e induzir o clique. Ações de cancelamento ou fuga usam botões sem preenchimento (`.btn-flat`) para passarem despercebidos.
- **Cards (`.card`):** Usados obrigatoriamente para exibir o Saldo em destaque e encapsular as listagens do Extrato. Devem usar a sombra padrão (`z-depth-1`).
- **Formulários (`.input-field`):** Os inputs devem ser largos e burocráticos.

### 5. Componentes do Framework no Protótipo

Componentes desenhados no protótipo que serão substituídos pelos componentes prontos do MaterializeCSS:

| No protótipo | Componente do MaterializeCSS | Onde aparece |
| --- | --- | --- |
| Barra superior com o logo e os links | Navbar (`nav`, com `.sidenav` no celular) | Todas as páginas |
| Painel do saldo | Card (`.card`) | Painel principal |
| Janela "Tem certeza? Será cobrada uma taxa" | Modal (`.modal`) | Confirmação de saque e de depósito |

### 6. Dos Tokens ao Código

Como cada token do Design System vira código. As variáveis Sass do MaterializeCSS são definidas **antes** do `@import` do framework; o que não tem variável vira uma variável CSS própria:

| Token | Valor | No código |
| --- | --- | --- |
| Cor primária | `#D32F2F` | `$primary-color` (Sass do MaterializeCSS) |
| Cor secundária | `#212121` | `$secondary-color` (Sass do MaterializeCSS) |
| Cor de sucesso | `#388E3C` | `$success-color` (Sass do MaterializeCSS) |
| Cor de fundo | `#F5F5F5` | `--cor-fundo` (variável CSS própria, usada no `body`) |
| Fonte dos títulos | `Roboto`, 700 | `--fonte-titulos` (variável CSS própria) |
| Fonte do texto | `Open Sans`, 400 | `$font-stack` (Sass do MaterializeCSS) |