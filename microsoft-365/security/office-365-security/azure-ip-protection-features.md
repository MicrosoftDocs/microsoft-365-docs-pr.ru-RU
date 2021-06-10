---
title: Функции защиты в Azure Information Protection, развертывание для существующих клиентов
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/29/2018
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 7ad6f58e-65d7-4c82-8e65-0b773666634d
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: В этой статье объясняются изменения, которые были внесены в функции защиты в Azure Information Protection.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 77d45c8521e67c480b9e5557b05eed8ba5dd2645
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206008"
---
# <a name="protection-features-in-azure-information-protection-rolling-out-to-existing-tenants"></a>Функции защиты в Azure Information Protection, развертывание для существующих клиентов

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Область применения**
- [Microsoft Defender для Office 365 (план 2)](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Чтобы помочь на начальном этапе защиты информации, с июля 2018 г. все клиенты Azure Information Protection будут иметь функции защиты в Azure Information Protection, включенной по умолчанию. Функции защиты в Azure Information Protection ранее были известны в Office 365 как Управление правами или Azure RMS. Если у вашей организации есть Office E3 или более высокий план службы, вы получите возможность защитить информацию с помощью Azure Information Protection при запуске этих функций.

## <a name="changes-beginning-july-1-2018"></a>Изменения с 1 июля 2018 г.

С 1 июля 2018 г. Корпорация Майкрософт будет использовать возможности защиты в Azure Information Protection для всех организаций с одним из следующих планов подписки:

- шифрование сообщений Office 365 предлагается в Office 365 e3 и E5, Microsoft E3 и E5, Office 365 A1, A3 и A5, а также Office 365 G3 и G5. Вам не нужны дополнительные лицензии для получения новых возможностей защиты с помощью Azure Information Protection.

- Вы также можете добавить план 1 azure information Protection Plan 1 к следующим планам получения новых возможностей шифрование сообщений Office 365: Exchange Online Plan 1, Exchange Online Plan 2, Office 365 F1, Microsoft 365 бизнес базовый, Microsoft 365 бизнес стандарт или Office 365 корпоративный E1.

- Каждый пользователь, пользующийся шифрование сообщений Office 365, должен иметь лицензию, чтобы она была охвачена этой функцией.

- Полный список см. в Exchange Online [описания](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description) службы для шифрование сообщений Office 365.

Администраторы клиентов могут проверить состояние защиты на портале Office 365 администратора.

![Снимок экрана, на который показано, Office 365 активируется управление правами.](../../media/303453c8-e4a5-4875-b49f-e80c3eb7b91e.png)

## <a name="why-are-we-making-this-change"></a>Почему мы внося эти изменения?

шифрование сообщений Office 365 использует возможности защиты в Azure Information Protection. В основе последних улучшений шифрование сообщений Office 365 и наших более широких инвестиций в защиту информации в Microsoft 365 году мы упрощаем для организаций возможность включить и использовать наши возможности защиты, так как исторически технологии шифрования сложно настроить. Включив функции защиты в Azure Information Protection по умолчанию, можно быстро начать защищать конфиденциальные данные.

## <a name="does-this-impact-me"></a>Влияет ли это на меня?

Если ваша организация приобрела Office 365 лицензию, это изменение повлияет на клиента.

> [!IMPORTANT]
> Если вы используете службы Active Directory Rights Management (AD RMS) в локальной среде, необходимо либо немедленно отказаться от этого изменения, либо перейти в Azure Information Protection, прежде чем мы выкатим это изменение в течение следующих 30 дней. Сведения о том, как отказаться от использования, см. в "Я использую AD RMS, как отказаться?" далее в этой статье. Если вы предпочитаете мигрировать, см. в руб. Миграция из [AD RMS в Azure Information Protection.](/azure/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms).

## <a name="can-i-use-azure-information-protection-with-active-directory-rights-management-services-ad-rms"></a>Можно ли использовать Azure Information Protection с службы Active Directory Rights Management (AD RMS)?

Нет. Это не поддерживаемый сценарий развертывания. Без дополнительных действий по отказу некоторые компьютеры могут автоматически приступить к использованию службы управления правами Azure, а также подключиться к кластеру AD RMS. Этот сценарий не поддерживается и имеет ненадежные результаты, поэтому важно отказаться от этого изменения в течение следующих 30 дней, прежде чем мы выкатим эти новые функции. Сведения о том, как отказаться от использования, см. в "Я использую AD RMS, как отказаться?" далее в этой статье. Если вы предпочитаете мигрировать, см. в видеоролике Миграция из [AD RMS в Azure Information Protection.](/azure/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms)

## <a name="how-do-i-know-if-im-using-ad-rms"></a>Как узнать, использую ли Я AD RMS?

Используйте эти инструкции по подготовке среды для управления правами Azure, если у вас также есть службы Active Directory Rights Management [(AD RMS),](/azure/information-protection/deploy-use/prepare-environment-adrms) чтобы проверить, развернута ли служба AD RMS:

1. Хотя это необязательно, большинство развертывания AD RMS публикуют точку подключения службы (SCP) к Active Directory, чтобы доменные компьютеры могли обнаружить кластер AD RMS.

   Чтобы узнать, опубликован ли SCP в Active Directory, используйте редактирование ADSI: CN=Configuration [имя сервера], CN=Services, CN=RightsManagementServices, CN=SCP

2. Если вы не используете SCP, Windows компьютеры, подключаемые к кластеру AD RMS, должны быть настроены для обнаружения клиентской службы или перенаправления лицензирования с помощью Windows реестра: `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC\ServiceLocation or HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\MSIPC\ServiceLocation` .

Дополнительные сведения об этих конфигурациях реестра см. в дополнительных сведениях об открытии клиентской службы с помощью [Windows](/azure/information-protection/rms-client/client-deployment-notes#enabling-client-side-service-discovery-by-using-the-windows-registry) реестра и перенаправления трафика серверов [лицензирования.](/azure/information-protection/rms-client/client-deployment-notes#redirecting-licensing-server-traffic)

## <a name="i-use-ad-rms-how-do-i-opt-out"></a>Как отказаться от использования AD RMS?

Чтобы отказаться от предстоящих изменений, выполните следующие действия:

1. С помощью учетной записи работы или школы, которая имеет глобальные разрешения администратора в организации, запустите сеанс Windows PowerShell и подключите к Exchange Online. Инструкции см. в статье [Подключение к Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

2. Запустите Set-IRMConfiguration с помощью следующего синтаксиса:

  ```powershell
  Set-IRMConfiguration -AutomaticServiceUpdateEnabled $false
  ```

## <a name="what-can-i-expect-after-this-change-has-been-made"></a>Что можно ожидать после внося этого изменения?

После включения, при условии, что вы не отказали, вы можете начать использовать новую версию шифрование сообщений Office 365, которая была объявлена на [Microsoft Ignite 2017](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Email-Encryption-and-Rights-Protection/ba-p/110801) и использует возможности шифрования и защиты azure information Protection.

![Снимок экрана, на который показано защищенное сообщение OME в Outlook в Интернете.](../../media/599ca9e7-c05a-429e-ae8d-359f1291a3d8.png)

Дополнительные сведения о новых улучшениях см. в [шифрование сообщений Office 365.](../../compliance/ome.md)