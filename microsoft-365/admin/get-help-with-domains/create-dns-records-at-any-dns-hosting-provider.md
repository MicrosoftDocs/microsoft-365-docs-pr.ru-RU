---
title: Добавление записей DNS для подключения своего домена
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
search.appverid:
- MET150
description: Подключите домен любого поставщика услуг размещения DNS к Microsoft 365, проверив домен и обновив записи DNS в учетной записи регистратора.
ms.custom:
- okr_smb
- AdminSurgePortfolio
- AdminTemplateSet
ms.openlocfilehash: 4b4c09ce6a4161c713490daef46157b5555e124b
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393923"
---
# <a name="add-dns-records-to-connect-your-domain"></a>Добавление записей DNS для подключения своего домена

Если вы приобрели домен у стороннего поставщика услуг размещения, вы можете подключить его к Microsoft 365, обновив записи DNS учетной записи регистратора.

После выполнения этих действий ваш домен останется зарегистрированным на узле, через который вы приобрели домен, но Microsoft 365 сможет использовать его для ваших адресов электронной почты (например, user@yourdomain.com) и других служб.

Если вы не добавите домен, сотрудники вашей организации будут использовать домен onmicrosoft.com в своих адресах электронной почты до тех пор, пока вы не добавите домен. Перед добавлением пользователей важно добавить свой домен, поэтому вам не нужно было настраивать их дважды.

Если вы не нашли то, что вы ищете, см. раздел [Вопросы и ответы по доменам](../setup/domains-faq.yml) ниже.

## <a name="step-1-add-a-txt-or-mx-record-to-verify-you-own-the-domain"></a>Этап 1. Добавление записи типа TXT или MX для подтверждения права собственности на домен

### <a name="recommended-verify-with-a-txt-record"></a>Рекомендуется: Проверка с помощью записи TXT

Сначала необходимо подтвердить, что вы владеете доменом, который вы хотите добавить в Microsoft 365.

1. Войдите в [центр администрирования Microsoft 365](https://admin.microsoft.com/), а затем выберите **Показать все** > **Настройки** > **Домены**.
2. В новой вкладке или окне браузера, войдите в свой поставщик услуг размещения DNS и найдите место, в котором вы управляете параметрами DNS (например, параметры файла зоны, управление доменами, диспетчер доменов, диспетчер DNS).
3. Перейдите на страницу диспетчера DNS поставщика, добавьте запись TXT, указанную в центре администрирования, в ваш домен.

Добавление этой записи не повлияет на ваши существующие сообщения электронной почты и другие службы, и вы можете безопасно удалить ее после подключения домена к Microsoft 365.

Пример.
- Имя TXT: `@`
- Значение TXT: MS=ms######## (уникальный идентификатор из центра администрирования);
- TTL: `3600‎` (или значение вашего поставщика по умолчанию)

4. Сохраните запись, вернитесь в центр администрирования и выберите **Проверить**. Как правило, регистрация изменений занимает около 15 минут, но иногда это может занять больше времени. Предоставьте процессу некоторое время и выполните несколько попыток, чтобы изменение вступило в силу.

Когда продукт корпорации Майкрософт обнаружит правильную запись TXT, ваш домен будет подтвержден.

### <a name="verify-with-an-mx-record"></a>Проверка с помощью записи MX

Если регистратор не поддерживает добавление записей типа TXT, выполните проверку, добавив запись MX.

1. Войдите в [центр администрирования Microsoft 365](https://admin.microsoft.com/), а затем выберите **Показать все** > **Настройки** > **Домены**.
2. В новой вкладке или окне браузера, войдите в свой поставщик услуг размещения DNS и найдите место, в котором вы управляете параметрами DNS (например, параметры файла зоны, управление доменами, диспетчер доменов, диспетчер DNS).
3. Перейдите на страницу диспетчера DNS поставщика, добавьте запись MX, указанную в центре администрирования, в ваш домен.

**Priority** (Приоритет) этой записи MX должен быть самым высоким из всех существующих записей MX для домена. В противном случае она может помешать отправке и получению электронной почты. Такие записи следует удалить сразу после завершения проверки домена.

Убедитесь, что значения полей точно соответствуют указанным ниже.

- Record Type (Тип записи): `MX`
- Приоритет: установите максимальное доступное значение, обычно `0`.
- Host Name (Имя узла): `@`
- Указывает на адрес: скопируйте значение из центра администрирования и вставьте его сюда.
- TTL: `3600‎` (или значение вашего поставщика по умолчанию)

Когда продукт корпорации Майкрософт обнаружит правильную запись MX, ваш домен будет подтвержден.

## <a name="step-2-add-dns-records-to-connect-microsoft-services"></a>Шаг 2. Добавление записей DNS для подключения служб Майкрософт

В новой вкладке или окне браузера, войдите в свой поставщик услуг размещения DNS, а затем найдите место, в котором вы управляете параметрами DNS (например, параметры файла зоны, управление доменами, диспетчер доменов, диспетчер DNS).

В зависимости от служб, которые вы хотите включить, потребуется добавить несколько записей DNS различных типов. 

### <a name="add-an-mx-record-for-email-outlook-exchange-online"></a>Добавление записи MX для электронной почты (Outlook, Exchange Online)
**Прежде чем начать, выполните указанные ниже действия**. Если у пользователей уже есть электронная почта в вашем домене (например, user@yourdomain.com), перед настройкой записей MX создайте их учетные записи в центре администрирования. Таким образом, они будут продолжать получать электронную почту. После обновления записи MX вашего домена все новые сообщения, адресованные его пользователям, будут поступать в Microsoft 365. Ранее полученные сообщения останутся на текущем узле электронной почты, если вы не решите [перенести сообщения и контакты в Microsoft 365](../setup/migrate-email-and-contacts-admin.md).

Информация для записи MX будет выводится в мастере настройки домена центра администрирования.

На веб-сайте своего поставщика услуг размещения добавьте новую MX-запись.
Убедитесь, что значения полей точно соответствуют указанным ниже.

- Record Type (Тип записи): `MX`
- Приоритет: установите максимальное доступное значение, обычно `0`.
- Host Name (Имя узла): `@`
- Указывает на адрес: скопируйте значение из центра администрирования и вставьте его сюда.
- TTL: `3600‎` (или значение вашего поставщика по умолчанию)

Сохраните запись, а затем удалите все остальные записи MX.

### <a name="add-cname-records-to-connect-other-services-teams-exchange-online-aad-mdm"></a>Добавление записей CNAME для подключения к другим службам (Teams, Exchange Online, AAD, MDM)
Информация для записей CNAME будет выводится в мастере настройки домена центра администрирования.

На веб-сайте поставщика услуг размещения добавьте записи CNAME для каждой службы, которую вы хотите подключить.
Убедитесь, что значения полей точно соответствуют каждым из указанных ниже.

- Record Type (Тип записи): `CNAME (Alias)`
- Host (Узел): вставьте значения, скопированные из центра администрирования, здесь.
- Указывает на адрес: скопируйте значение из центра администрирования и вставьте его сюда.
- TTL: `3600‎` (или значение вашего поставщика по умолчанию)


### <a name="add-or-edit-an-spf-txt-record-to-help-prevent-email-spam-outlook-exchange-online"></a>Добавление или изменение записи SPF, которая помогает предотвратить нежелательную почту (Outlook, Exchange Online)
**Прежде чем начать:** если вы уже указали запись SPF для домена, не создавайте еще одну для Microsoft 365. Вместо этого добавьте необходимые значения Microsoft 365 в текущую запись по веб-сайту вашего поставщика услуг размещения, таким образом, в *одной* записи SPF будут указаны оба набора значений.

На веб-сайте вашего поставщика услуг размещения измените имеющуюся запись SPF или создайте новую запись SPF.
Убедитесь, что значения полей точно соответствуют указанным ниже.

- Record Type (Тип записи): `TXT (Text)`
- Host (Узел): `@`
- TXT Value (Значение TXT): `v=spf1 include:spf.protection.outlook.com -all`
- TTL: `3600‎` (или значение вашего поставщика по умолчанию)

Сохраните запись.

Проверьте запись SPF, используя одно из этих [средств проверки SPF](/office365/admin/setup/domains-faq#how-can-i-validate-spf-records-for-my-domain).

Инфраструктура политики отправителей (SPF) призвана предотвратить спуфинг, но существуют некоторые методики, позволяющие обойти ее. Чтобы защититься от таких атак, по завершении настройки SPF необходимо настроить DKIM и DMARC для Microsoft 365. 

Чтобы начать, см. статьи [Проверка исходящей электронной почты, отправляемой со своего домена в Microsoft 365, с помощью DKIM](../../security/office-365-security/use-dkim-to-validate-outbound-email.md) и [Использование DMARC для проверки электронной почты в Microsoft 365](../../security/office-365-security/use-dmarc-to-validate-email.md).

### <a name="add-srv-records-for-communications-services-teams-skype-for-business"></a>Добавление записей SRV для служб связи (Teams, Skype для бизнеса)

На веб-сайте поставщика услуг размещения добавьте записи SRV для каждой службы, которую вы хотите подключить.
Убедитесь, что значения полей точно соответствуют каждым из указанных ниже.

- Record Type (Тип записи): `SRV (Service)`
- Имя: `@`
- Цель: скопируйте значение из центра администрирования и вставьте его сюда.
- Протокол: скопируйте значение из центра администрирования и вставьте его сюда.
- Служба: скопируйте значение из центра администрирования и вставьте его сюда.
- Приоритет: `100`
- Weight (Вес):`1`
- Порт: скопируйте значение из центра администрирования и вставьте его сюда.
- TTL: `3600‎` (или значение вашего поставщика по умолчанию)

Сохраните запись.

#### <a name="srv-record-field-restrictions-and-workarounds"></a>Ограничения и обходные пути для полей записи SRV
Некоторые поставщики услуг размещения накладывают ограничения на значения полей в записях SRV. Ниже приведены некоторые распространенные временные решения для этих ограничений.

##### <a name="name"></a>Имя
Если ваш поставщик услуг размещения не позволяет задать для этого поля **@**, оставьте это поле пустым. Следуйте этим инструкциям *только* в том случае, если вашим поставщиком услуг размещения предусмотрены отдельные поля для значений "Service" (Служба) и "Protocol" (Протокол). В противном случае см. примечания о соответствующих параметрах ниже.

##### <a name="service-and-protocol"></a>Поля Service (Служба) и Protocol (Протокол)
Если у вашего поставщика услуг размещения нет соответствующих полей для записей SRV, параметры **Service (Служба)** и **Protocol (Протокол)** задаются в поле **Name (Имя)** данной записи. (Примечание. В зависимости от поставщика услуг размещения, поле **Name (Имя)** может называться иначе, например, **Host**, **Hostname** или **Subdomain**.) Чтобы добавить эти значения, укажите их в одной строке, разделив значения точкой. 

Пример: `_sip._tls`

##### <a name="priority-weight-and-port-br"></a>Поля Priority (Приоритет), Weight (Вес) и Port (Порт) <br>
Если у вашего поставщика услуг размещения нет необходимых полей для записей SRV, соответствующие параметры задаются в поле **Target (Цель)** данной записи. (Примечание. В зависимости от поставщика услуг размещения поле **Target (Цель)** может называться иначе, например, **Content (Содержимое)**, **IP Address (IP-адрес)** или **Target Host (Целевой узел**.) 

Чтобы добавить эти значения, укажите их в одной строке, разделив значения пробелами, и *иногда строка может заканчиваться точкой* (если вы не уверены, обратитесь к поставщику.) Значения указываются в следующем порядке: Priority, Weight, Port, Target. 

- Пример 1:`100 1 443 sipdir.online.lync.com.`
- Пример 2: `100 1 443 sipdir.online.lync.com`

## <a name="related-content"></a>См. также:

[Изменение серверов доменных имен для настройки Microsoft 365 с любым регистратором доменных имен](change-nameservers-at-any-domain-registrar.md) (статья)\
[Поиск и устранение неполадок после добавления домена и записей DNS](find-and-fix-issues.md) (статья)\
[Управление доменами](index.yml) (страница ссылки)