# Adlayer Tracker API

A Adlayer Tracker API permite que se faça a contabilizações de eventos, que estarão posteriormente disponíveis na sessão de relatórios em sua conta Adlayer.

Se você deseja fazer uma integração simples com o Adlayer recomendamos nossa [Javascript API](https://github.com/adlayer/javascript-api) que possui um modo muito simples de lidar com nossa API HTTP.

# Requsições

Aponte suas requisições para a url: http://tracker.adlayerapp.com

## Pixel Tracking
Atualmente o único método de requisição aceito é o "Pixel Tracking", esta técnica amplamente utilizada por web analytics e ad servers permite que a contabilização de eventos seja efetuada através da transferência de uma imagem de "1x1 pixel".

Portanto qualquer requisição efetuada com o método GET nesta API retornará uma imagem .gif como resposta.

Quando um evento não pode ser salvo o servidor enviará o Header "warning" informando que não pode efetuar a operação.

Veja na próxima sessão deste documento (API Endpoints), para ver exemplos de requisições e quais parâmetros são aceitos.


## API Endpoints

### Impressões
```http
GET /impressions/:ad_id HTTP/1.1
Host: tracker.adlayerapp.com
```

### Clicks
```http
GET /clicks/:ad_id HTTP/1.1
Host: tracker.adlayerapp.com
```

### Parâmetros

Os seguintes parâmetros podem ser usados para tracker clique e impressões.

| Parameter   | Description                        |
|-------------|------------------------------------|
| campaign_id | Id único da campanha               |
| space_id    | Id do espaço onde o evento ocorreu |
| site_id     | Id do site que o evento ocorreu    |
| page_url    | Url em que o evento ocorreu        |
| date        | Data UTC formatad como ISO 8601    |
| browser     | Nome do navegador                  |

## Exemplos

### Trackando a impressão de uma peça

```http
GET /clicks/:ad_id?campaign_id=5091c7a4496c4f318d490117ee58a4a5& space_id=96c4f7ee58a4a55091c7a44318d49011 HTTP/1.1
Host: tracker.adlayerapp.com
```

### Trackando o click de uma peça

```http
GET /impressions/:ad_id?campaign_id=5091c7a4496c4f318d490117ee58a4a5& space_id=96c4f7ee58a4a55091c7a44318d49011 HTTP/1.1
Host: tracker.adlayerapp.com
```