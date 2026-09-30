# A FENDA: PLATAFORMA WEB DE INTERAÇÃO E SERVIÇOS PARA A COMUNIDADE UNIVERSITÁRIA

**Autor:** [CONFIRMAR NOME COMPLETO]  
**Curso/Turma:** [PREENCHER]  
**Orientador(a):** [PREENCHER]  
**Instituição:** Centro Universitário de Votuporanga — UNIFEV  
**Data:** [PREENCHER]

## RESUMO

A Fenda — Spotted Universitário é uma aplicação web concebida para reunir, em um ambiente voltado à comunidade universitária, publicações, conversas e serviços de interesse cotidiano. A ideia surgiu de um repositório de desenvolvimento versionado com Git e tinha inicialmente como foco uma área de achados e perdidos. Durante a evolução do projeto, esse escopo foi ampliado para um hub com feed de publicações, perfis, comunidades, eventos, classificados e recursos de interação. O objetivo deste trabalho é apresentar a concepção, a implementação e o estado atual da plataforma, destacando como seus módulos procuram aproximar estudantes e organizar atividades e informações que poderiam ficar dispersas em diferentes canais. O desenvolvimento foi realizado de forma incremental, com levantamento e revisão de requisitos, implementação das telas e dos fluxos de dados, testes locais e ajustes iterativos de interface. A aplicação utiliza PHP no servidor, JavaScript no cliente, CSS para apresentação responsiva e um banco de dados compatível com MySQL; o repositório também contém integrações com serviços de autenticação e armazenamento de arquivos, além de configurações para execução e publicação. Entre as funcionalidades implementadas estão cadastro e autenticação, feed com publicações, comentários e reações, perfis, comunidades com participação de membros, eventos, classificados e achados e perdidos. A validação relatada nesta etapa inclui inspeção funcional do projeto e testes de interface em dispositivos emulados pelo DevTools, abrangendo diferentes larguras e orientações de tela. Esses testes permitiram identificar e corrigir problemas de dimensionamento de mídia e conteúdo em telas pequenas. Como o projeto continua em desenvolvimento, os resultados descrevem a implementação observável e os testes realizados, sem afirmar adoção ampla, eficácia social comprovada ou disponibilidade contínua em produção. Conclui-se que a plataforma constitui uma base funcional para um espaço digital universitário mais contextualizado, cuja evolução depende da conclusão das validações pendentes, de testes com usuários e da continuidade das melhorias de segurança, acessibilidade e usabilidade.

**Palavras-chave:** comunidade universitária; aplicação web; interação digital; desenvolvimento de software.

## 1. INTRODUÇÃO

A comunicação cotidiana de uma comunidade universitária pode envolver avisos, dúvidas, eventos, conversas e a troca de objetos ou serviços. Quando essas atividades ficam distribuídas entre canais distintos, pode ser difícil encontrar conteúdos relacionados ao contexto do campus. A Fenda — Spotted Universitário foi criada como uma proposta de espaço digital voltado a esse contexto, reunindo diferentes formas de publicação e participação em uma mesma aplicação.

Conforme o histórico relatado pelo autor, A Fenda começou como seu primeiro projeto versionado com Git e tinha como finalidade inicial oferecer uma seção de achados e perdidos. O autor recorda que, após um commit, o computador apresentou uma tela azul, provavelmente em junho ou julho de 2026. Ele perdeu os arquivos locais de desenvolvimento acumulados desde fevereiro e precisou recuperar ou recriar o repositório para continuar trabalhando em outro computador. A data exata e os detalhes técnicos da recuperação não puderam ser confirmados. O repositório consultado ainda apresenta branches com commits de abril e maio de 2026, anteriores à perda segundo essa lembrança; isso mostra que alguns registros dessas etapas permaneceram acessíveis no GitHub, mas não reconstitui os arquivos locais perdidos nem a cronologia posterior completa. Assim, a evolução inicial é apresentada como memória do autor complementada por evidências pontuais de versionamento, e não como uma sequência integral de commits.

Ao longo do desenvolvimento, a proposta foi ampliada para incluir um feed de publicações e outros módulos de interesse da comunidade acadêmica. Essa evolução representa uma mudança de escopo: de uma funcionalidade pontual para uma plataforma web com áreas relacionadas entre si.

O trabalho apresenta a motivação, os objetivos, o processo de desenvolvimento, a arquitetura observável no repositório e os resultados verificados até o momento. A descrição distingue funcionalidades presentes no código de configurações de hospedagem e integrações cuja operação contínua depende de ambientes externos.

## 2. OBJETIVOS

### 2.1 Objetivo geral

Desenvolver uma aplicação web destinada a apoiar a interação e a circulação de informações de interesse da comunidade universitária, por meio de publicações, comunidades, eventos e serviços complementares.

### 2.2 Objetivos específicos

- Implementar cadastro, autenticação e áreas acessíveis a usuários autenticados.
- Disponibilizar um feed de publicações com categorias, comentários e reações.
- Oferecer páginas de perfil e ferramentas de participação em comunidades.
- Reunir funcionalidades para divulgação e interação em eventos.
- Incluir áreas de classificados e achados e perdidos.
- Adaptar a interface a diferentes tamanhos de tela e orientações.
- Organizar a aplicação em módulos de servidor, interface, estilos e integrações.
- Validar progressivamente os fluxos e a apresentação, registrando limitações e itens pendentes.

## 3. JUSTIFICATIVA

A proposta responde à necessidade de oferecer um espaço digital com foco no contexto universitário. Diferentemente de uma página dedicada a apenas um tipo de anúncio, A Fenda reúne recursos para compartilhar publicações, interagir com outros usuários, participar de comunidades e consultar informações sobre eventos, classificados e objetos perdidos ou encontrados.

O projeto não pretende substituir todas as redes sociais ou canais institucionais existentes. Sua contribuição proposta é complementar esses meios com uma aplicação organizada em torno de interesses e atividades relacionados à comunidade acadêmica. A justificativa do produto está em reunir essas funções em um mesmo ambiente, cuja utilidade deverá ser avaliada com usuários em etapas futuras.

A concentração de módulos em uma plataforma também pode facilitar a descoberta de conteúdos que, de outra forma, estariam dispersos. Para que esse benefício se concretize, a aplicação precisa manter informações compreensíveis, controles adequados e uma experiência utilizável em diferentes dispositivos. A proteção de dados pessoais é igualmente relevante, uma vez que a plataforma lida com contas, perfis e conteúdo criado pelos usuários; a legislação brasileira estabelece princípios e obrigações aplicáveis ao tratamento de dados pessoais [3]. Este texto apresenta essa preocupação como requisito de projeto, não como declaração de conformidade jurídica já auditada.

## 4. METODOLOGIA

### 4.1 Abordagem de desenvolvimento

O trabalho caracteriza-se como desenvolvimento aplicado de um produto de software. O processo foi incremental: a solução começou com uma necessidade delimitada — achados e perdidos — e recebeu novos módulos e ajustes ao longo de ciclos de implementação. A documentação do projeto e o histórico de alterações em Git servem como instrumentos de organização do trabalho e acompanhamento da evolução.

O desenvolvimento considerou atividades de engenharia de software, como identificar objetivos, definir funcionalidades, organizar módulos, validar e rever requisitos conforme a solução era construída [1]. Não há, no material consultado para esta versão, evidência suficiente para caracterizar o processo como pesquisa formal com entrevistas, questionários ou experimento controlado. Assim, a análise de requisitos é descrita como conduzida pelo autor a partir do problema percebido, dos objetivos do produto e das revisões iterativas do sistema.

Como referência exploratória de interface, o autor observou elementos visuais e padrões de interação encontrados em plataformas sociais e de mensagens, incluindo Facebook, Instagram, WhatsApp e Tinder. Essas observações informais serviram de inspiração para decisões de apresentação e interação da Fenda; não constituem avaliação comparativa nem documentação oficial das plataformas. O padding observado nas conversas do WhatsApp por meio das ferramentas de desenvolvedor, por exemplo, deve ser entendido como uma referência visual pontual, sujeita à versão da interface e ao contexto em que foi observada, e não como especificação oficial do serviço. O Orkut, por ser uma plataforma descontinuada, só deve ser apresentado como referência consultada se o autor indicar materiais preservados efetivamente examinados; lembranças pessoais podem ser relatadas como memória, não como fonte técnica.

O autor conduziu a concepção, as decisões de escopo e a implementação principal do projeto. Ferramentas de assistência por inteligência artificial foram utilizadas durante o desenvolvimento como apoio à investigação de problemas, revisão e elaboração de documentação; a seleção das alterações e a validação final permanecem sob responsabilidade do autor. Essa declaração deve ser ajustada às orientações acadêmicas da disciplina.

#### Evolução técnica segundo o relato do autor

A sequência abaixo resume a lembrança do autor e deve ser entendida como aproximada: a perda do repositório original reduziu a disponibilidade de registros e o próprio autor não afirma recordar a ordem exata de todas as etapas. Os itens descrevem decisões e dificuldades relatadas, não resultados de testes independentes.

O histórico do GitHub consultado em 29 de setembro de 2026 expõe branches de trabalho com nomes como `caos-iphone4`, `feature-swipe-ap`, `feature-motor-dinamico`, `spotted_totalmente_redesenhado` e `xamp--spotted-unifevpc`, além de `main`. Essas branches são linhas de desenvolvimento distintas e não devem ser lidas automaticamente como fases integradas ou uma cronologia linear. Na branch `caos-iphone4`, há um commit datado de 15 de abril de 2026 cujo título registra problemas de layout associados ao iPhone 4. Na `feature-swipe-ap`, um commit de 17 de maio de 2026 descreve ajustes no modo swipe, movimento suavizado e trabalho de layout para telas pequenas. Esses títulos confirmam que tais temas foram registrados nessas datas, mas não substituem um roteiro formal de testes nem provam que cada alteração foi incorporada à versão de produção.

As primeiras versões foram hospedadas temporariamente em Railway e Render. Segundo o autor, o período de uso do Railway terminou e o Render apresentou instabilidade relacionada à persistência de sessões, com respostas de erro observadas durante o uso. Em uma etapa posterior, o autor migrou a aplicação para Vercel e o banco para TiDB. A configuração de roteamento e execução de PHP na Vercel exigiu trabalho adicional; o autor também relata que o limite de payload dessa plataforma motivou a criação de compactação de mídia antes do envio ao armazenamento externo. A integração com Supabase Auth passou a atender funções de autenticação, enquanto o Backblaze B2 foi adotado para armazenar arquivos, mantendo no banco principalmente referências e URLs, em vez dos próprios arquivos.

Na evolução da interface, o recurso de cartões deslizáveis passou por tentativas com biblioteca externa e por problemas de jitter e condições de corrida associados à interação e à observação de mudanças na página. Conforme o relato, o autor e colaboradores optaram por desenvolver um mecanismo próprio em JavaScript, refinado em etapas com limiares de gesto, proteção contra jitter, interação de pressionar e segurar, animações, variáveis de estilo e alternativas de fallback. O autor descreve que a experiência desse modo também levou à consolidação de uma função JavaScript de recálculo de layout para os cartões, reduzindo a dependência de várias media queries específicas.

Em paralelo, foram acrescentados recursos como domínio próprio, envio de e-mails pelo Resend, comentários com cabeçalho dinâmico, visualização detalhada de publicações, comunidades, eventos e interações de perfil. Também foram relatados desafios com token CSRF em execução serverless, anexos em modais concorrentes, cadastro, rotas de fallback e compatibilidade de código com serviços externos. Como CSS e funcionalidades continuaram sendo refinados em diferentes momentos, não é possível atribuir uma data única de início ou conclusão a cada módulo com os registros disponíveis.

### 4.2 Requisitos funcionais identificados

Os requisitos funcionais observáveis na aplicação incluem:

1. Permitir cadastro e autenticação de usuários.
2. Exibir um feed de publicações e permitir filtragem por categoria e contexto.
3. Permitir publicação de conteúdo, comentários e reações.
4. Disponibilizar páginas de perfil.
5. Permitir criação e participação em comunidades, incluindo gestão de membros.
6. Disponibilizar criação e consulta de eventos e respostas relacionadas.
7. Oferecer módulos de classificados e achados e perdidos.
8. Apresentar notificações e ferramentas de administração e moderação em áreas próprias.

### 4.3 Requisitos não funcionais e critérios de qualidade

Entre os requisitos não funcionais considerados estão a adaptação da interface a telas de celular, tablet e computador; a organização modular dos arquivos; a validação de dados recebidos; e a proteção dos fluxos de autenticação e interação. O projeto não foi submetido a auditoria formal, portanto a presença de mecanismos específicos não deve ser tomada como certificação de segurança. O guia de testes da OWASP pode orientar verificações futuras de riscos como falsificação de requisições entre sites (CSRF) e execução de scripts entre sites (XSS) [2]. O OWASP Top 10:2025, por sua vez, apresenta dez categorias de riscos relevantes para conscientização sobre segurança de aplicações web; sua menção não significa que tenha sido realizada uma auditoria baseada nessa lista [5]. Para acessibilidade, as WCAG 2.2 fornecem critérios verificáveis, incluindo o critério de *Reflow* para apresentação do conteúdo em larguras reduzidas [4].

### 4.4 Modelagem das telas e navegação

A navegação funcional observada no projeto é apresentada na Figura 1. A interface é composta por páginas PHP e componentes reutilizáveis, com folhas de estilo e scripts separados. O modo de feed em cartões empilhados (“swipe”) é uma apresentação alternativa do feed, ativada conforme a preferência de interface registrada para o usuário.

**[INSERIR AQUI A FIGURA 1 — DIAGRAMA DE NAVEGAÇÃO]**

**Figura 1 — Diagrama de navegação funcional da plataforma A Fenda**  
[Inserir a imagem exportada do diagrama de navegação]  
Fonte: elaborado pelo autor com base nas funcionalidades identificadas no projeto (2026).

### 4.5 Modelo lógico de dados

O arquivo SQL exportado do banco de produção `fenda_db` contém a definição de 21 tabelas, incluindo colunas, chaves primárias, índices, restrições únicas e chaves estrangeiras. A exportação contém estrutura, sem registros. O dump identifica TiDB Serverless compatível com MySQL 8.0 (TiDB v8.5.3). O banco local também possui uma estrutura para desenvolvimento e testes, mas é distinto do banco de produção; portanto, este modelo descreve especificamente o esquema de produção exportado e não afirma que os dois ambientes tenham estruturas idênticas. A descrição representa o esquema no momento da exportação, não uma garantia de que ele permaneça inalterado após essa data.

| Tabela | Finalidade observável pelo esquema |
|---|---|
| `usuarios` | Contas, credenciais, perfil e preferências de interface; `email` e `username` possuem restrições únicas. |
| `mensagens` | Publicações com texto, anexos, categoria, estado e possível associação a usuário e comunidade. Achados e perdidos são publicados no feed e identificados pela categoria e pelas subcategorias “achei” e “perdi”. |
| `comentarios` | Comentários em publicações, com possibilidade de resposta a outro comentário. |
| `curtidas` | Reações de usuários a publicações, com tipo e data. |
| `comunidades` | Comunidades, com nome, slug, tipo e usuário criador. |
| `comunidade_membros` | Associação entre usuários e comunidades, incluindo papel e estado de participação. |
| `eventos` | Eventos com criador, descrição, data, local e outros dados; há um campo `comunidade_id`. |
| `evento_respostas` | Resposta de um usuário a um evento (`vou`, `nao_vou` ou `talvez`). |
| `evento_comentarios` | Comentários de usuários associados a eventos. |
| `anuncios` | Classificados com título, descrição, preço, categoria, tipo e estado. |
| `seguidores` | Relações direcionadas de seguimento entre usuários. |
| `avaliacoes_perfil` | Avaliações de um usuário sobre outro, por tipo. |
| `depoimentos` | Mensagens de um usuário destinadas a outro, sujeitas a estado de aprovação. |
| `notificacoes` | Notificações associadas a um usuário e, opcionalmente, a uma publicação. |
| `sessoes_ativas` | Registros de sessão, token, atividade e metadados de conexão. |
| `logs_auditoria` | Registros de ações e detalhes associados a um identificador de usuário. |
| `comentarios_ip_log` | Registro de tentativas por endereço IP relacionadas a comentários. |
| `rate_limiter_avaliacoes` | Registros de tentativas por IP para avaliações. |
| `rate_limiter_depoimentos` | Registros de tentativas por IP para depoimentos. |
| `rate_limiter_polling` | Registros de tentativas por IP para operações de polling. |
| `rate_limiter_reacoes` | Registros de tentativas por IP e, opcionalmente, identificador de usuário para reações. |

O modelo entidade-relacionamento correspondente ao esquema físico está representado nas Figuras 2 a 6. Para manter legíveis as entidades e suas conexões, o DER foi organizado em quatro recortes de domínio, além da página operacional. A entidade `usuarios` e, quando necessário, `mensagens` são repetidas como referências visuais entre páginas; isso não significa que existam tabelas duplicadas no banco.

**[INSERIR AQUI A FIGURA 2 — DER: PUBLICAÇÕES, COMENTÁRIOS E REAÇÕES]**

**Figura 2 — Diagrama entidade-relacionamento: publicações, comentários e reações**  
[Inserir a imagem exportada da página “DER - Publicacoes”]  
Fonte: elaborado pelo autor com base no esquema do banco de produção, exportado sem dados (2026).

**[INSERIR AQUI A FIGURA 3 — DER: COMUNIDADES]**

**Figura 3 — Diagrama entidade-relacionamento: comunidades e publicações associadas**  
[Inserir a imagem exportada da página “DER - Comunidades”]  
Fonte: elaborado pelo autor com base no esquema do banco de produção, exportado sem dados (2026).

**[INSERIR AQUI A FIGURA 4 — DER: PERFIL]**

**Figura 4 — Diagrama entidade-relacionamento: perfil e relações entre usuários**  
[Inserir a imagem exportada da página “DER - Perfil”]  
Fonte: elaborado pelo autor com base no esquema do banco de produção, exportado sem dados (2026).

**[INSERIR AQUI A FIGURA 5 — DER: EVENTOS]**

**Figura 5 — Diagrama entidade-relacionamento: eventos, respostas e comentários**  
[Inserir a imagem exportada da página “DER - Eventos”]  
Fonte: elaborado pelo autor com base no esquema do banco de produção, exportado sem dados (2026).

**[INSERIR AQUI A FIGURA 6 — DER: TABELAS OPERACIONAIS]**

**Figura 6 — Diagrama entidade-relacionamento: tabelas operacionais**  
[Inserir a imagem exportada da página “DER - Operacional”]  
Fonte: elaborado pelo autor com base no esquema do banco de produção, exportado sem dados (2026).

#### Relacionamentos e cardinalidades

As cardinalidades abaixo são interpretadas pelas chaves estrangeiras, nulabilidade e restrições únicas presentes no SQL exportado. Onde a tabela filha permite `NULL` na chave estrangeira, a associação do registro filho ao pai é opcional; onde não permite, cada registro filho deve apontar para um único pai. Um pai pode ter nenhum ou vários registros filhos, salvo restrição única que limite essa quantidade.

- **Usuário — publicações:** um usuário pode ter zero ou muitas publicações; cada publicação pode estar associada a zero ou um usuário, pois `mensagens.usuario_id` aceita `NULL` e usa `ON DELETE SET NULL`.
- **Achados e perdidos:** são publicações do feed classificadas pela categoria de achados e perdidos e pela subcategoria “achei” ou “perdi”; não constituem uma tabela ou módulo de publicação separado.
- **Comunidade — publicações:** uma comunidade pode ter zero ou muitas publicações; cada publicação pode estar associada a zero ou uma comunidade, pois `mensagens.comunidade_id` aceita `NULL` e usa `ON DELETE SET NULL`.
- **Usuário — comentários:** um usuário pode estar associado a zero ou muitos comentários; o autor de um comentário é opcional (`usuario_id` aceita `NULL`).
- **Publicação — comentários:** uma publicação pode possuir zero ou muitos comentários; cada comentário referencia uma publicação. A exclusão da publicação remove seus comentários (`ON DELETE CASCADE`).
- **Comentário — comentário:** um comentário pode ter zero ou muitas respostas; cada resposta pode ter zero ou um comentário pai (`parent_id` aceita `NULL`).
- **Usuário — reações — publicação:** usuários e publicações relacionam-se por `curtidas`. A restrição única `(usuario_id, mensagem_id)` permite no máximo uma reação por usuário em cada publicação. Cada reação aponta para exatamente um usuário e uma publicação.
- **Usuário — comunidade:** é uma relação muitos-para-muitos representada por `comunidade_membros`. A chave primária composta `(comunidade_id, usuario_id)` permite um único registro de participação para cada par usuário-comunidade; cada registro referencia uma comunidade e um usuário.
- **Usuário — comunidade criada:** cada comunidade referencia exatamente um criador; um usuário pode criar zero ou várias comunidades.
- **Usuário — eventos:** cada evento referencia exatamente um criador; um usuário pode criar zero ou vários eventos.
- **Evento — respostas — usuário:** é uma relação muitos-para-muitos representada por `evento_respostas`; a chave primária composta permite uma resposta por par evento-usuário.
- **Evento — comentários — usuário:** cada comentário de evento referencia exatamente um evento e um usuário; cada evento e cada usuário podem estar associados a zero ou vários comentários.
- **Usuário — anúncios:** cada anúncio referencia exatamente um usuário; um usuário pode publicar zero ou vários anúncios.
- **Usuário — seguidores — usuário:** representa uma relação direcionada entre usuários. A chave única `(id_seguidor, id_seguido)` impede duplicar o mesmo par; ambos os identificadores referenciam usuários.
- **Usuário — avaliações de perfil:** cada avaliação referencia um usuário avaliado e um avaliador. A restrição única sobre `(usuario_avaliado_id, usuario_avaliador_id, tipo)` permite no máximo uma avaliação de cada tipo para o par ordenado de usuários.
- **Usuário — depoimentos:** cada depoimento referencia um autor e um destinatário; ambos podem estar associados a vários depoimentos.
- **Usuário — notificações:** cada notificação pertence a exatamente um usuário; um usuário pode ter zero ou várias notificações. A referência à publicação é opcional e fica nula se a publicação for removida.

Alguns campos parecem representar relações, mas não possuem `FOREIGN KEY` no dump: `eventos.comunidade_id`, `sessoes_ativas.usuario_id`, `logs_auditoria.usuario_id` e `rate_limiter_reacoes.usuario_id`. Portanto, o banco não garante integridade referencial para esses campos por meio de constraints declaradas.

As regras acima descrevem as constraints encontradas, não todas as regras de negócio nem o conteúdo efetivo do banco. O arquivo [der-fenda-producao.drawio](./der-fenda-producao.drawio) contém um DER editável, preparado a partir do dump estrutural de produção sem dados. As cinco páginas do arquivo separam as relações de negócio por domínio e as tabelas operacionais sem `FOREIGN KEY`.

### 4.6 Arquitetura e hospedagem

A aplicação é implementada principalmente em PHP, com JavaScript no navegador e CSS para apresentação. O backend usa `mysqli` para acesso ao TiDB, compatível com o protocolo e recursos de MySQL. O código contém integração com Supabase Auth para validação de autenticação e com Backblaze B2 para operações de armazenamento de mídia. Essas integrações são configuradas por variáveis de ambiente.

O repositório inclui configuração de runtime e roteamento da Vercel, além de um `Dockerfile` baseado em PHP com Apache. Esses arquivos demonstram opções de implantação configuradas no projeto, mas não comprovam, isoladamente, que cada ambiente está ativo ou disponível no momento da entrega. Segundo o relato retrospectivo do autor, versões anteriores utilizaram Railway e Render como hospedagem temporária; após problemas de sessão e limitações de uso, a aplicação migrou para Vercel. A ordem exata das demais migrações e a situação operacional atual devem ser confirmadas para a versão final.

O navegador solicita páginas e operações ao servidor. O PHP processa autenticação, conteúdo e regras de negócio, consulta ou atualiza o banco e utiliza os serviços externos configurados quando necessário. O roteador e os arquivos de implantação determinam como essas solicitações podem ser encaminhadas em ambientes configurados.

O fluxo lógico simplificado é apresentado na Figura 7. O desenho distingue a comunicação do navegador com a aplicação, o acesso ao banco e as integrações externas. As opções de hospedagem e os serviços indicados correspondem a configurações e integrações identificadas no projeto; a figura não afirma que todos estejam ativos simultaneamente.

**[INSERIR AQUI A FIGURA 7 — FLUXO LÓGICO DA ARQUITETURA E HOSPEDAGEM]**

**Figura 7 — Fluxo lógico da arquitetura e hospedagem da plataforma A Fenda**  
[Inserir a imagem exportada de arquitetura-hospedagem-fenda.svg]  
Fonte: elaborado pelo autor com base na arquitetura e nas integrações identificadas no projeto (2026).

## 5. TECNOLOGIAS UTILIZADAS

- **PHP:** páginas, endpoints, processamento de formulários e regras do servidor.
- **JavaScript:** interações no navegador, atualização de conteúdo, filtros, menções e modos de navegação.
- **CSS:** estrutura visual, componentes e regras responsivas.
- **Font Awesome Free 6.5.1:** biblioteca de ícones carregada por CDN; a documentação oficial descreve a configuração e o uso dos ícones [6].
- **TiDB Serverless, compatível com MySQL, via `mysqli`:** persistência de contas, publicações e outras entidades do sistema, conforme os metadados do dump de produção fornecido pelo autor.
- **Supabase Auth:** integração de autenticação presente no código.
- **Backblaze B2:** cliente de armazenamento de arquivos presente no projeto.
- **Vercel e Docker/Apache:** configurações de runtime e publicação existentes no repositório.
- **Git:** versionamento do código e acompanhamento de alterações.

## 6. RESULTADOS E VALIDAÇÃO

### 6.1 Funcionalidades implementadas

O código atual contempla os principais módulos planejados: entrada e cadastro de usuários, feed, publicação de conteúdo, comentários, reações, perfis, comunidades, eventos, classificados, achados e perdidos e recursos administrativos. A aplicação também possui manifest e service worker, elementos associados à experiência de aplicação web instalável e ao tratamento de recursos em cache.

### 6.2 Testes realizados

Na etapa de refinamento visual do feed, o autor utilizou o modo responsivo do Chrome DevTools para simular diferentes dimensões e orientações, incluindo celulares pequenos e grandes, tablet e computador. Entre os dispositivos/presets registrados nos testes estão iPhone 4, iPhone SE, Samsung S10 Plus, S20 Ultra, iPhone 16 Pro Max e Zenfone 8; também foram avaliados formatos de tablet e desktop. Os testes foram feitos em emulação no computador, não em todos esses aparelhos físicos.

Para investigar problemas, foram coletadas no console medidas de cartões, contêineres de mídia, itens e imagens, incluindo dimensões renderizadas e internas, valores de `scrollWidth`/`scrollHeight`, proporção, `object-fit`, overflow e dimensões naturais das imagens. Essa inspeção identificou, por exemplo, uma imagem vertical cujo item interno excedia a altura da moldura em uma versão inicial do layout landscape, além de conteúdo de reação que ficava apertado em telas portrait pequenas. A partir das observações, foram feitos ajustes CSS na contenção da imagem e na distribuição de espaço entre texto e reações. O usuário confirmou visualmente que os cenários de iPhone 4 portrait e landscape passaram a funcionar após os ajustes.

Essa validação é exploratória e direcionada aos problemas observados: não representa cobertura exaustiva de todas as combinações de conteúdo, testes em todos os aparelhos físicos, teste automatizado de regressão visual ou avaliação formal de acessibilidade. Também foram consultados registros de desenvolvimento de sessões anteriores, que descrevem verificações funcionais pontuais em ambientes locais e de produção, mas não fornecem um protocolo uniforme nem evidência suficiente para generalizar os resultados a todos os módulos.

Um registro de agosto de 2026 descreve que o teste de upload de imagens grandes em produção ainda estava em andamento devido a problemas de exibição e roteamento. Registros posteriores sobre outras correções não confirmam especificamente que esse cenário foi resolvido; portanto, o estado desse teste precisa ser verificado novamente antes de uma eventual afirmação de suporte a uploads grandes. Os relatos históricos também não equivalem a auditoria de segurança, teste de carga, avaliação sistemática de acessibilidade ou pesquisa com usuários. Nenhum dos testes descritos, isoladamente ou em conjunto, comprova disponibilidade contínua em produção.

### 6.3 Estado do desenvolvimento

O projeto permanece em desenvolvimento. Conforme o retrato de acompanhamento de 29 de setembro de 2026, a fase inicial de correções críticas foi encerrada, enquanto a Sprint 1 — dedicada principalmente a segurança, confiabilidade dos fluxos e atualização de notificações — ainda estava em andamento, com itens implementados aguardando validação e outras correções pendentes. As Sprints 2 e 3 estavam planejadas, respectivamente, para tratar melhorias relevantes antes da apresentação do projeto e tarefas posteriores de manutenção e redução de débito técnico; não são apresentadas aqui como iniciadas ou concluídas. Este resumo registra o planejamento e o estado informado naquela data, sem detalhar a lista completa de tarefas nem equiparar itens commitados a itens testados. Assim, os resultados deste relatório se limitam às funcionalidades identificadas no código e aos testes descritos nas seções anteriores; atividades pendentes não são tratadas como concluídas.

## 7. CONCLUSÃO

O objetivo de construir um espaço digital universitário com mais de uma função foi alcançado em nível de implementação: além da ideia inicial de achados e perdidos, A Fenda dispõe de feed de publicações e módulos para perfis, comunidades, eventos e classificados. A principal contribuição do projeto é a integração desses recursos em uma plataforma voltada a um contexto acadêmico específico, acompanhada de uma interface que vem sendo adaptada a diferentes formatos de tela.

Os testes exploratórios ajudaram a encontrar problemas concretos de apresentação, mas a avaliação permanece limitada à inspeção do código e a cenários emulados. Assim, não se pode concluir ainda que a solução aumentou o engajamento da comunidade ou que atenda a todos os requisitos de segurança, acessibilidade e desempenho. Essas conclusões dependem de validações adicionais.

Como trabalhos futuros, estão previstas evoluções funcionais e avaliações complementares, ainda sujeitas a priorização e validação. Na área de interação, pretende-se estender o menu de ações por toque longo a publicações de comunidades públicas e ao perfil público, além de criar um mecanismo de descarte individual de notificações por gesto de arrasto, com alternativa de interação por menu ou reticências em computadores. Também se propõe evoluir os comentários em comunidades para uma apresentação em árvore integrada ao contexto do feed, com painel retrátil e atualização de conteúdo, reduzindo a necessidade de sair da publicação em consulta. Essa proposta corresponde a uma única funcionalidade de conversação contextual, e não a dois módulos distintos de “chat” e “comentários em cascata”.

Na organização e recuperação de conteúdo, pretende-se implementar favoritos para publicações e eventos, com lembretes programados duas horas antes dos eventos salvos; completar o módulo de classificados/marketplace; acrescentar notificações quando um evento for cancelado; e ampliar o lightbox para exibir vídeos e GIFs. Para a gestão de comunidades, prevê-se revisar os níveis de permissão de moderadores, permitindo ações de moderação sem conceder poderes de promoção de membros. Como evoluções transversais, foram planejadas melhorias de acessibilidade para as interações do modo swipe, a integração da aparência hacker ao sistema explícito de preferências de tema, uma rotina automatizada de limpeza de dados em um ciclo de sete meses para a transição entre semestres e a avaliação de notificações por serviços de mensageria, como WhatsApp ou Telegram. A aba de favoritos e alguns pontos de entrada para essas funções já aparecem na interface, mas isso não significa que os fluxos completos estejam implementados; por exemplo, a própria aplicação ainda identifica favoritos e marketplace como funcionalidades futuras.

Além das evoluções do produto, ainda são necessários testes em aparelhos físicos, avaliação com usuários representativos e verificações específicas de acessibilidade, privacidade, segurança e desempenho. Essas atividades deverão permitir priorizar as propostas e avaliar sua utilidade; portanto, as funcionalidades descritas são intenções de desenvolvimento, não resultados já alcançados nem evidência de impacto sobre a comunidade.

## REFERÊNCIAS

1. SOMMERVILLE, Ian. **Software Engineering**. 10. ed. Pearson, 2015. ISBN 978-0-13-394303-0. Disponível em: <https://www.pearson.com/en-us/subject-catalog/p/software-engineering/P200000003259/9780133943030>.
2. OWASP FOUNDATION. **Web Security Testing Guide (WSTG)**. Versão 4.2. 3 dez. 2020. Disponível em: <https://owasp.org/www-project-web-security-testing-guide/v42/>. Acesso em: 29 set. 2026.
3. BRASIL. **Lei nº 13.709, de 14 de agosto de 2018**. Lei Geral de Proteção de Dados Pessoais (LGPD). Diário Oficial da União: Brasília, DF, 15 ago. 2018. Disponível em: <https://www2.camara.leg.br/legin/fed/lei/2018/lei-13709-14-agosto-2018-787077-publicacaooriginal-156212-pl.html>. Acesso em: 29 set. 2026.
4. WORLD WIDE WEB CONSORTIUM (W3C). **Web Content Accessibility Guidelines (WCAG) 2.2**. W3C Recommendation, 5 out. 2023. Disponível em: <https://www.w3.org/TR/WCAG22/>. Acesso em: 29 set. 2026.
5. OWASP FOUNDATION. **OWASP Top 10:2025**. Disponível em: <https://owasp.org/Top10/2025/>. Acesso em: 29 set. 2026.
6. FONT AWESOME. **Font Awesome Documentation: Quick Start**. Disponível em: <https://docs.fontawesome.com/web/setup/get-started>. Acesso em: 29 set. 2026.

---

## MATERIAL DE APOIO À DIAGRAMAÇÃO NO DIAGRAMS.NET

> Esta seção é um roteiro de produção para o autor, não conteúdo do relatório acadêmico. Use as instruções para inserir as figuras no Word e remova esta seção e os marcadores entre colchetes antes da submissão, a menos que o orientador peça o roteiro metodológico.

> **Importante:** para estas figuras, não abra uma caixa de classe nem uma caixa de método. Você não está desenhando um diagrama UML de classes. No diagrama de navegação, use retângulos arredondados e setas; no DER, use caixas de entidade/tabela com campos `PK` e `FK` e linhas de relacionamento.

#### Posição e formatação das figuras no Word Online

1. Mantenha cada figura na seção indicada pelos marcadores: Figura 1 na seção 4.4; Figuras 2 a 6 na seção 4.5, depois da tabela que lista as entidades e antes de “Relacionamentos e cardinalidades”; Figura 7 na seção 4.6. Remova cada marcador e a linha de instrução correspondente depois de inserir a imagem.
2. Para as Figuras 2 a 6, abra [der-fenda-producao.drawio](./der-fenda-producao.drawio), selecione a página correspondente por vez e exporte-a como PNG.
3. A Figura 7 está disponível como [arquitetura-hospedagem-fenda.svg](./arquitetura-hospedagem-fenda.svg), um arquivo vetorial que pode ser inserido diretamente no Word. Se a versão do Word não aceitar SVG, exporte/converta o arquivo para PNG em alta resolução.
4. A escala 200% aumenta a resolução da imagem exportada, mas não o tamanho em que ela cabe na página do Word. Isso não obriga o trabalho inteiro a ficar em paisagem: use orientação paisagem somente nas páginas das figuras largas e mantenha as demais páginas no formato exigido pelo curso.
5. No Word Online, para deixar uma figura em paisagem sem mudar as páginas seguintes, insira uma quebra de seção antes e outra depois dela; selecione a página da figura e aplique **Layout → Orientação → Paisagem**. Os nomes dos menus podem variar conforme a versão. Se não conseguir configurar quebras de seção, mantenha a imagem na página retrato, mas confira se continua legível no PDF.
6. No Word Online, coloque a identificação e o título da figura acima da imagem, centralize a imagem e ajuste-a pelos cantos, sem distorcer a proporção. Coloque a fonte logo abaixo. Se o modelo do curso ou o orientador prescrever formatação, siga essa orientação. Se não houver regra, uma apresentação simples é usar título em negrito, sem itálico, em tamanho igual ao texto ou ligeiramente menor; usar a fonte abaixo em tamanho menor e regular. Mantenha os títulos e fontes com a mesma formatação.
7. Confira o resultado no PDF final. As imagens dos diagramas são figuras de documentação; não são capturas das telas do site. Se o professor não pediu capturas da aplicação, não é necessário incluir imagens das páginas do sistema.

#### Referência visual

O modelo DER editável está em [der-fenda-producao.drawio](./der-fenda-producao.drawio). Suas cinco páginas separam publicações, comunidades, perfil, eventos e tabelas operacionais; em conjunto, representam as 21 tabelas do dump estrutural de produção.

### Exportar o DER editável

1. Baixe/abra [der-fenda-producao.drawio](./der-fenda-producao.drawio) no diagrams.net. Se o arquivo não abrir automaticamente, use **Ficheiro → Importar de → Dispositivo** e selecione o `.drawio`.
2. Use as abas `DER - Publicacoes`, `DER - Comunidades`, `DER - Perfil`, `DER - Eventos` e `DER - Operacional`. Os quatro primeiros recortes contêm as 24 FKs de negócio ao todo; a última página contém sete tabelas sem FKs declaradas. Algumas entidades, como `usuarios`, se repetem como referência visual entre recortes.
3. As cinco páginas do arquivo estão em formato horizontal (paisagem). Para gerar cada imagem para o Word Online, selecione uma das abas e use **Ficheiro → Exportar como → PNG**, mantendo fundo branco. Insira cada imagem na posição indicada para as Figuras 2 a 6.
4. Os recortes menores reduzem cruzamentos e sobreposição de rótulos, mas podem continuar precisando de página paisagem no Word para manter o texto legível. Mantenha também a descrição textual das entidades e relacionamentos na seção 4.5 como apoio e confira a legibilidade no PDF final.

As pontas usam notação *Crow’s Foot* (pé-de-galinha) para indicar cardinalidade: pé-de-galinha representa muitos, barra representa um e círculo indica participação opcional. Rótulos como `PK`, `FK`, `NULL`, `NOT NULL` e `UQ` são abreviações das propriedades/chaves das colunas no banco; não são relações UML `<<include>>`. Os nomes das FKs aparecem dentro das entidades, e os rótulos curtos nas linhas distinguem o papel da relação (por exemplo, autor, destinatário ou criador).

O diagrama marca PK (chave primária), FK (chave estrangeira) e UQ (restrição única). As linhas representam apenas FKs que constam no dump. Em particular, `eventos.comunidade_id`, `sessoes_ativas.usuario_id`, `logs_auditoria.usuario_id` e `rate_limiter_reacoes.usuario_id` são mostrados como campos sem relação declarada. A coluna `comunidades.slug` também tem índice único. Achados e perdidos permanecem como categorias/subcategorias das mensagens, não como tabela independente.

---

## REVISÃO FINAL DO AUTOR

Antes de enviar ao professor/coordenador responsável, o essencial é preencher os campos de identificação no início do documento e confirmar se ele quer alguma norma de formatação específica. Como o projeto continua evoluindo, confira também se o resumo do estado atual e a data de referência dos sprints ainda estão corretos na data da submissão.

As observações técnicas abaixo são ressalvas para manter a documentação precisa; não são uma lista de tarefas de desenvolvimento que você precise concluir antes de enviar esta versão:

- O dump representa o banco de produção TiDB no momento da exportação; o banco local é separado e usado para desenvolvimento e testes.
- Algumas colunas com nomes de identificador não têm `FOREIGN KEY` declarada no dump; isso descreve uma limitação das constraints do banco, não necessariamente um erro da aplicação.
- A cronologia de hospedagem e a perda dos arquivos locais foram descritas com as incertezas do relato do autor, pois não há registros completos para confirmar cada data.
- O DER editável das 21 tabelas está incluído em [der-fenda-producao.drawio](./der-fenda-producao.drawio) e distribuído em cinco páginas para favorecer a leitura.
- A declaração sobre assistência de ferramentas de IA deve seguir a política da instituição e do orientador.
