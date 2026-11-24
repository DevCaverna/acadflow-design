# Gerência de Configuração de Software (GCS) — AcadFlow Design

Este documento define como os ativos visuais e especificações de produto de **AcadFlow Design** são identificados, versionados e auditados como linha de base para [acadflow-web](https://github.com/DevCaverna/acadflow-web) e [acadflow-api](https://github.com/DevCaverna/acadflow-api).

---

## 1. Catálogo de Itens de Configuração (ICs)

| ID | Item de Configuração | Localização | Versionamento | Responsável |
| --- | --- | --- | --- | --- |
| `IC-DES-01` | Fontes das telas do Claude Design Canvas | `design-files/*.dc.html` | Git SHA + Release visual (`v1.0`..`v1.3`) | `@aqu1no1` |
| `IC-DES-02` | Manifesto de páginas, posições e notas | `design-files/canvas.json` | Git SHA (versão `3` do canvas) | `@aqu1no1` |
| `IC-DES-03` | Cópias de consulta por página | `telas/01-*` .. `telas/07-*` | Git SHA (espelho exato de `design-files/`) | `@aqu1no1` |
| `IC-DES-04` | Ícones e marca exportados | `icone/` (`SVG` e `PNG` `16`..`1024`) | Git SHA | `@aqu1no1` |
| `IC-DES-05` | Documentação de tokens e rastreabilidade | `README.md`, `docs/`, `CHANGELOG.md` | Git SHA + revisão em PR | `@Vinicius-Antonio` / `@OtavioGonzaga` |

---

## 2. Linhas de Base (Baselines) de Design

| Versão | Marco | Conteúdo congelado |
| --- | --- | --- |
| `v1.0` | Identidade e fluxos iniciais | Ícones, paleta, componentes e telas iniciais de Professor, Aluno e Erros |
| `v1.1` | Alinhamento ao MVP | `EscopoMVP`, `ModeloDados` (5 tabelas), `Avisos`, `Perfil` e catálogo de validação |
| `v1.2` | Navegação ampliada | `Landing`, `ProfHome`, `AlunoHome` e renomeação para Visão geral |
| `v1.3` | Protótipos pós-MVP (`ACA-30`) | `ProfAlunos`, `AtividadeAnexos`, `PerfilFoto`, `TemaEscuro` e regra `409` na exclusão de atividades |

---

## 3. Controle de Mudanças e Auditorias (FCA / PCA)

### Fluxo de Mudança
1. Toda alteração visual ou de regra de tela parte de uma issue `ACA-*` em branch dedicada a partir de `main`.
2. Mudanças que afetam tokens, campos ou fluxos devem documentar o impacto em Web/API no `.github/PULL_REQUEST_TEMPLATE.md` e em [rastreabilidade.md](rastreabilidade.md).
3. Revisão obrigatória por `.github/CODEOWNERS` antes do merge em `main`.

### Checklist de Auditoria Funcional e Física (FCA / PCA)
- [ ] **Sincronia física:** os arquivos em `design-files/*.dc.html` e `telas/**` permanecem idênticos após alterações no canvas.
- [ ] **Regra de negócio:** limites de média (`>= 7,0` Aprovado, `5,0–6,9` Recuperação, `< 5,0` Reprovado) e textos em `pt-BR` preservados.
- [ ] **Tokens e ícones:** escala simplificada abaixo de `64 px` (`acadflow-icone-simples.svg`) e contraste acessível respeitados.
- [ ] **Histórico:** versão e alterações registradas em [CHANGELOG.md](../CHANGELOG.md) e [README.md](../README.md).

