# Changelog

Todas as mudanças notáveis de **AcadFlow Design** são documentadas neste arquivo, seguindo o padrão [Keep a Changelog](https://keepachangelog.com/pt-BR/1.1.0/).

## [Unreleased]

### Adicionado
- Documentação em Markdown de tokens visuais e acessibilidade ([docs/tokens-e-acessibilidade.md](docs/tokens-e-acessibilidade.md)) e matriz de rastreabilidade Design × Web × API ([docs/rastreabilidade.md](docs/rastreabilidade.md)).
- Governança: `CHANGELOG.md`, `SECURITY.md` e `LICENSE` (MIT).

## [1.3.0] - 2026-11-24

### Adicionado
- Protótipos pós-MVP (`ACA-30`): `ProfAlunos` (matrícula/remoção com bloqueio se houver notas), `AtividadeAnexos` (materiais de apoio até 10 MB), `PerfilFoto` (upload/remoção até 2 MB) e `TemaEscuro`.

### Alterado
- Regra vigente documentada no `README.md`: atividade com notas ou anexos não pode ser excluída (alinhamento ao contrato da API).

## [1.2.0] - 2026-11-23

### Adicionado
- `Landing` (home pública antes do login), `ProfHome` e `AlunoHome` (telas iniciais após o login).

### Alterado
- `ProfPainel` e `AlunoPainel` passaram a ser nomeados como **Visão geral** no menu lateral.

## [1.1.0] - 2026-11-23

### Adicionado
- `EscopoMVP`, `ModeloDados` (5 tabelas principais), `Avisos` (sino derivado), `Perfil` e catálogo de validação em `Feedback`.

### Alterado
- Alinhamento ao MVP: cadastro público restrito a `ALUNO` (pós-MVP), atividades visíveis imediatamente sem rascunho, disciplinas com `code` + `semester` únicos, média parcial arredondada uma única vez e notas com `PUT` idempotente.

## [1.0.0] - 2026-11-23

### Adicionado
- Identidade visual, ícones (`SVG` e `PNG`), tokens *Tinta* / *Âmbar* / *Grafite*, componentes base, fluxos de navegação e telas iniciais de Professor, Aluno e Erros.

