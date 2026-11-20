set(srcs "simple_video_server_example.c")
set(html_files "../frontend/gzipped/index.html.gz"
               "../frontend/gzipped/loading.jpg.gz"
               "../frontend/gzipped/favicon.ico.gz"
               "../frontend/gzipped/assets/index.js.gz"
               "../frontend/gzipped/assets/index.css.gz")

idf_component_register(SRCS "${srcs}"
                       PRIV_INCLUDE_DIRS .
                       EMBED_TXTFILES ${html_files}
                       PRIV_REQUIRES
                       	    esp_eth
                	        esp_netif
                	        esp_event
	                        esp_timer
                            esp_http_server
                            nvs_flash
                            lwip
                            espressif__ethernet_init
                            espressif__mdns
                            espressif__cjson
                            protocol_examples_common
                            example_video_common)
