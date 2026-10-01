# A Fenda — Documentação e apêndices

Repositório de materiais complementares à documentação acadêmica da plataforma **A Fenda — Spotted Universitário**, desenvolvida no curso de Análise e Desenvolvimento de Sistemas (ADS) do Centro Universitário de Votuporanga (UNIFEV).

Este repositório reúne diagramas vetoriais, arquivos editáveis e registros visuais de testes exploratórios. O código-fonte da aplicação está em um repositório separado: [Twester77/components-spotted-xamp](https://github.com/Twester77/components-spotted-xamp).

## Sobre o projeto

A Fenda é uma aplicação web voltada à comunidade universitária. O projeto reúne recursos como publicações, perfis, comunidades, eventos e achados e perdidos. Classificados/marketplace e administração global permanecem fora do escopo funcional concluído e não devem ser interpretados como recursos disponíveis apenas por estarem representados ou mencionados nos materiais.

Os diagramas registram uma visão conceitual ou estrutural do sistema na época em que foram produzidos. Consulte o código e o esquema do banco para verificar o estado atual da implementação.

## Conteúdo do repositório

```text
.
├── README.md
├── LICENSE
├── Captura de tela *.png
└── documentacao/
    ├── arquitetura-hospedagem-fenda.svg
    ├── der-fenda-producao.drawio
    ├── diagrama-navegacao-fenda.svg
    └── diagrama/
        ├── diagrama-casos-de-uso-fenda.svg
        ├── diagrama-classes-fenda.svg
        ├── diagrama-classes-fenda.drawio
        ├── diagrama-classes-fenda-parte-1.svg
        ├── diagrama-classes-fenda-parte-2.svg
        └── diagrama-classes-fenda-legivel.drawio
```

As imagens PNG na raiz são registros visuais de testes de interface em emuladores de dispositivos. São exemplos de cenários exploratórios, não evidência de testes em todos os aparelhos físicos.

## Diagramas

### Casos de uso

- [`diagrama-casos-de-uso-fenda.svg`](documentacao/diagrama/diagrama-casos-de-uso-fenda.svg) — atores externos e casos de uso principais.

### Classes

- [`diagrama-classes-fenda.svg`](documentacao/diagrama/diagrama-classes-fenda.svg) — visão conceitual geral das classes centrais do domínio.
- [`diagrama-classes-fenda-parte-1.svg`](documentacao/diagrama/diagrama-classes-fenda-parte-1.svg) — vista ampliada de publicações e interações.
- [`diagrama-classes-fenda-parte-2.svg`](documentacao/diagrama/diagrama-classes-fenda-parte-2.svg) — vista ampliada de comunidades e eventos.
- [`diagrama-classes-fenda.drawio`](documentacao/diagrama/diagrama-classes-fenda.drawio) — arquivo editável da visão geral.
- [`diagrama-classes-fenda-legivel.drawio`](documentacao/diagrama/diagrama-classes-fenda-legivel.drawio) — arquivo editável com as duas vistas detalhadas.

O diagrama de classes é conceitual. Os nomes de classe representam elementos do domínio e não afirmam que a aplicação PHP use classes com esses mesmos nomes.

### Dados, navegação e arquitetura

- [`der-fenda-producao.drawio`](documentacao/der-fenda-producao.drawio) — modelo entidade-relacionamento editável, elaborado a partir de uma exportação estrutural do banco de produção, sem registros de usuários.
- [`diagrama-navegacao-fenda.svg`](documentacao/diagrama-navegacao-fenda.svg) — principais percursos de navegação da aplicação.
- [`arquitetura-hospedagem-fenda.svg`](documentacao/arquitetura-hospedagem-fenda.svg) — fluxo lógico entre navegador, aplicação, banco de dados e serviços externos identificados.

Os arquivos SVG são vetoriais e podem ser ampliados sem a perda de qualidade típica de imagens rasterizadas. Os arquivos `.drawio` podem ser abertos e editados em [diagrams.net](https://app.diagrams.net/).

## Testes exploratórios de interface

As capturas de tela registram cenários de responsividade verificados por meio da emulação de dispositivos nas ferramentas de desenvolvimento do navegador. Os testes foram feitos em emulação no computador, não em todos os aparelhos físicos correspondentes. Eles não equivalem a testes automatizados, auditoria de segurança, avaliação formal de acessibilidade, teste de carga ou validação exaustiva da aplicação.

## Estado do projeto

A Fenda permanece em desenvolvimento. A documentação acadêmica descreve o estado observado durante sua elaboração e distingue funcionalidades implementadas, parciais e planejadas. A existência de uma tabela no esquema, de um diagrama ou de uma tela não comprova, isoladamente, que um fluxo funcional esteja concluído ou disponível em produção.

## Autoria

**Leonardo Florindo Alves Rodrigues**  
Curso de Análise e Desenvolvimento de Sistemas (ADS)  
Centro Universitário de Votuporanga — UNIFEV  
2026

## Licença e escopo

Os materiais originais deste repositório estão disponibilizados sob a licença MIT indicada em [`LICENSE`](LICENSE). Essa licença se aplica somente aos materiais deste repositório e **não** altera nem concede direitos sobre o código-fonte da aplicação no repositório [Twester77/components-spotted-xamp](https://github.com/Twester77/components-spotted-xamp), que possui termos próprios de direitos autorais.

Logotipos, marcas, bibliotecas, imagens ou outros materiais de terceiros eventualmente incluídos continuam sujeitos às licenças e aos direitos de seus respectivos titulares; a licença deste repositório não amplia essas permissões.
