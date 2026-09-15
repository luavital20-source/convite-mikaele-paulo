# Convite de casamento — Paulo & Mikaele

Convite digital (site de uma página) para o casamento de **Paulo e Mikaele**,
em **14 de novembro de 2026**, na **Chácara Encanto das Anas**, em Fortaleza — CE.

É um site estático: basta abrir o `index.html` ou publicar a pasta em qualquer
hospedagem (Vercel, Netlify, GitHub Pages). Não precisa de servidor.

---

## ✅ O que já está pronto

- Capa com o **monograma da identidade visual** e a data
- Foto do casal na abertura
- Frase de Van Gogh: *“O amor é algo eterno. O aspecto pode mudar, mas não a essência.”*
- Data, horário (15h) e local, com botão **Ver no mapa** (cerimônia e recepção no mesmo endereço)
- Foto do local (aquarela da cerimônia)
- Contagem regressiva
- **Dress code** (social fino, evitar branco, roupas leves e salto baixo ou rasteira) + paleta da decoração
- **Manual do convidado — Avisos importantes** (5 avisos, incluindo o aviso aos papais)
- **Nossa música** tocando pelo YouTube (o link enviado pelos noivos)
- Paleta e tipografia seguindo a identidade visual: marrom `#785243`, terracota `#B95F45`,
  amarelo `#FBCB72` e amêndoa `#EED9C4`

---

## 📸 1. Imagens

Todas já estão no lugar, dentro de `img/`:

| Arquivo               | Onde aparece                                    |
|-----------------------|-------------------------------------------------|
| `casal.jpeg`          | Foto de abertura (capa)                         |
| `chacara.jpeg`        | Foto do local, na seção da cerimônia            |
| `monograma.jpeg`      | Arquivo original do monograma (identidade)      |
| `monograma.png`       | O mesmo monograma sem fundo — é este que o site usa |
| `textura.jpg`         | Textura de papel do fundo                       |

Para trocar qualquer uma, basta substituir o arquivo mantendo o mesmo nome.
Se trocar o `monograma.jpeg`, gere de novo o `monograma.png` sem fundo (ou me peça).

## ✍️ 2. Pagamentos e confirmação de presença

Tudo já configurado no bloco `CONFIG`, no início do `<script>` do `index.html`.

### Confirmação de presença
```js
whatsapp: '5585985345493',
```
O botão da seção "Você vem?" abre o WhatsApp com a mensagem já escrita.

### Presentes — Pix
```js
pixChave:   '85cbe5d2-801c-4e18-80de-b8f43a861338',   // chave aleatória
pixTitular: 'Mikaele dos Santos',
pixBanco:   'InfinitePay',
pixCidade:  'Fortaleza',
```
O botão **Pix** de cada cota abre um pop-up com o código **copia e cola** já com
o valor daquela cota. Funciona sem servidor.

### Presentes — Cartão (InfinitePay)
```js
infinitepayHandle: 'mikaele-santos-o49',   // a InfiniteTag, sem o "$"
```
O botão **Cartão** chama `https://api.checkout.infinitepay.io/links`, que cria o
link de pagamento com o valor da cota e leva o convidado direto para o checkout.
Depois de pagar, ele volta para o convite com `?presente=ok` e vê um "Obrigado!".

> ⚠️ **Exige "Checkout externo / integrado" ligado** na conta InfinitePay.
> Sem isso a API recusa a chamada. Se o botão der erro, o aviso na tela mostra a
> resposta da InfinitePay e a InfiniteTag usada — é por aí que se descobre o motivo.
>
> Para desligar o cartão e deixar só o Pix, basta apagar o valor de
> `infinitepayHandle`.

As **fotos das 20 cotas já estão no lugar**, em `img/presentes/01.jpg` … `20.jpg`.
O `LEIA-ME.md` de lá lista qual número é qual presente. Para trocar alguma, é só
substituir o arquivo mantendo o número — a extensão tanto faz (`.jpg`, `.jpeg`,
`.png`, `.webp`). Card sem foto mostra um fundo da paleta, nada quebra.

---

## 🎵 3. Música

Já está configurada com o vídeo do YouTube enviado:

```js
youtubeId: 'LavVjIoGDw8',
```

A música começa quando o convidado toca na capa e pode ser pausada no botão
**Nossa música**. Se preferir um arquivo local em vez do YouTube, coloque o
`musica.mp3` na raiz do projeto e preencha:

```js
musicaArquivo: 'musica.mp3',
```

---

## 🔤 4. Fonte do nome do casal (Moontime)

A identidade visual usa a fonte **Moontime**, que não existe no Google Fonts.
O site usa hoje a **Sacramento**, o substituto mais parecido.

Para usar a Moontime de verdade, é só colocar o arquivo da fonte em:

```
fonts/Moontime.woff2      (ou fonts/Moontime.ttf)
```

Ela é aplicada automaticamente no monograma e nos títulos — sem mexer em nada.

---

## 🔖 Monograma

O site usa o monograma da identidade visual de vocês (`img/monograma.png`),
que é o `monograma.jpeg` com o fundo removido para assentar sobre a textura
de papel. Ele aparece na capa, na abertura e no rodapé.

## 🎨 Paleta

| Cor        | Hex       |
|------------|-----------|
| Marrom     | `#785243` |
| Terracota  | `#B95F45` |
| Amarelo    | `#FBCB72` |
| Amêndoa    | `#EED9C4` |
