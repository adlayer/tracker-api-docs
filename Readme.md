# Adlayer Tracker API

A Adlayer Tracker API permite que se faça a contabilizações de eventos, que estarão posteriormente disponíveis na sessão de relatórios em sua conta Adlayer.

Aponte suas requisições para a url: http://tracker.adlayerapp.com

Se você deseja fazer uma integração simples com o Adlayer recomendamos nossa [Javascript API](https://github.com/adlayer/javascript-api) que possui um modo muito simples de lidar com nossa API HTTP.

## API

### Parametros

Os seguintes parametros podem ser usados para tracker clique e impressões.

| Parameter   | Description                        |
|--------------------------------------------------|
| campaign_id | Id único da campanha               |
| space_id    | Id do espaço onde o evento ocorreu |
| site_id     | Id do site que o evento ocorreu    |
| page_url    | Url em que o evento ocorreu        |
| date        | Data UTC formatad como ISO 8601    |
| browser     | Nome do navegador                  |


