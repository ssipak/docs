# Взаимосвязь ресурсов в {{ mos-name }}

Сервис {{ mos-full-name }} помогает разворачивать и поддерживать кластеры серверов {{ OS }} в инфраструктуре {{ yandex-cloud }}.

{{ OS }} — это комплект поисковых и аналитических ресурсов для мониторинга приложений в режиме реального времени, анализа журналов и поиска по веб-сайтам. Кластер {{ OS }} состоит из одной или нескольких групп хостов с разными ресурсами, которые решают разные задачи.

При [создании кластера](../operations/cluster-create.md) необходимо указывать:

- [_Классы хостов_](instance-types.md) — шаблоны виртуальных машин, по которым будут развертываться хосты кластера.

- [_Группы хостов_](host-groups.md) — наборы из нескольких связанных друг с другом хостов с определенными характеристиками и [ролями](hosts-roles.md):

    - [_DATA_](hosts-roles.md#data);
    - [_MANAGER_](hosts-roles.md#manager);
    - [_DASHBOARDS_](hosts-roles.md#dashboards).

- _Окружение_, в котором будет развертываться кластер:

    - `PRODUCTION` — для стабильных версий ваших приложений.
    - `PRESTABLE` — для тестирования, в том числе самого сервиса {{ mos-name }}. В Prestable-окружении раньше появляются новая функциональность, улучшения и исправления ошибок. При этом не все обновления обеспечивают обратную совместимость.

- _Пароль пользователя_ `admin`.

    {% include [mos-superuser](../../_includes/mdb/mos/superuser.md)%}

- _Версию_ {{ OS }}.


Созданный в каталоге кластер {{ OS }} доступен для всех виртуальных машин, подключенных к той же [облачной сети](../../vpc/concepts/network.md), что и кластер.


Кластер с группой из одного хоста отказоустойчивости не обеспечивает. Кластер из нескольких хостов автоматически обеспечивает отказоустойчивость для роли `MANAGER`. Чтобы обеспечить сохранность данных в многохостовом кластере, настройте для него [шардирование и репликацию](scalability-and-resilience.md) индексов.

Хосты кластера могут находиться в разных зонах доступности и разных подсетях. Подробнее о географии {{ yandex-cloud }} см. в разделе [{#T}](../../overview/concepts/geo-scope.md).

{% include [monitoring-access](../../_includes/mdb/monitoring-access.md) %}
