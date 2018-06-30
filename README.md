cfssl
=========

[![Travis-CI](https://travis-ci.org/deadc/deadcow.cfssl.svg?branch=master)](https://travis-ci.org/deadc/deadcow.cfssl)

CFSSL é o canivete suíço PKI/TLS da CloudFlare. É uma ferramenta de linha de comando e um servidor de API HTTP para assinar, verificar e agrupar certificados TLS.

Requerimentos
------------

Os certificados são gerados localmente, independente se o ansible é executado local ou remotamente.

Variaveis
--------------

Valores padroes de conbfiguraçao PKI

    cfssl_pki_common_name: Kubernetes
    cfssl_pki_country: GB
    cfssl_pki_state: London
    cfssl_pki_locality: London
    cfssl_pki_organisation: Kubernetes
    cfssl_pki_organisational_unit: CA

Lista de hosts a serem configurados no CSR server.

    cfssl_pki_hosts:
      - 192.168.52.12
      - 192.168.52.13
      - 192.168.52.14
      - 127.0.0.1
      - localhost

Dependencias
------------

Nenhuma

Playbook exemplo
----------------

    - hosts: all

      vars:
        cfssl_pki_hosts:
          - 192.168.0.10
          - 192.168.0.20
          - 192.168.0.30

      roles:
         - cfssl

Licença
-------

BSD/MIT

Informações sobre autor
------------------

Desenvolvido por Thiago Freitas (deadcow@archlinux.com.br) em 06/2018.
