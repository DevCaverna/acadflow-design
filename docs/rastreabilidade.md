# Matriz de Rastreabilidade e Notas de Alinhamento — AcadFlow Design

Este documento relaciona as páginas e pranchas deste repositório com sua implementação em [acadflow-web](https://github.com/DevCaverna/acadflow-web) e [acadflow-api](https://github.com/DevCaverna/acadflow-api), além de registrar pendências de alinhamento identificadas nos quadros `.dc.html`.

---

## 1. Mapa de Páginas × Web × API

| Página (`telas/`) | Quadros principais | Implementação no `acadflow-web` (`develop`) | Suporte na `acadflow-api` |
| --- | --- | --- | --- |
| `01-capa-icone-escopo` | `Main`, `Icone`, `LogoMark`, `EscopoMVP` | `public/icons/*` (SVG e ícones base) | — |
| `02-fundamentos-componentes` | `Fundamentos`, `Componentes`, `Sidebar`, `Avisos`, `TemaEscuro` | `src/styles/index.css`, `src/shared/components/*`, `AppLayout`, `NotificationBell` | Reutiliza endpoints de disciplinas/atividades/notas |
| `03-fluxos-e-dados` | `FluxoAuth`, `FluxoProfessor`, `FluxoAluno`, `ModeloDados` | Rotas protegidas e hooks TanStack Query | Migrations PostgreSQL 17 + serviços de domínio |
| `04-home-publica-e-autenticacao` | `Landing`, `Login`, `LoginCarregando`, `LoginErro`, `Cadastro` | `/login` (`LoginPage`); `Landing` e `Cadastro` não implementados no app atual | `POST /auth/login`, `GET /auth/me` (`POST /auth/register` pós-MVP) |
| `05-professor` | `ProfHome`, `ProfPainel`, `ProfDisciplinas`, `ProfAtividades`, `ProfNovaAtividade`, `ProfNotas`, `ProfAlunos`, `AtividadeAnexos` | `/disciplines`, `/disciplines/:disciplineId`, `/grades` (`ProfHome` e `ProfPainel` unificados em `/disciplines`) | `develop/main` (MVP), `ACA-24` (`ProfAlunos`), `ACA-25` (`AtividadeAnexos`) |
| `06-aluno` | `AlunoHome`, `AlunoPainel`, `AlunoNotas`, `Perfil`, `PerfilFoto` | `/disciplines`, `/disciplines/:disciplineId`, `/grades`, `/profile` (`AlunoHome` e `AlunoPainel` unificados em `/disciplines`) | `develop/main` (MVP), `ACA-24` (`Perfil`), `ACA-25` (`PerfilFoto`) |
| `07-erros-e-feedback` | `Erro404`, `Erro403`, `Erro500`, `SemConexao`, `SessaoExpirada`, `Feedback` | `NotFoundPage` (`*`), `SessionExpiredDialog` (`401`), `QueryState`, `Alert`, `ConfirmDialog`, `Toaster` | `ApiExceptionFilter` (`{ statusCode, code, message }`) |

---

## 2. Inconsistências e Pendências nos Quadros `.dc.html`

Estes itens foram preservados nos arquivos originais de canvas e devem ser considerados como referência de revisão em futuras versões do design:

1. **Modal de exclusão de atividade em `Feedback.dc.html`:** o quadro ainda exibe um diálogo de confirmação em cascata (*"as 18 notas lançadas serão removidas juntas"*), herdado da v1.1. Conforme registrado no `README.md` (v1.3), **a regra vigente é o bloqueio (`409 CONFLICT`)**: atividade com notas ou anexos não é excluída (`ON DELETE RESTRICT` na API).
2. **Placeholder em `Landing.dc.html`:** o rodapé contém o texto literal `[CONTATO DA EQUIPE]`.
3. **Rótulo de versão na capa (`Main.dc.html`):** ainda exibe `Design de produto · v1.0` apesar de o repositório estar na v1.3.
4. **Exemplos de rotas nos rodapés de erro (`ProfPainel.dc.html` e `AlunoPainel.dc.html`):** exibem caminhos em português (`/professor/painel`, `/aluno/painel`), enquanto o contrato REST oficial e `EscopoMVP.dc.html` usam rotas em inglês (`/disciplines`, `/auth/me`).
5. **Fluxogramas e sino pré-v1.2:** `FluxoProfessor.dc.html`, `FluxoAluno.dc.html` e `Erro404.dc.html` ainda apontam para `ProfPainel`/`AlunoPainel` como destino inicial em vez de `ProfHome`/`AlunoHome`, e o sino de avisos aparece em `ProfPainel`/`AlunoPainel`, mas não em `ProfHome`/`AlunoHome`.
6. **Sincronia manual entre `design-files/` e `telas/`:** ambos os diretórios armazenam cópias idênticas dos 43 arquivos `.dc.html`; alterações futuras no canvas devem atualizar as duas pastas em conjunto.

