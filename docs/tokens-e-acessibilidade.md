# Tokens Visuais, Layout e Acessibilidade — AcadFlow Design

Referência em Markdown dos tokens, padrões responsivos, diretrizes de acessibilidade e mensagens padronizadas definidos nos quadros `Icone`, `Fundamentos`, `Componentes`, `Sidebar`, `TemaEscuro` e `Feedback`.

---

## 1. Marca e Ícones (`icone/`)

- **Metáfora:** livro aberto com caneta âmbar escrevendo *Acad* sobre base azul tinta (`#2E43C8`), canto arredondado `116px` no canvas `512×512` (`22,6%`).
- **Variantes:** `cor` (padrão), `mono` (`#151826`), `claro` (`#EEF0FC` sobre fundos escuros ou azuis).
- **Regra de escala:** abaixo de `64 px` (`48`, `32` favicon, `16`), usar obrigatoriamente a versão simplificada (`acadflow-icone-simples.svg`, sem texto *Acad* nem linhas de página).

---

## 2. Paleta de Cores

### Tema Claro (`Fundamentos.dc.html`)

| Grupo | Token | Hex | Uso |
| --- | --- | --- | --- |
| **Primária (Tinta)** | `Tinta 800` | `#1C2A8C` | Pressionado |
| | `Tinta 700` | `#2436A8` | Hover, texto de item ativo no menu |
| | `Tinta 600` | `#2E43C8` | Botões primários, links, foco de input |
| | `Tinta 100` | `#DDE2FA` | Ring de foco de campo, tag `ALUNO` |
| | `Tinta 50` | `#EEF0FC` | Fundo de nav ativo, banners informativos |
| **Destaque (Âmbar)** | `Âmbar 400` | `#F2A93B` | Anel de foco de teclado, célula editada, barra Recuperação |
| | `Âmbar texto` | `#8A5300` | Texto de aviso / Recuperação (`#5C3800` em banner) |
| | `Âmbar 50` | `#FDF3E1` | Fundo de aviso / Recuperação / célula editada |
| **Neutros (Grafite)** | `Grafite 900` | `#151826` | Texto principal, badge `PROFESSOR` |
| | `Grafite 600` | `#5A6072` | Texto secundário |
| | `Grafite 400` | `#8A90A6` | Ícones e texto desabilitado |
| | `Grafite 200` | `#E4E6EE` | Bordas de cards e seções (campo `#C9CDDA`, cabeçalho `#F9FAFC`, linha `#F0F1F5`) |
| | `Grafite 100` | `#F5F6FA` | Fundo da aplicação |
| | `Branco` | `#FFFFFF` | Superfície de cards, modais e sidebar |
| **Semânticas** | `Sucesso` / `Sucesso 50` | `#1C7A4A` / `#E6F4EC` | Aprovado |
| | `Erro` / `Erro 50` | `#C0322A` / `#FCE9E7` | Reprovado e validações (`#A02720` hover, `#8F241E` texto alerta) |

### Tema Escuro (`TemaEscuro.dc.html` — Pós-MVP)

| Papel | Hex |
| --- | --- |
| Fundo (`canvas`) / Superfície (`surface`) | `#10131C` / `#1A1F2E` |
| Borda (`line`) / Borda de campo (`field`) | `#2D3447` / `#454D66` |
| Texto principal / Texto secundário | `#ECEEF6` / `#A3A9BD` |
| Primária / Primária suave / Link | `#4A5FE0` / `#232B55` / `#A9B6FF` |
| Sucesso / Fundo Sucesso | `#5FD39A` / `#163528` |
| Recuperação / Fundo Recuperação | `#F5C36B` / `#40300F` |
| Erro / Fundo Erro / Botão perigo | `#FF8F87` / `#43201F` / `#C0322A` |

---

## 3. Tipografia, Espaçamento, Raios e Layout

- **Famílias:** `Space Grotesk` (`500`, `600`, `700`) para títulos; `Inter` (`400`, `500`, `600`, `700`) para interface/corpo; `Caveat` (`700`) apenas no ícone; `ui-monospace` para códigos/rotas.
- **Escala tipográfica:** Landing H1 `56px` · Display `48/56` (`700`) · H1 `32/40` (`700`) · H2 `24/32` (`600`) · H3 `18/26` (`600`) · Body `16/24` (`400`) · Small `14/20` · Label `12/16` (`600`, uppercase, `letter-spacing: 0.08em`).
- **Espaçamento (base `4px`):** `4`, `8`, `12`, `16`, `24`, `32`, `48`, `64`.
- **Raios:** `6px` (campos e badges de papel) · `10px` (botões e itens de menu) · `14px`–`16px` (cards e modais) · `999px` (pílulas e avatares).
- **Elevação:** Shadow 1 `0 1px 2px rgba(21,24,38,0.06), 0 1px 3px rgba(21,24,38,0.08)` · Shadow 2 `0 12px 32px rgba(21,24,38,0.16)` (diálogos até `0 24px 64px rgba(21,24,38,0.28)`).
- **Layout:** barra lateral esquerda de `248px` + conteúdo fluido (`max-width: 1200px`, `padding: 32px 40px 48px`). Abaixo de `820px`, a barra lateral converte-se em barra superior.

---

## 4. Acessibilidade e Estados

- **Alvos de toque:** altura mínima de `44px` em botões, inputs e itens de navegação (`48px` nos CTAs de autenticação/erro).
- **Foco de teclado:** anel âmbar `box-shadow: 0 0 0 2px #FFFFFF, 0 0 0 4px #F2A93B` (mantido em ambos os temas).
- **Independência de cor:** badges acadêmicos sempre exibem **ícone + texto** (`✓ Aprovado`, `! Recuperação`, `× Reprovado`, `Sem notas`).
- **Estados obrigatórios:** skeleton shimmer (`> 300ms`), vazio com CTA, erro com `retry`, botão `loading` com `aria-busy="true"` bloqueando duplo clique, toasts com `5s` e `role="status"`/`role="alert"`.

---

## 5. Mensagens Padrão de Validação (`pt-BR`)

| Cenário | Mensagem especificada |
| --- | --- |
| Login inválido | `E-mail ou senha incorretos.` |
| Nota fora de `0,0–10,0` | `A nota deve estar entre 0,0 e 10,0.` |
| Mais de 1 casa decimal | `Use no máximo uma casa decimal.` |
| Disciplina duplicada | `Já existe BD-204 no semestre 2026.2.` |
| E-mail duplicado | `Já existe uma conta com este e-mail.` |
| Título de atividade vazio | `Informe o título da atividade.` |
| Prazo no passado | `Escolha uma data a partir de hoje.` |
| Senha curta / divergente | `Use pelo menos 8 caracteres.` / `As senhas não são iguais.` |
| Anexo inválido | `Escolha um PDF, PNG ou JPG de até 10 MB.` |
| Avatar inválido / storage indisponível | `Escolha uma imagem PNG, JPG ou WebP de até 2 MB.` / `O envio de arquivos está indisponível.` |

