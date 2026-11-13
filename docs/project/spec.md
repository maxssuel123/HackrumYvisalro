# Especificação inicial do projeto: Vitrine Perto

**Escopo**: Projeto completo — base inicial de requisitos do produto, não uma funcionalidade isolada.
**Created**: 2026-11-12
**Status**: Especificação inicial — base para planejamento do projeto
**Input**: Aplicativo mobile com busca contextual, comparação de produtos, mapa 3D e trajetos indoor, promoções em stories/cards, desejos, login funcional e duas landing pages, com nomes fictícios.

## Jornadas de uso e critérios de aceitação

### User Story 1 - Buscar e comparar produtos (Priority: P1)

Como visitante, quero encontrar produtos pelo nome ou necessidade e comparar preços entre lojas sem precisar entrar em uma conta.

**Why this priority**: Encontrar a melhor oferta é o valor central do produto.
**Independent Test**: Buscar um item em catálogo fictício, filtrar categoria e preço e comparar duas lojas.

**Acceptance Scenarios**:

1. **Given** produtos associados a necessidades e sinônimos, **When** pesquiso por texto contextual, **Then** vejo produtos pertinentes, filtros ativos e opção de limpar a busca.
2. **Given** ofertas em várias lojas, **When** aplico categoria e faixa de preço, **Then** os resultados respeitam ambos os filtros e aparecem por disponibilidade e menor preço atual; em empate, promoções vigentes vêm primeiro, seguidas por nome do produto e da loja.
3. **Given** o mesmo produto e variante em duas lojas, **When** abro a comparação, **Then** vejo preços, condições, disponibilidade e pequena logo/nome de cada loja abaixo do item.
4. **Given** itens semelhantes e itens indisponíveis, **When** vejo os resultados, **Then** semelhantes são identificados separadamente do mesmo produto e indisponíveis aparecem por último, com opção de aviso de reposição.

### User Story 2 - Localizar a loja e visualizar o trajeto (Priority: P1)

Como visitante, quero descobrir lojas no mapa do shopping e seguir um percurso demonstrativo até a loja escolhida.

**Why this priority**: Liga a descoberta de ofertas à visita à loja.
**Independent Test**: Selecionar origem simulada e destino, visualizar caminho entre andares, iniciar e cancelar o trajeto.

**Acceptance Scenarios**:

1. **Given** o mapa 3D, **When** afasto a visualização, **Then** vejo sacolas nos pontos das lojas; ao aproximar, vejo logos e nomes acessíveis.
2. **Given** uma oferta ou loja selecionada, **When** escolho como chegar, **Then** vejo origem, destino, andar e caminho destacado, incluindo conexão entre andares quando necessária.
3. **Given** uma origem selecionada manualmente, **When** inicio o trajeto, **Then** posso avançar na simulação, concluir ou cancelar, consultando também instruções textuais.
4. **Given** qualquer trajeto ativo, **When** uma promoção próxima fica elegível, **Then** nenhum pop-up promocional aparece e um pop-up aberto anteriormente é fechado.

### User Story 3 - Explorar promoções e recomendações (Priority: P2)

Como visitante, quero explorar ofertas em cards, carrosséis e stories relacionados aos meus interesses.

**Why this priority**: Ajuda a descobrir produtos sem uma consulta exata.
**Independent Test**: Abrir home, escolher categoria, navegar por stories e abrir uma oferta.

**Acceptance Scenarios**:

1. **Given** a home, **When** acesso a tela, **Then** vejo busca superior, atalhos de categoria com silhuetas, destaque grande de promoção, carrossel e stories.
2. **Given** gostos, pesquisas recentes, compras fictícias, desejos ou alertas, **When** vejo recomendações, **Then** produtos relacionados recebem destaque; sem histórico, aparecem ofertas gerais vigentes.
3. **Given** uma busca ativa, **When** abro um story relacionado, **Then** posso avançar, voltar, fechar ou abrir o produto sem perder texto e filtros.
4. **Given** localização simulada a até 50 metros de uma loja no mesmo andar e nenhum trajeto ativo, **When** existe promoção vigente, **Then** um pop-up dispensável pode aparecer, no máximo uma vez por promoção por sessão e com intervalo mínimo de cinco minutos entre pop-ups.
5. **Given** um card promocional, **When** consulto a oferta, **Then** vejo preço, condições e validade; preço anterior e desconto correspondem aos dados fictícios e não são inventados para criar urgência.

### User Story 4 - Acessar conta e manter desejos e preferências (Priority: P1)

Como usuário, quero criar uma conta, entrar por e-mail/senha, Google ou Apple e manter meus gostos e produtos salvos entre acessos.

**Why this priority**: Login funcional é obrigatório para proteger e manter os recursos pessoais.
**Independent Test**: Criar conta, entrar, salvar desejos, sair e entrar novamente; repetir com Google e Apple e verificar isolamento entre duas contas.

**Acceptance Scenarios**:

1. **Given** cadastro funcional, **When** preencho nome, e-mail e senha válidos, **Then** uma conta é criada e avanço à escolha de gostos e produtos desejados; foto é opcional e erros aparecem junto aos campos.
2. **Given** a etapa de gostos, **When** escolho receber anúncios por e-mail, **Then** a opção começa desmarcada e pode ser alterada sem impedir uso do protótipo.
3. **Given** login, **When** informo e-mail e senha válidos, **Then** entro na minha conta; a tela oferece senha mascarada/revelável e preenchimento de credenciais, e o perfil exibe avatar ou imagem padrão.
4. **Given** esqueci a senha de uma conta por e-mail, **When** informo e-mail válido, **Then** vejo confirmação genérica e, se a conta existe, recebo mensagem real com link temporário de uso único para redefinir a senha e entrar com a nova credencial.
5. **Given** um produto e minha conta autenticada, **When** salvo nos desejos ou solicito reposição, **Then** posso consultar e remover a inscrição após sair, reiniciar o app e entrar novamente, inclusive em outro dispositivo.
6. **Given** um alerta de reposição, **When** simulo retorno ao estoque, **Then** vejo aviso dentro do protótipo, sem envio de e-mail real.
7. **Given** login por Google ou Apple, **When** autorizo o provedor, **Then** entro em uma conta funcional com perfil persistente; cancelar ou falhar mantém o usuário fora da conta e permite tentar novamente.
8. **Given** um visitante sem login, **When** tenta salvar desejos, configurar alertas ou preferências pessoais, **Then** é direcionado ao login e retorna ao contexto anterior após autenticar, sem salvar silenciosamente a ação.
9. **Given** duas contas distintas, **When** uma tenta acessar ou alterar dados pessoais da outra, **Then** o acesso é negado; sair da conta impede continuar usando sua sessão para acessar recursos protegidos.

### User Story 5 - Conhecer a proposta em duas landing pages (Priority: P3)

Como visitante externo, quero entender a proposta e acessar a demonstração pelas páginas de apresentação.

**Why this priority**: Duas landing pages são obrigatórias na entrega final.
**Independent Test**: Abrir ambas em celular e computador e acionar suas chamadas principais.

**Acceptance Scenarios**:

1. **Given** a página para consumidores, **When** a acesso, **Then** entendo busca, comparação, ofertas e mapa e encontro chamada que abre a demonstração.
2. **Given** a página para lojistas, **When** a acesso, **Then** entendo a proposta de visibilidade e encontro chamada que abre uma loja fictícia da demonstração.
3. **Given** qualquer página em tela pequena ou grande, **When** navego, **Then** conteúdo e chamadas são legíveis e operáveis, sem rolagem horizontal.

### Edge Cases

- Busca vazia apresenta categorias; sem resultados, mantém consulta e permite limpar filtros ou explorar semelhantes identificados.
- Preço mínimo maior que máximo impede aplicar o filtro e mostra orientação.
- Localização indisponível permite escolher origem manualmente.
- Origem inválida, destino removido ou caminho inexistente impede iniciar trajeto e permite outra seleção.
- Lojas sobrepostas no mapa permitem seleção distinta; mudança de andar é explícita.
- Promoções expiradas perdem destaque; estoque atualizado aparece antes de iniciar novo trajeto.
- Falha de carregamento mostra erro e tentativa novamente; não simula sucesso silencioso.
- Recusar anúncios por e-mail não desativa desejos nem alertas internos.
- Credenciais inválidas e recuperação de conta usam respostas genéricas que não revelam se um e-mail está cadastrado.
- Link de recuperação expirado ou reutilizado não altera a senha e permite solicitar novo link.
- Sessão expirada ou revogada exige novo login; falhas de conexão não apagam dados persistidos nem simulam gravação bem-sucedida.
- Cancelamento do login social não cria sessão. Contas de provedores com e-mail coincidente não são mescladas apenas pelo texto do e-mail, sem comprovação de titularidade.

## Requisitos do projeto

### Functional Requirements

- **FR-001**: Priorizar uso mobile; manter busca, comparação, mapa e descoberta públicos e exigir login funcional para desejos, alertas e preferências pessoais (histórias 1–4).
- **FR-002**: Usar nomes comerciais, lojas, logos e ofertas fictícios e sinalizar dados comerciais, preços e localização demonstrativos; contas de usuários são funcionais e não devem ser tratadas como identidades fictícias (todas as histórias).
- **FR-003**: Buscar por nome, categoria, sinônimos e necessidades contempladas no catálogo demonstrativo; não exigir interpretação irrestrita de linguagem natural (história 1).
- **FR-004**: Combinar texto, categoria/tipo e faixa de preço, exibindo filtros ativos removíveis individualmente ou em conjunto (história 1).
- **FR-005**: Ordenar por estoque disponível, preço atual crescente, promoção vigente em empate e nome do produto/loja; publicidade não pode alterar essa ordem (história 1).
- **FR-006**: Destacar produto e preço antes da identidade da loja, com pequena logo e nome abaixo do item (história 1).
- **FR-007**: Comparar o mesmo produto e variante entre lojas; apresentar semelhantes separadamente com indicação de categoria ou atributo em comum (história 1).
- **FR-008**: Colocar indisponíveis por último e permitir alerta demonstrativo de reposição (histórias 1 e 4).
- **FR-009**: Exibir busca superior, silhuetas de categoria, grande destaque, carrossel e stories na home (história 3).
- **FR-010**: Personalizar destaques por gostos, pesquisas, compras fictícias, desejos e reposição, usando ofertas gerais sem histórico e preservando os filtros da busca (história 3).
- **FR-011**: Oferecer stories na descoberta e busca com avançar, voltar, fechar e abrir oferta preservando o contexto (história 3).
- **FR-012**: Exibir validade e condições das promoções e descontos coerentes com preços demonstrativos (história 3).
- **FR-013**: Oferecer mapa 3D com zoom, seleção de andar/loja e transição de sacolas para logos (história 2).
- **FR-014**: Abrir trajeto por oferta ou marcador, selecionar origem simulada e iniciar, avançar, cancelar e concluir percurso, incluindo conexões entre andares (história 2).
- **FR-015**: Oferecer alternativa textual para lojas e instruções e escolha manual de origem sem localização (história 2).
- **FR-016**: Exibir pop-ups próximos segundo raio simulado de 50 metros no mesmo andar, uma vez por promoção/sessão e intervalo de cinco minutos, bloqueando-os durante navegação ativa (histórias 2–3).
- **FR-017**: Criar contas funcionais por nome, e-mail e senha, com foto opcional e gostos, validação de campos obrigatórios e prevenção de contas duplicadas pelo mesmo e-mail (história 4).
- **FR-018**: Autenticar por e-mail/senha, oferecer máscara e preenchimento de credenciais e recuperação real por e-mail com link temporário de uso único (história 4).
- **FR-019**: Manter opção de anúncios por e-mail inicialmente desmarcada e alterável; consentimento de marketing não condiciona criação de conta, recuperação de senha, desejos ou alertas internos. Envio de marketing não integra esta entrega (história 4).
- **FR-020**: Permitir adicionar, consultar e remover desejos/alertas e persistir esses dados e preferências por conta entre sessões e dispositivos autenticados (história 4).
- **FR-021**: Entregar prototipagem navegável de login, cadastro, gostos, recuperação, home, busca/filtros, comparação, desejos/alertas, stories, mapa e trajeto, incluindo estados vazios e de erro (histórias 1–4).
- **FR-022**: Entregar duas landing pages distintas, para consumidores e lojistas, com chamadas operantes para a demonstração (história 5).
- **FR-023**: Permitir toque e teclado onde disponível, nomes acessíveis para ícones e comunicação de estoque e promoção além de cor (todas as histórias).

- **FR-024**: Permitir logout e impedir reutilização da sessão encerrada nos recursos pessoais; negar acesso não autenticado e acesso aos dados de outras contas (história 4).
- **FR-025**: Não armazenar senhas em texto legível nem expor credenciais em respostas ou registros; comunicar falhas de autenticação de forma genérica (história 4).
- **FR-026**: Oferecer login funcional por Google e Apple, tratando autorização, cancelamento e falha; vincular identidades somente após comprovar titularidade (história 4).

### Entidades principais

- **Produto**: Identidade, nome, categoria, marca/modelo fictícios, variante, imagem, sinônimos e atributos de similaridade.
- **Loja**: Nome/logo fictícios, andar e localização no shopping.
- **Oferta**: Produto/variante em uma loja, preço atual, preço anterior opcional e estoque.
- **Promoção**: Ofertas abrangidas, condições, validade e conteúdo de cards/stories.
- **Conta e perfil**: Identificador, nome, e-mail, identidades de acesso, avatar opcional, gostos e consentimento de marketing associados a uma conta funcional.
- **Desejo e alerta**: Produto de interesse, inscrição de reposição e estado do aviso simulado.
- **Sinal de interesse**: Pesquisa, gosto, desejo, alerta ou compra fictícia usada em recomendações.
- **Shopping e trajeto**: Andares, pontos conectados, origem, destino, caminho e estado de navegação.
- **Sessão de acesso**: Conta autenticada, validade e estado de encerramento/revogação; filtros e histórico de pop-ups podem continuar temporários, enquanto desejos e preferências pertencem à conta.

## Critérios de sucesso do projeto

### Measurable Outcomes

- **SC-001**: Pelo menos 4 de 5 participantes encontram produto e loja de menor preço em até 90 segundos, sem ajuda, em catálogo com pelo menos 30 produtos e 6 lojas fictícias.
- **SC-002**: Em todos os casos de comparação preparados, preços e estoque de pelo menos duas lojas estão corretos; variantes e semelhantes não são confundidos com produto idêntico.
- **SC-003**: Pelo menos 4 de 5 participantes iniciam trajeto em até 60 segundos após abrir uma oferta, incluindo um percurso de teste com mudança de andar.
- **SC-004**: Nenhum pop-up aparece em 20 tentativas durante trajetos ativos; os testes fora de trajeto respeitam proximidade e frequência definidas.
- **SC-005**: Em 95% de 20 buscas/alterações de filtro com catálogo já carregado, resultados aparecem em até 2 segundos no dispositivo de referência documentado para a demonstração.
- **SC-006**: Pelo menos 4 de 5 participantes concluem cadastro funcional, gostos e um desejo em até 3 minutos e recuperam o desejo após sair e entrar novamente.
- **SC-007**: Todos os fluxos de FR-021 são navegáveis; ambas as landing pages funcionam em larguras de 360 e 1280 pixels com chamadas corretas e sem rolagem horizontal.
- **SC-008**: Todos os testes de ordenação colocam indisponíveis ao final e todos os descontos correspondem aos preços fictícios, com identificação demonstrativa visível.

- **SC-009**: Em todos os testes com duas contas distintas, nenhuma consegue consultar ou alterar dados pessoais da outra; credenciais inválidas e sessões encerradas não dão acesso a recursos protegidos.
- **SC-010**: A recuperação envia mensagem real e permite redefinir e usar a nova senha; links expirados ou reutilizados falham em todos os casos preparados.
- **SC-011**: Os três métodos de login concluem autenticação real; cancelamentos e falhas não criam sessão e os dados pessoais permanecem disponíveis no novo acesso da mesma conta.

## Assumptions

- Nome de trabalho: Vitrine Perto. Um shopping fictício com pelo menos dois andares compõe o cenário inicial.
- A orientação mais recente substitui o registro não funcional: cadastro, login, recuperação de senha e persistência por conta são reais. Catálogo comercial, localização, estoque e avanço de percurso continuam demonstrativos.
- E-mail/senha, Google e Apple estão confirmados como métodos de autenticação. Preenchimento de credenciais do dispositivo também permanece previsto.
- Duas landing pages significam páginas para consumidores e lojistas; essa divisão é uma suposição revisável.
- Marketplace significa descoberta e comparação. Checkout, pagamento, reserva, entrega e operação administrativa de lojas ficam fora do escopo. Compras anteriores são dados fictícios pré-carregados.
- O mapa demonstra navegação indoor, sem prometer posicionamento real preciso ou orientação física garantida.
- Desejos, alertas e preferências persistem por conta após reinício e novo acesso. Visitantes usam descoberta pública sem acesso a recursos pessoais.
- Recuperação de senha depende de envio de e-mail configurado; login social depende de credenciais dos provedores para os ambientes de entrega. Alertas de reposição continuam demonstrativos dentro do app, sem envio real de campanhas.
- Dados de demonstração devem incluir múltiplas lojas por produto, variantes, similares, estoque zerado, sinônimos e promoções expiradas.
- Apelo promocional significa apresentação visual atraente com preços coerentes e dados fictícios identificados, sem descontos falsificados.
- A constituição atual ainda é um template sem princípios aprovados.
- Restrições técnicas solicitadas estão preservadas em [planning-input.md](planning-input.md) para a próxima fase.
