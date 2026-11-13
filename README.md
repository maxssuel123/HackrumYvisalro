# Vitrine Perto

Projeto mobile para descoberta e comparação de produtos e ofertas em lojas de um shopping, com mapa e trajetos demonstrativos.

## Documentação inicial

- [Especificação do projeto](docs/project/spec.md): escopo inicial, jornadas, requisitos e critérios de sucesso.
- [Insumos técnicos](docs/project/planning-input.md): Flutter/Dart com MVVM, API Node.js, Supabase/PostgreSQL e Supabase Auth.
- [Checklist de qualidade](docs/project/checklists/requirements.md): revisão documental dos requisitos iniciais.

Esses documentos descrevem a base do projeto inteiro. As jornadas e prioridades organizam o escopo inicial; não representam uma feature já aberta no Spec Kit.

## Organização

- `docs/project/`: documentação e planejamento geral do projeto.
- `.specify/`: configuração, templates e infraestrutura do Spec Kit.
- `.agents/skills/`: skills do Spec Kit disponíveis para o desenvolvimento.
- `specs/`: reservado para futuras funcionalidades delimitadas, quando forem especificadas; será criado quando necessário.

Não há funcionalidade ativa registrada em `.specify/feature.json`. Ao iniciar uma funcionalidade futura com `$speckit-specify`, usar a documentação inicial como contexto e criar sua especificação própria em `specs/`.

A constituição em `.specify/memory/constitution.md` ainda é um template e deverá ser definida antes de usar seus princípios como critérios de planejamento.
