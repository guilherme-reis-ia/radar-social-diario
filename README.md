# Radar Social Diário

Painel com as atualizações de TikTok, Instagram e Facebook que importam para quem trabalha com marketing e social media no Brasil: novos recursos, mudanças de algoritmo, anúncios e monetização, políticas, ferramentas para criadores e comércio.

Cada notícia traz plataforma, categoria, impacto (alto, médio ou baixo), um resumo curto, "por que importa" e o link da fonte. Itens em teste ou ainda não confirmados levam o selo "Em teste".

## Recursos

- Contadores do dia por plataforma e horário da última atualização
- Filtros combináveis por plataforma, categoria e impacto, mais busca por texto
- Histórico dos últimos 30 dias
- Cards que se expandem com o resumo completo e a fonte
- Modo claro e escuro, com layout para celular
- Caixa de inscrição na newsletter, com validação e consentimento (LGPD)

## Estrutura

```
index.html        página completa (HTML, CSS e JS, sem dependências de build)
data/radar.json   notícias e registro de cada execução
```

A página lê `data/radar.json` ao abrir. Para publicar um novo dia, acrescente os itens em `noticias` e um registro em `execucoes`, depois faça commit.

### Campos de uma notícia

| Campo | Exemplo |
|---|---|
| `id` | `2026-10-26-meta-adia-termos-comerciais` (data + slug) |
| `data` | `2026-10-26` (dia da execução) |
| `publicado_em` | `2026-10-23` (data da fonte) |
| `plataforma` | `TikTok`, `Instagram` ou `Facebook` |
| `categoria` | `Recursos`, `Algoritmo`, `Anúncios e monetização`, `Políticas e privacidade`, `Criadores` ou `Comércio` |
| `impacto` | `Alto`, `Médio` ou `Baixo` |
| `titulo`, `resumo`, `por_que_importa` | texto |
| `status` | `confirmado` ou `em teste` |
| `fonte_nome`, `fonte_url` | fonte efetivamente lida |

## Newsletter

O formulário vem em modo demonstração: ele valida o e-mail e o consentimento, mas não envia nada. Para receber inscrições de verdade, crie um formulário em um serviço como o [Formspree](https://formspree.io) e cole o endereço em `NEWSLETTER_ENDPOINT`, no fim de `index.html`.

## Rodar localmente

A página usa `fetch`, então precisa de um servidor (abrir o arquivo direto no navegador não carrega os dados). Por exemplo:

```bash
npx serve .
```

## Publicar no GitHub Pages

Em **Settings → Pages**, escolha **Deploy from a branch**, branch `main`, pasta `/ (root)`.
