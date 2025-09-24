# Visão de Produto

## Introdução

<p style="text-align: justify; text-indent: 2em;">Em um cenário de mercados financeiros cada vez mais dinâmicos e complexos, a tomada de decisão baseada apenas na análise humana se torna limitada. A velocidade com que preços, volumes de negociação e notícias mudam exige sistemas capazes de processar grandes quantidades de dados em tempo real e responder de forma precisa e consistente. Nesse contexto, a aplicação de técnicas de Machine Learning surge como uma solução estratégica para reduzir vieses humanos, acelerar análises e apoiar decisões mais eficazes.</p>

<p style="text-align: justify; text-indent: 2em;">Este projeto propõe o desenvolvimento de um Agente de Negociação Automatizada (Trading Bot), cujo objetivo é prever o comportamento futuro de ativos financeiros, como ações ou criptomoedas, e utilizar essas previsões para executar negociações de forma autônoma. Mais do que a simples construção de um modelo preditivo, o foco está na implementação de um sistema completo de aprendizado de máquina aplicado a séries temporais, integrando coleta de dados, previsão, simulação de negociações e avaliação de desempenho.</p>

## O Problema

<p style="text-align: justify; text-indent: 2em;">Com o intuito de compreender de maneira sistemática os fatores que contribuem para perdas financeiras e para o desperdício de oportunidades de lucro nas negociações, elaborou-se um Diagrama de Ishikawa (Fishbone Diagram), como é possível ver na Figura 1. Tal ferramenta permite estruturar visualmente as múltiplas causas do problema, distribuindo-as em categorias que evidenciam a complexidade e a interdependência entre variáveis humanas, tecnológicas, organizacionais e de mercado.</p>

<p style="text-align: justify; text-indent: 2em;">Entre as principais dimensões identificadas, destacam-se:</p>

* **Fatores Humanos e Cognitivos**: vieses psicológicos, excesso de confiança e decisões influenciadas por emoções comprometem a racionalidade do processo decisório.
* **Complexidade e Qualidade dos Dados**: o grande volume de informações, associado à heterogeneidade e à presença de ruídos, dificulta a extração de padrões relevantes para subsidiar estratégias de negociação.
* **Estratégias de Negociação Limitadas**: a adoção de regras fixas, a ausência de mecanismos de atualização contínua e a utilização de modelos defasados reduzem a capacidade adaptativa frente às dinâmicas de mercado.
* **Condições de Mercado**: a volatilidade elevada e a assimetria de informação colocam os investidores em situação de desvantagem, sobretudo quando comparados a agentes institucionais de maior porte.
* **Limitações Tecnológicas**: falhas de integração entre sistemas, ausência de automação e dependência de infraestrutura terceirizada contribuem para atrasos, inconsistências e riscos operacionais.
* **Processos e Organização**: a inexistência de metodologias robustas, de padronização de procedimentos e de mecanismos de governança prejudica a consistência das práticas de negociação.
* **Restrições de Tempo e Escalabilidade**: a necessidade de decisões em escalas de tempo reduzidas (milissegundos) e a impossibilidade de monitoramento ininterrupto do mercado evidenciam a ineficiência das estratégias manuais.
* **Gestão de Risco Deficiente**: a ausência de controles adequados de exposição, o uso inadequado de instrumentos de proteção (como stop-loss) e a falta de equilíbrio entre risco e retorno ampliam a probabilidade de perdas significativas.

<p style="text-align: justify; text-indent: 2em;">A partir desse mapeamento, observa-se que as perdas financeiras não são decorrentes exclusivamente da dificuldade de prever preços, mas resultam de um conjunto multifatorial de limitações, distribuídas em diferentes esferas de influência.</p>

<div align="center">
    <img src="https://raw.githubusercontent.com/unb-Sistemas-de-Machine-learning/grupo06-trading-bot/refs/heads/gh-pages/docs/images/fishbone.png" alt="Diagrama de Ishikawa">
    <p style="text-align: center"><b>Figura 1:</b> Diagrama de Ishikawa</p>
</div>


### Público Afetado e Impactos do Problema

<p style="text-align: justify; text-indent: 2em;">O público principal afetado pelo problema de identificado compreende investidores individuais que dependem da análise manual para tomar decisões de compra e venda. Esses agentes de mercado, muitas vezes, não possuem acesso a recursos tecnológicos avançados nem a equipes especializadas de análise, ficando vulneráveis às rápidas variações de preços, à volatilidade elevada e à assimetria de informações presentes nos mercados financeiros modernos.</p> 
<p style="text-align: justify; text-indent: 2em;">A consequência direta desse cenário é a exposição a decisões baseadas em informações incompletas ou interpretadas de maneira subjetiva, o que potencializa a ocorrência de vieses cognitivos, excesso de confiança e reações impulsivas diante de flutuações de mercado. Além disso, a incapacidade de processar grandes volumes de dados em tempo real reduz a eficiência na identificação de oportunidades de lucro e aumenta a probabilidade de perdas financeiras significativas.</p> 
<p style="text-align: justify; text-indent: 2em;">Investidores afetados enfrentam, portanto, não apenas prejuízos econômicos, mas também impactos psicológicos, como frustração e insegurança, que podem comprometer a consistência e a racionalidade das estratégias de negociação. O problema se agrava pela limitação em escalar análises, monitorar o mercado de forma contínua e aplicar controles de risco adequados, criando um ciclo de vulnerabilidade frente a agentes institucionais que dispõem de sistemas automatizados mais robustos.</p>

## O Produto

<p style="text-align: justify; text-indent: 2em;">O produto proposto neste projeto é um Agente de Negociação Automatizada baseado em Machine Learning, concebido para atuar de forma autônoma no mercado financeiro. Diferente de soluções que dependem exclusivamente de regras fixas ou da intervenção humana, o sistema integra coleta contínua de dados, previsão de séries temporais e execução automatizada de ordens, oferecendo um fluxo de decisão completo e consistente.</p> 
<p style="text-align: justify; text-indent: 2em;">O Trading Bot é estruturado em três módulos principais que trabalham de maneira integrada:</p>

* Pipeline de Dados: responsável por coletar, normalizar e armazenar informações de mercado em tempo real, provenientes de múltiplas fontes, como preços, volumes de negociação e notícias financeiras. Este módulo garante que o sistema tenha acesso a dados confiáveis e atualizados, fundamentais para a precisão das previsões e a tomada de decisão automatizada.
* Cérebro do Bot (Modelo de Machine Learning): constitui o núcleo preditivo do sistema, utilizando técnicas de aprendizado de máquina, como ARIMA ou redes neurais recorrentes (LSTM), para analisar séries temporais e gerar previsões sobre o comportamento futuro dos ativos. Este módulo visa identificar padrões não triviais nos dados e transformar essa análise em sinais de negociação confiáveis.
* Motor de Execução: interpreta os sinais gerados pelo modelo preditivo e executa ordens de compra e venda em um ambiente de simulação (backtesting). Além de traduzir previsões em ações concretas, este módulo monitora o desempenho do sistema, permitindo ajustes e otimizações contínuas, garantindo que a estratégia seja robusta e adaptável a diferentes condições de mercado.

#### Por que a utilização de Inteligência Artifical é uma solução correta para esse problema?

<p style="text-align: justify; text-indent: 2em;">O desafio central não é apenas executar ordens, mas prever o comportamento futuro dos preços em um ambiente altamente volátil. Os algoritmos de previsão temporal oferecem uma abordagem superior em relação a métodos manuais ou regras fixas, pois conseguem aprender padrões históricos, identificar sazonalidades, tendências e correlações complexas que não são visíveis à análise humana. Em mercados financeiros, onde segundos fazem diferença, a IA permite decisões mais rápidas, baseadas em previsões estatisticamente fundamentadas.</p>

#### Qual o valor único que a Inteligência Artifical pode oferecer em comparação com soluções tradicionais?

<p style="text-align: justify; text-indent: 2em;">O diferencial da Inteligência Artificial, aplicada via algoritmos de previsão temporal, está em:</p>

- Antecipar movimentos de mercado em vez de apenas reagir a eles.
- Detectar padrões não lineares e relações dinâmicas entre preços, volumes e indicadores.
- Adaptar-se continuamente a mudanças de regime do mercado, re-treinando modelos e refinando previsões com novos dados.
- Fornecer previsões com níveis de confiança e métricas de erro (como MAE ou RMSE), oferecendo transparência e mensurabilidade de risco.

## Declaração de Posição de Produto

<p style="text-align: justify; text-indent: 2em;">A Declaração de Posição do Produto é um resumo estratégico que define claramente o público-alvo, o produto, seus benefícios e diferenciais frente às alternativas existentes. Ela serve como guia para a comunicação do produto, garantindo que todos os envolvidos no projeto compreendam seu propósito, valor e aplicação.</p>

<html>
    <div align="center">
        <table>
            <tr>
                <th>Elemento</th>
                <th>Descrição</th>
            </tr>
            <tr>
                <td>Público-alvo</td>
                <td>Investidores individuais e pequenos investidores que enfrentam dificuldades em acompanhar a velocidade e complexidade dos mercados financeiros.</td>
            </tr>
            <tr>
                <td>Produto</td>
                <td>Agente de Negociação Automatizada (Trading Bot) baseado em Machine Learning.</td>
            </tr>
            <tr>
                <td>Proposta de Valor</td>
                <td>Coleta dados de mercado em tempo real, realiza previsões de séries temporais e executa ordens de compra e venda de forma automatizada.</td>
            </tr>
            <tr>
                <td>Diferencial</td>
                <td>Reduz vieses humanos, reage rapidamente a mudanças de mercado e oferece controle consistente sobre riscos e oportunidades.</td>
            </tr>
            <tr>
                <td>Alternativa à</td>
                <td>Estratégias manuais ou sistemas baseados em regras fixas.</td>
            </tr>
        </table>
    </div>
</html>


----

#### Bibliografia

> Explorando as Emoções e os Vieses Comportamentais no Contexto Financeiro. Disponível em: <https://www.gov.br/investidor/pt-br/explorando-as-emocoes-e-os-vieses-comportamentais-no-contexto-financeiro>. Acesso em: 24 set. 2025. 

> Como a Volatilidade do Mercado Financeiro Pode Afetar Suas Economias e Como se Preparar. Disponível em: <https://www.convexainvestimentos.com/volatilidade-mercado-financeiro-afeta-economias/?utm_source=chatgpt.com>. Acesso em: 24 set. 2025. 

----

<div align="center">

<p style="text-align: center"><b>Histórico de Revisão</b></p>

|Data|Versão|Descrição|Autores|
|-|-|-|-|
|23/09/2025|0.1|Adição da documentação inicial|Júlia Yoshida, Jefferson Sena e Tiago Albuquerque|

</div>
