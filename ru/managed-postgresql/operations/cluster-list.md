---
title: "Информация о кластерах в {{ mpg-short-name }}"
description: "Вы можете запросить детальную информацию о каждом созданном вами кластере {{ mpg-short-name }}. Чтобы получить список кластеров БД в каталоге, перейдите на страницу каталога и выберите сервис {{ mpg-name }}."
---

# Информация об имеющихся {{ PG }}-кластерах

Вы можете запросить детальную информацию о каждом созданном вами кластере {{ mpg-short-name }}.


## Получить список кластеров БД в каталоге {#list-clusters}

{% list tabs %}

- Консоль управления

  Перейдите на страницу каталога и выберите сервис **{{ mpg-name }}**.

- CLI

  {% include [cli-install](../../_includes/cli-install.md) %}

  {% include [default-catalogue](../../_includes/default-catalogue.md) %}

  Чтобы запросить список {{ PG }}-кластеров в каталоге по умолчанию, выполните команду:

  ```
  {{ yc-mdb-pg }} cluster list

  +----------------------+---------------+-----------------------------+--------+---------+
  |          ID          |     NAME      |         CREATED AT          | HEALTH | STATUS  |
  +----------------------+---------------+-----------------------------+--------+---------+
  | c9wlk4v14uq79r9cgcku | mypg          | 2018-11-02T10:04:14.645214Z | ALIVE  | RUNNING |
  | ...                                                                                   |
  +----------------------+---------------+-----------------------------+--------+---------+
  ```

- API

  Воспользуйтесь методом API [list](../api-ref/Cluster/list.md) и передайте идентификатор каталога в параметре `folderId` запроса.

{% endlist %}


## Получить детальную информацию о кластере {#get-cluster}

{% list tabs %}

- Консоль управления

  1. Перейдите на страницу каталога и выберите сервис **{{ mpg-name }}**.
  1. Нажмите на имя нужного кластера.

- CLI

  {% include [cli-install](../../_includes/cli-install.md) %}

  {% include [default-catalogue](../../_includes/default-catalogue.md) %}

  Чтобы получить информацию о {{ PG }}-кластере, выполните команду:

  ```
  {{ yc-mdb-pg }} cluster get <имя или идентификатор кластера>
  ```

  Идентификатор и имя кластера можно запросить со [списком кластеров в каталоге](#list-clusters).

- API

  Воспользуйтесь методом API [get](../api-ref/Cluster/get.md) и передайте в запросе идентификатор кластера в параметре `clusterId`.

  Идентификатор кластера можно получить со [списком кластеров в каталоге](cluster-list.md#list-clusters).

{% endlist %}

## Посмотреть список операций в кластере {#list-operations}

{% include [list-operations-about](../../_includes/mdb/list-operations-about.md) %}

{% list tabs %}

- Консоль управления

  1. Перейдите на страницу каталога и выберите сервис **{{ mpg-name }}**.
  1. Нажмите на имя нужного кластера.
  1. Перейдите на вкладку **Операции**.

- CLI

  {% include [cli-install](../../_includes/cli-install.md) %}

  {% include [default-catalogue](../../_includes/default-catalogue.md) %}

  Чтобы получить список операций, выполните команду:

  ```
  {{ yc-mdb-pg }} cluster list-operations <имя или идентификатор кластера>
  ```

  Идентификатор и имя кластера можно запросить со [списком кластеров в каталоге](#list-clusters).

- API

  Воспользуйтесь методом API [listOperations](../api-ref/Cluster/listOperations.md) и передайте в запросе идентификатор кластера в параметре `clusterId`.

  Идентификатор кластера можно получить со [списком кластеров в каталоге](cluster-list.md#list-clusters).

{% endlist %}
