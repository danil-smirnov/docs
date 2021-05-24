1. В начале конфигурационного файла необходимо задать настройки провайдера.

    {% note info %}

    Настройки проверены на Terraform версии `0.14`.

    {% endnote %}

   ```hcl
   terraform {
     required_providers {
       yandex = {
         source = "yandex-cloud/yandex"
       }
     }
   }

   provider "yandex" {
     token     = "<OAuth>"
     cloud_id  = "<идентификатор облака>"
     folder_id = "<идентификатор каталога>"
     zone      = "<зона доступности по умолчанию>"
   }
   ```

   * `provider` — название провайдера.
   * `token` — [OAuth-токен](../../iam/concepts/authorization/oauth-token.md) для доступа к {{ yandex-cloud }}.
   * `cloud_id` — идентификатор облака, в котором Terraform создаст ресурсы.
   * `folder_id` — [идентификатор каталога](../../resource-manager/operations/folder/get-id.md), в котором по умолчанию будут создаваться ресурсы.
   * `zone` — [зона доступности](../../overview/concepts/geo-scope.md), в которой по умолчанию будут создаваться все облачные ресурсы.

1.  Выполните команду `terraform init` в папке с конфигурационным файлом. Эта команда инициализирует провайдеров, указанных в конфигурационных файлах, и позволяет работать с ресурсами и источниками данных провайдера.