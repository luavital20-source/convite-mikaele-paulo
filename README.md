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

## ✍️ 2. O que ainda falta preencher

Tudo fica no bloco `CONFIG`, logo no início do `<script>` do `index.html`.
Enquanto esses campos estiverem vazios, as seções correspondentes **ficam escondidas**
(o convite não fica “quebrado”).

### Confirmação de presença (RSVP)
```js
whatsapp: '',   // ex.: '5585999998888'  (DDI + DDD + número, só dígitos)
```
Preenchendo, aparece a seção **“Você vem?”** com o botão que abre o WhatsApp
já com a mensagem pronta.

### Lista de presentes — **falta a chave Pix**

As 20 cotas já estão cadastradas no `index.html`, com nome e valor. O que falta
é a chave Pix que vai receber:

```js
pixChave:   '',            // CPF, celular, e-mail ou chave aleatória
pixTitular: 'Paulo e Mikaele',
pixBanco:   '',            // opcional, só aparece no rodapé do pop-up
```

Enquanto a chave estiver vazia, os cards aparecem com nome e valor, mas **sem o
botão "Presentear"** — ninguém vê um botão que não funciona. Assim que preencher,
cada card ganha um Pix **copia e cola** com o valor daquela cota já embutido.

As **fotos das cotas** vão em `img/presentes/` — veja o `LEIA-ME.md` de lá com a
tabela de qual número é qual presente. A extensão tanto faz (`.jpg`, `.jpeg`,
`.png`, `.webp`); o que importa é o número com dois dígitos. Card sem foto mostra
um fundo da paleta — nada quebra.

Se preferir, dá para usar também um link de lista externa:

```js
listaLink: '',   // aparece como botão "Ver lista de presentes"
```

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
