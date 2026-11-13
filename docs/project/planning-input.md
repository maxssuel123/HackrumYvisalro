# Insumos para planejamento

Restrições solicitadas pelo usuário em 2026-11-12; não constituem um plano de implementação.

- Aplicativo mobile em Flutter/Dart, com arquitetura MVVM.
- API backend em Node.js, consumida pelo aplicativo Flutter. A API será responsável pelos dados de negócio, validação, autorização e isolamento por usuário; não será substituída por acesso direto do app às tabelas de negócio.
- Supabase com PostgreSQL e Supabase Auth confirmados pelo usuário. Autenticação funcional por e-mail/senha, Google e Apple; recuperação de senha por e-mail real.
- O app integra os fluxos de identidade com Supabase Auth e apresenta sua credencial de sessão à API Node.js, que deve validá-la antes de autorizar recursos pessoais. Definir contratos e tratamento de renovação, expiração e logout no planejamento.
- Preferências, desejos e inscrições de reposição persistem por conta. Busca, comparação, mapa e descoberta têm acesso público; recursos pessoais exigem autenticação.
- Vercel como hospedagem solicitada: planejar uso para as duas landing pages e eventual demonstração web, separando distribuição mobile.
- Elaborar contratos de API e mocks coerentes para catálogo, ofertas, comparação, promoções, perfil funcional, desejos, reposição, mapa e trajetos, documentando operações públicas/protegidas, erros e identidade do usuário.
- Mocks apoiam desenvolvimento e testes, mas não substituem login real, recuperação real ou persistência na entrega final. Dados comerciais e percurso permanecem fictícios.
- “mapa pk” pode se referir a Mapbox; fornecedor não confirmado. Avaliar compatibilidade com mapa indoor 3D e Flutter no planejamento.
- Entregar prototipagens navegáveis das telas e duas landing pages distintas.
- Estoque real, localização indoor real e envio externo de alertas/campanhas permanecem fora da entrega inicial. Autenticação e recuperação deixam de ser escopo futuro.
- Planejar configuração de Supabase, envio de e-mail, aplicações Google/Apple, URLs de retorno e retorno ao app mobile; segredos e credenciais administrativas ficam fora do aplicativo e do repositório.
- Definir hospedagem da API Node.js no planejamento; Vercel continua solicitada, sem presumir que a distribuição mobile ou todos os serviços serão hospedados nela.
