API Automação-IOT
-----------------

A Automaççao-IOT utiliza um conjunto de rotinas padronizadas de programação denominado de API_ que serve de acesso para a  plataforma IOT baseado na WEB. Através da API que estabelecemos comunicação de entrada e/ou saída com os Dispositivos e/ou Recursos.


.. _API: https://api-automacaoiot.readthedocs.io/pt_BR/latest/

.. Outras Plaformas_:

Outras Plaformas
~~~~~~~~~~~~~~~~

A API_ da Automação_IOT, possibilita a conexão de outras plataformas a base de dados IOT. Vamos implementar o exemplo utilizado no SDK do ESP8266, de forma genérica para ser aplicado ao seu projeto em outras plataformas.

Get Device
++++++++++

Obtém informações sobre um determinado Dispositivo. Este EndPoint retorna dados informacionais do Dispositivo, tal como id, dono, nome e descrição do dispositivo

.. code-block:: JSON

    GET api/device/{PUBLIC_KEY}

**Implementação**

.. code-block:: JSON

    GET api/device/B07CFA0A9204228A30C68FB346C407E7  HTTP/1.1  
    Authorization: Bearer B8CE671CFE226CC190D5478E8E5A3CD7FB59D87F872278E59E4E6847B5E4B2F1  
    Host: https://automacao-iot.com.br/api

**Resposta**

.. code-block:: JSON

    {
	    "success": true,
	    "payload": {
		    "id_device": 12,
		    "id_user": 12,
		    "name": "ESP8266",
		    "icon_name": "fa-microchip",
		    "description": "ESP8266",
		    "ip": "10.1.1.11",
		    "timezone": "America\/Sao_Paulo",
		    "latitude": "-35.2837000",
		    "longitude": "-47.5343000",
		    "public_key": "B07CFA0A9204228A30C68FB346C407E7",
		    "api_requests_usage": 30653,
		    "api_network_usage": 4060992,
		    "api_network_income_usage": 4060875,
		    "api_network_outgoing_usage": 117,
		    "lifetime": 15,
		    "lifetime_updated_at": "2018-06-05 17:30:46",
		    "created_at": "2018-06-04 19:09:39",
		    "updated_at": "2018-06-04 19:09:39",
		    "private": 0,
		    "active": 1,
		    "is_alive": false,
		    "is_dead": true,
		    "last_sys_call": null
	    },
	    "message": ""
    }


Get Resource Last Feeds
+++++++++++++++++++++++

Recupera o último Registro de Feeds do Recurso.

.. code-block:: JSON

    GET/api/device/{PUBLIC_KEY}/resource/{ID_RESOURCE}/feeds/last

**Implementação**

.. code-block:: JSON

    GET api/device/B07CFA0A9204228A30C68FB346C407E7/resource/6/feeds/last  HTTP/1.1  
    Authorization: Bearer B8CE671CFE226CC190D5478E8E5A3CD7FB59D87F872278E59E4E6847B5E4B2F1
    Host: https://automacao-iot.com.br/api


**Resposta**

.. code-block:: JSON

    {
	    "success": true,
	    "payload": {
		    "id_resource_feed": 14603,
		    "id_resource": 6,
		    "raw_data": "0",
		    "created_at": "2018-06-05 17:13:06"
	    },
	    "message": ""
    }