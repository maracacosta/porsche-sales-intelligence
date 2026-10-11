# Porsche Sales Intelligence

Dashboard executiva de vendas de veículos Porsche, desenvolvida em HTML, CSS e JavaScript, com gráficos interativos em Chart.js.

> **Nota sobre dados:** esta publicação usa uma cópia demonstrativa com nomes de clientes e vendedores substituídos por identificadores fictícios. Antes de publicar, valide também se os valores comerciais, datas, cidades e demais campos podem ser compartilhados publicamente. Não publique a planilha original.

## Dashboard publicada

Depois de ativar o GitHub Pages, substitua este texto pelo endereço publicado:

- **GitHub Pages:** `https://maracacosta.github.io/porsche-sales-intelligence/`
- **Repositório:** `https://github.com/maracacosta/porsche-sales-intelligence`

## Perguntas de negócio e justificativa

1. **Quais modelos vendem mais por cidade?** Ajuda a identificar diferenças de preferência por praça e apoiar decisões de mix, estoque e ações comerciais.
2. **Quais vendedores geram mais vendas?** Permite comparar volume por responsável comercial e levantar oportunidades de treinamento e replicação de boas práticas.
3. **Qual é o faturamento por ano?** Mostra a dimensão financeira anual e facilita comparar períodos.
4. **Como as vendas evoluem mês a mês e quais meses concentram mais vendas?** Evidencia sazonalidade, tendências e períodos de maior demanda.
5. **Qual é a referência de vendas para o mês corrente e os meses seguintes?** Dá uma visão inicial para planejamento de metas. A projeção implementada é uma referência simples pela média dos meses recentes, não uma previsão estatística validada.
6. **Como ano do modelo, forma de pagamento e período afetam o recorte?** Os filtros permitem aprofundar a leitura sem perder a visão executiva.

## Prompt usado para gerar a primeira versão

> Usando o recurso do canvas, renderize uma dashboard em HTML ao lado. Filtros: modelo da Porsche, cidade, data da venda, ano do modelo e forma de pagamento. Colunas: Id, Dia Venda, customer_name, Porsche Model, Model Year, Sales Price, Vehicle Mileage, Pay Method, State, salesperson e Delivery Status. A dashboard deve responder: quais os modelos mais vendidos por cidade e por vendedor; qual o faturamento por ano; qual a evolução mensal; quais os meses de maior venda; e, com base no histórico, qual a projeção de vendas do mês e dos próximos meses. Para UX/UI, use como referência visual o site Porsche Brasil (https://www.porsche.com/brazil/pt/), com uma apresentação arrojada e refinada para diretoria.

## O que mudou até a versão final

- Organização da experiência em visão executiva, indicadores, gráficos temporais, rankings, projeção e tabela detalhada.
- Inclusão de filtros combináveis e de ação para limpar filtros.
- Criação de ranking de modelos na cidade com maior volume dentro do recorte e ranking de vendedores.
- Inclusão de alertas de qualidade da base e explicação da limitação do forecast.
- Ajuste de responsividade para diferentes larguras de tela.
- Para a cópia pública, substituição dos nomes de clientes e vendedores por identificadores fictícios.
- Os valores permanecem em USD, conforme a base de origem, sem conversão cambial. Isso precisa ficar explícito ao interpretar os indicadores.

## Tratamento da base antes de usar a IA

A planilha original continha 100 registros e campos de vendas. A inspeção inicial indicou 78 registros com data interpretável e 22 sem data válida na versão usada para a dashboard. A análise temporal usa apenas registros com data interpretável. Também foram observadas datas futuras, que precisam ser verificadas antes de qualquer uso executivo do forecast.

Tratamentos realizados para a cópia de publicação:

- Seleção dos campos usados pela visualização.
- Conversão dos registros para uma estrutura JSON incorporada ao HTML.
- Substituição de `customer_name` por `Cliente 001`, `Cliente 002` etc.
- Substituição de `salesperson` por identificadores fictícios (`Vendedor 01` etc.).
- Manutenção dos valores em USD, sem conversão cambial.
- Não inclusão da planilha original no repositório público.

**Importante:** a anonimização de nomes não garante, por si só, que dados comerciais possam ser divulgados. Confirme autorização para publicar os valores, datas, cidades, estados, modelos e demais atributos. Se não houver autorização, substitua também os dados transacionais por uma base sintética antes de publicar.

## Ferramentas utilizadas

- **ChatGPT:** apoio na estruturação das perguntas de negócio, criação do código HTML/CSS/JavaScript e documentação.
- **Canvas:** não foi utilizado como ambiente de edição/publicação final nesta versão; o artefato entregue é um arquivo HTML autônomo.
- **Agente com skill:** não foi utilizado.

A biblioteca Chart.js é carregada por CDN, então os gráficos exigem conexão à internet.

## Como publicar no GitHub Pages

1. Crie um repositório público chamado `porsche-sales-intelligence` na sua conta GitHub.
2. Envie `index.html` e `README.md` para a raiz do repositório.
3. Abra **Settings → Pages**.
4. Em **Build and deployment**, selecione **Deploy from a branch**.
5. Escolha a branch `main` e a pasta `/(root)`; salve.
6. Aguarde a publicação e teste o endereço exibido na área Pages.
7. Substitua os links de exemplo no início deste README pelos endereços reais.
8. Faça uma captura de tela da dashboard aberta e de pelo menos um filtro aplicado; adicione a imagem ao repositório (por exemplo, em `docs/dashboard-filtro.png`) e referencie-a neste README.

## Checklist antes de submeter

- [ ] `index.html` abre localmente e os filtros atualizam os gráficos e a tabela.
- [ ] GitHub Pages está ativo e o endereço público funciona.
- [ ] O repositório é público e pertence à minha conta.
- [ ] O link submetido é o do repositório GitHub.
- [ ] Todos os arquivos citados no README existem.
- [ ] Nenhum dado pessoal ou comercial confidencial foi publicado.
- [ ] Incluí uma captura de tela da dashboard e um exemplo de filtro aplicado.
- [ ] Validei datas futuras, datas inválidas e moeda antes de interpretar o forecast.

## Limitações conhecidas

- O forecast usa uma média simples dos meses recentes e deve ser tratado como referência exploratória.
- Meses sem registro podem significar ausência de vendas ou lacuna na base; a dashboard não consegue distinguir essas situações automaticamente.
- A dashboard é uma demonstração analítica, não um sistema oficial de vendas.
