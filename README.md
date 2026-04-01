# Documentação do Projeto: Investe Cajamar - Feira

## Visão Geral
Este projeto consiste em uma *Landing Page* única (`investe.html`) desenvolvida para a iniciativa "Investe Cajamar". O objetivo é apresentar Cajamar como um polo estratégico para investimentos, destacando sua localização, talentos, qualidade de vida e indicadores econômicos.

A página foi projetada para ser **autocontida** e **facilmente integrável** em plataformas como WordPress/Elementor, utilizando um namespace CSS específico para evitar conflitos de estilo.

## Estrutura do Arquivo (`investe.html`)

O arquivo contém todo o código necessário (HTML, CSS e JS), seguindo a estrutura:

1.  **Head**: Metadados SEO (Open Graph, Twitter, Schema.org), Favicons e blocos `<style>`.
2.  **Body**:
    -   Container Principal (`.investe-feira`): Envolve todo o conteúdo visível.
    -   **Seções**:
        -   `Header`: Navegação fixa com logo e links âncora.
        -   `Hero`: Destaque visual com título, subtítulo e CTAs.
        -   `Por que Cajamar`: Cards ilustrativos sobre os pilares da cidade.
        -   `Indicadores (KPIs)`: Números animados e gráficos de barra CSS.
        -   `Principais Setores`: Cards detalhando logística, indústria e serviços.
        -   `Institucional`: Informações sobre secretarias de apoio (Desenvolvimento, Trabalho, Turismo).
        -   `Galeria`: Slider de imagens (carrossel).
        -   `Acessos`: Informações logísticas sobre rodovias.
        -   `Contato`: CTA final para WhatsApp e E-mail.
    -   **Scripts**: Blocos `<script>` ao final do body para interatividade.

## Padrões de Código

### 1. CSS (Estilização)
*   **Namespace Isolado**: Todos os seletores CSS começam com `.investe-feira` para garantir que os estilos não vazem ou sejam afetados pelo CSS global do site hospedeiro.
*   **CSS Variables**: Uso extensivo de variáveis CSS (`--brand`, `--text`, `--shadow`, etc.) no topo do escopo para facilitar a personalização de cores e espaçamentos.
*   **Layout Moderno**: Utilização predominante de `CSS Grid` e `Flexbox` para alinhamentos e responsividade.
*   **Responsividade**: Media queries (`@media`) ajustam o número de colunas dos grids para Mobile (<640px), Tablet (<1024px) e Desktop.
*   **Reset Local**: Um reset suave (`box-sizing: border-box`) é aplicado apenas dentro do namespace.

### 2. JavaScript (Comportamento)
*   **Vanilla JS**: Todo o código é escrito em JavaScript puro, sem dependências externas (como jQuery).
*   **Escopo Fechado**: O código é encapsulado em **IIFEs** (Immediately Invoked Function Expressions) para não poluir o escopo global `window`.
*   **Funcionalidades**:
    *   **Smooth Scroll**: Rolagem suave para links internos.
    *   **Animações**:
        *   Contagem progressiva de números (KPIs) usando `requestAnimationFrame`.
        *   Animação de barras de progresso (CSS width).
        *   Uso de `IntersectionObserver` para disparar animações apenas quando o elemento entra na tela.
    *   **Slider**: Lógica simples de carrossel para a galeria de imagens.
    *   **UTM & Links**: Script para capturar parâmetros UTM da URL e repassá-los dinamicamente para os links de contato (WhatsApp/E-mail).
    *   **Chatbot**: Injeção dinâmica de um iframe (Araçá Bot) apenas em telas maiores que 768px.

### 3. HTML & SEO
*   **Semântica**: Uso de tags semânticas (`<header>`, `<section>`, `<article>`, `<nav>`, `<figure>`).
*   **Acessibilidade**: Atributos `aria-label`, `aria-labelledby` e `role` presentes em componentes interativos.
*   **Metadados**: Configuração completa de tags `<meta>` para redes sociais e JSON-LD para dados estruturados (Schema.org).

## Como Editar

1.  **Cores e Fontes**: Altere as variáveis dentro do bloco `:root` (ou `.investe-feira`) no início do CSS.
2.  **Imagens**: As imagens são referenciadas por URLs absolutas (`https://cajamar.sp.gov.br/...`). Para trocar, substitua o atributo `src`.
3.  **Conteúdo**: O texto está diretamente no HTML. Procure pelos IDs ou classes das seções para alterar textos.
4.  **Links de Contato**: Os números de telefone e e-mails base são definidos nas variáveis CSS (`--whatsapp-number`, `--email-contato`) e processados pelo JS.

## Instalação / Deploy
Como é um arquivo único, basta fazer o upload do `investe.html` para o servidor ou copiar seu conteúdo (HTML+CSS+JS) para um bloco de "HTML Personalizado" em um CMS.
