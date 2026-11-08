# NOVA DETAIL V5 — CINEMATIC LUXURY EXPERIENCE
**Estado:** plano aprovado para preparação; implementação V5 ainda NÃO iniciada.
**Data:** 08-11-2026
**Projeto:** [NOVA DETAIL V4 (publicado)](https://kreamkilah.github.io/nova-detail-demo-2026/)
**Repositorio:** `KreamKilah/nova-detail-demo-2026`
**Nota:** website demonstrativo para marca fictícia. Não representar como empresa real, portefólio de cliente real ou resultados reais.

## 1. North star

Passar de um **site premium estático com algumas animações** para uma **experiência cinematográfica, editorial e interativa**, com qualidade consistente em mobile e desktop, sem sacrificar legibilidade, acessibilidade ou desempenho.

A UX deve fazer sentido mesmo com JavaScript desligado / preferência por movimento reduzido. Todas as animações devem explicar, revelar, comparar ou conduzir. Não criar efeitos apenas por serem vistosos.

**Critério subjetivo:** o primeiro ecrã deve impressionar sem esconder o objetivo do site; o resto da página tem de manter o mesmo nível.

## 2. Diagnóstico da V4 (confirmado por leitura do código)

- One-page HTML/CSS/JS no GitHub Pages.
- Hero com imagem original `assets/nova-hero.webp` (local), iluminação dourada e controlo interativo de luz.
- Galeria em modal, comparação com filtros de luminosidade **simulada** (sem fotos de trabalhos reais), menu móvel, progresso ao scroll.
- 9 secções; aproximadamente 40 KB de HTML (não é avaliação Lighthouse).
- Cerca de 12 referências a URLs de imagens Pexels; direção fotográfica não está unificada.
- Não usa ainda GSAP, ScrollTrigger, Lenis ou React.
- Principal risco visual: peso e composição do hero em ecrã pequeno; parte do site fica bastante mais genérica que a primeira secção.
- Nenhuma medição de Core Web Vitals foi realizada — metas abaixo são **alvos, não resultados atuais**.

## 3. Art direction — “Obsidian / Champagne”

**Paleta**
- Deep obsidian `#080B0D` (canvas principal).
- Graphite `#111719` (painéis).
- Warm champagne `#D4B88B` (detalhes e highlights controlados).
- Ivory `#F3F0E9` (titulação).
- Dust grey `#9FA8A5` (secundário).

**Tipografia**
- Display: Barlow Condensed em grande escala; hierarquia forte e spacing editorial.
- Leitura: Manrope.
- Uma única aplicação opcional de serif itálica editorial para contraste; não misturar famílias sem propósito.

**Fotografia**
- Um universo visual: carro desportivo **sem marca**, grafite/obsidiana, studio preto, luzes verticais champagne, reflexos reais plausíveis, macro de acabamento.
- Conjunto inicial de 6 a 8 imagens com consistência de luz, distância focal e paleta; privilégios de geração própria e direito de uso adequado.
- O carro/salão nas imagens não deve ser apresentado como veículo/empresa/cliente real.
- Fotos dos resultados dos serviços devem ser reais e autorizadas antes de fazer alegações de “antes/depois”. Até aí, identificar qualquer comparação como simulação.
- Não inventar reviews, certificados, métricas, estrelas, prémios, preços ou localidades.

## 4. Storyboard e motion por secção

| Sequência | Secção | Composição | Movimento V5 | Interação/CTA |
|---|---|---|---|---|
| 00 | Intro / Preloader | Fundo obsidiana + traço de luz com identidade NOVA | 0,6–1,0s apenas no primeiro acesso e só se necessário; não bloquear site por JS | Skip e redução de movimento respeitados |
| 01 | Hero | Carro dominante à direita, copy editável à esquerda; imagem local original + nova versão mobile crop | Máscara de tipografia em 2 passos, glow que atravessa carro, profundidade suave; sem vídeo pesado por defeito | Explorar serviços / ver experiência; controlo de iluminação mantido |
| 02 | Manifesto | Foto macro + headline editorial | Scroll progress que revela a imagem por recorte e deslocação curta (sem esconder texto) | Scroll normal sempre disponível |
| 03 | Serviços (3) | Imagens coerentes interior / paint / protection | Cards com transição de máscara, micro-parallax controlado e pequenos detalhes luminosos | Cards com explicação e serviço visível sem hover |
| 04 | Signature experience | Cena de carro: exterior → detalhe → acabamento | Scroll storytelling em 2 ou 3 quadros, pin só em desktop estável; mobile usa cortes simples sem secção presa | Mostrar processo de forma clara |
| 05 | Antes/Depois | Comparador editorial grande | Slider tátil/teclado e reveal limpo | **Simulação declarada** até existir par real autorizado |
| 06 | Gallery | Grid editorial grande, imagens próprias e detalhes | Reveal por máscara + hover discreto; modal V4 reaproveitado, setas e Escape | Galeria fullscreen acessível |
| 07 | Processo/Confiança | Três passos com detalhe | Sequência de linha animada, não números fabricados | Contextualizar serviços |
| 08 | Final / CTA | Novo enquadramento do mesmo universo do hero | Cinematic light fade e texto revelado | CTA não-falso: descobrir conceito, sem agendamento real |
| 09 | Footer | Identidade discreta, disclaimer e origem de imagens | Nada ou transições mínimas | Links funcionais |

## 5. Plano de implementação técnica

**Arquitetura**
- Manter HTML/CSS/JS para a V5 inicial, porque o projeto é uma one-page estática, o overhead do React não justifica uma migração imediata.
- Código separado por CSS variables, secções e módulos JS; duplicação de styles e scripts deve ser reduzida.
- GSAP + ScrollTrigger para timeline e animação por scroll; versão fixada e carregamento progressivo; fallback CSS se CDN falhar.
- Lenis **opcional e só depois de testes**: pode prejudicar navegação em previews/iframes e tornar touch menos natural. Em mobile usar inicialmente scroll nativo.
- Todos os movimentos baseados sobretudo em transform/opacity; evitar grandes filtros animados e relayouts em cada frame.
- Image assets WebP/AVIF locais e `srcset/sizes`; `fetchpriority=high` na hero; lazy-load nas imagens fora do ecrã; evitar poster de grandes dimensões via terceiros.
- `prefers-reduced-motion` respeitado: remover parallax, preloader longo, pin, scroll smoothing; garantir que nada fica invisível sem JS.
- Sem autoplay de som, sem vídeos pesados ou 3D/WebGL no mobile por defeito.
- Subpastas recomendadas: `assets/images/`, `assets/video/` (se aprovado), `css/`, `js/`. Fonte completa controlada por Git.

**Experiências interativas**
- Navbar e estado ativo acessíveis.
- Before/After deve funcionar por rato, toque e teclado; percentagem conhecida.
- Gallery V4 deve manter teclado, Escape e foco restaurado ao fechar modal.
- 3D verdadeiro só se for claramente melhor que o compromisso imagem + motion e depois de medir performance.

## 6. Orçamento

- **0 € adicionais antes de haver uma razão concreta**. Orçamento do desafio de 50 € preservado.
- Usar GitHub para código e assets de demonstração; não vender hosting no GitHub Pages como se fosse um serviço comercial de produção.
- Gerar algumas imagens com os créditos existentes somente quando houver prompts definidos e necessidade; não gastar recursos cegamente.
- Evitar plugins/subscrições sem retorno demonstrável.

## 7. Metas de qualidade / critérios de aceitação

| Categoria | Gate para V5 |
|---|---|
| Conteúdo | Todas as secções legíveis com ou sem JS; disclaimers de marca fictícia preservados |
| Responsivo | Testar larguras 360, 390, 430, 768, 1024 e 1440 px; sem overflow nem elementos cortados |
| Mobile hero | Carro visível em composição, headline legível e dois CTAs claramente utilizáveis no primeiro ecrã |
| Animações | Sem bloquear scroll e sem salto visual ao entrar/sair; 60 fps alvo no desktop, degradação elegante no mobile |
| Acessibilidade | Navegação teclado, foco visível, alt-text, contraste adequado, reduced motion |
| Qualidade de imagem | Geradas/autorizadas, consistência de grading, compressão e nenhuma URL assinada temporária |
| Google Core Web Vitals | Alvos: LCP <= 2,5s; INP <= 200ms; CLS <= 0,1 no p75 (medir, não inventar) |
| Informação | Sem falsas avaliações, preços, qualificações, marcações ou resultados |
| QA | Testes desktop + mobile reais; estados abertos da galeria/slider/menu; comparação antes e depois das mudanças |
| Entrega | Versão em branch de trabalho primeiro, revisão visual, depois publicação principal |

## 8. Sequência de execução / gates

### P0 — Safe baseline (primeiro)
1. Guardar snapshot V4 e inventário de CSS/JS/URLs e eventuais regressões.
2. Resolver eventuais cortes de hero em mobile, marcar breakpoints e medir tamanho da imagem.
3. Criar tokens de cor e tipografia, alinhar hierarquias e spacing base.
4. Criar uma branch `nova-v5` ou outra área separada de ensaio. **Não alterar produção** antes de testar.

### P1 — Visual assets / hero (primeiro salto visível)
5. Criar 2 crops da nova hero e avaliar no telemóvel.
6. Definir 6–8 prompts de imagens consistentes e gerar amostras sob controlo de créditos.
7. Implementar hero V5 com GSAP timeline progressiva, respeitando movimento reduzido.
8. Fazer revisão a 390 e 1440 px.

### P2 — Storyboard cinematográfico (corpo do site)
9. Refazer secções Manifesto / Serviços / Process com fotos coerentes e efeitos por scroll.
10. Acrescentar signature experience em desktop; alternativa sem pin no mobile.
11. Harmonizar galeria e footer.

### P3 — Interações e verdade do conteúdo
12. Melhorar slider, mantendo linguagem clara sobre simulação.
13. Rever CTAs, navegação e mensagens demonstrativas; remover claims duvidosos.
14. Verificar foco, teclado, ALT e modais.

### P4 — QA e entrega
15. Fazer teste em múltiplas larguras e dispositivos reais; corrigir overflow, problemas de z-index e carga da imagem.
16. Medir Lighthouse + Core Web Vitals onde houver dados suficientes.
17. Comparar V4/V5 com screenshots, decidir se houve melhoria suficiente.
18. Publicar na branch principal apenas quando aprovado.

## 9. Ferramentas / fontes

- GSAP ScrollTrigger docs: https://gsap.com/docs/v3/Plugins/ScrollTrigger/
- Lenis oficial: https://github.com/darkroomengineering/lenis
- Métricas Core Web Vitals: https://developers.google.com/search/docs/appearance/core-web-vitals
- Site V4: https://kreamkilah.github.io/nova-detail-demo-2026/
- Portfolio: https://kreamkilah.github.io/krm-digital-showcase/

## 10. Definição de 'pronto'

Não basta “ter mais efeitos”. V5 só é concluído quando:
1) a primeira dobra impressiona, 2) o design é consistente até ao footer, 3) o mobile está impecável, 4) o site não fica pesado, e 5) conseguimos demonstrar isto objetivamente em comparação visual e testes funcionais.

**Estado do projeto na data deste documento: ROADMAP CRIADO; V5 NÃO IMPLEMENTADO.**
