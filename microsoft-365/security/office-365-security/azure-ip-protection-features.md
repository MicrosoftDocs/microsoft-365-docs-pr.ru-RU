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
description: В этой статье объясняется, какие изменения внося в функции защиты в Azure Information Protection
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 0769306c3aa2d1a357e1d5999d1a1406c02aa5f3
ms.sourcegitcommit: a9ac702c9efc9defded3bfa65618b94bac00c237
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/16/2021
ms.locfileid: "50261565"
---
# <a name="protection-features-in-azure-information-protection-rolling-out-to-existing-tenants"></a>Функции защиты в Azure Information Protection, развертывание для существующих клиентов

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Область применения**
- [Microsoft Defender для Office 365 (план 2)](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Чтобы помочь вам на начальном этапе защиты информации, с июля 2018 г. все клиенты, соответствующие требованиям Azure Information Protection, по умолчанию будут иметь функции защиты в Azure Information Protection. Функции защиты в Azure Information Protection ранее были известны в Office 365 как управление правами или Azure RMS. Если в вашей организации имеется план обслуживания Office E3 или более высокий план обслуживания, вы получите возможность защитить информацию с помощью Azure Information Protection при их развии.

## <a name="changes-beginning-july-1-2018"></a>Изменения с 1 июля 2018 г.

С 1 июля 2018 г. корпорация Майкрософт включает функцию защиты в Azure Information Protection для всех организаций с одним из следующих планов подписки:

- Шифрование сообщений Office 365 предлагается в составе Office 365 E3 и E5, Microsoft E3 и E5, Office 365 A1, A3 и A5, а также Office 365 G3 и G5. Для получения новых возможностей защиты на платформе Azure Information Protection дополнительные лицензии не требуются.

- Вы также можете добавить Azure Information Protection (план 1) в следующие планы, чтобы получить новые возможности шифрования сообщений Office 365: Exchange Online (план 1), Exchange Online (план 2), Office 365 F1, Microsoft 365 бизнес базовый, Microsoft 365 бизнес стандарт или Office 365 корпоративный E1.

- Каждый пользователь, пользующийся шифрованием сообщений Office 365, должен иметь лицензию на эту функцию.

- Полный список см. в описании [службы Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description) для шифрования сообщений Office 365.

Администраторы клиентов могут проверить состояние защиты на портале администратора Office 365.

![Screenshot that shows that rights management in Office 365 is activated.](../../media/303453c8-e4a5-4875-b49f-e80c3eb7b91e.png)

## <a name="why-are-we-making-this-change"></a>Почему мы внося это изменение?

Шифрование сообщений Office 365 использует возможности защиты в Azure Information Protection. В основе последних улучшений шифрования сообщений Office 365 и наших более широких инвестиций в защиту информации в Microsoft 365 мы упростим для организаций возможность включить и использовать наши возможности защиты, так как исторически трудно настроить технологии шифрования. Включив функции защиты в Azure Information Protection по умолчанию, вы можете быстро начать защищать конфиденциальные данные.

## <a name="does-this-impact-me"></a>Влияет ли это на меня?

Если ваша организация приобрела подходящую лицензию На Office 365, это изменение повлияет на ваш клиент.

> [!IMPORTANT]
> Если вы используете службу служба управления правами Active Directory (AD RMS) в локальной среде, необходимо либо немедленно отказаться от этого изменения, либо перейти на Azure Information Protection, прежде чем мы развявим это изменение в течение следующих 30 дней. Сведения об отказе см. в подкачки "Я использую AD RMS, как отказаться?" далее в этой статье. Если вы предпочитаете мигрировать, см. сведения о переходе с [AD RMS на Azure Information Protection.](https://docs.microsoft.com/azure/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms)

## <a name="can-i-use-azure-information-protection-with-active-directory-rights-management-services-ad-rms"></a>Можно ли использовать Azure Information Protection с служба управления правами Active Directory (AD RMS)?

Нет. Этот сценарий развертывания не поддерживается. Без дополнительных действий по отказу некоторые компьютеры могут автоматически начать использовать службу управления правами Azure, а также подключиться к кластеру AD RMS. Этот сценарий не поддерживается и имеет ненадежные результаты, поэтому важно отказаться от этого изменения в течение следующих 30 дней, прежде чем мы развернем эти новые функции. Сведения об отказе см. в подкачки "Я использую AD RMS, как отказаться?" далее в этой статье. Если вы предпочитаете мигрировать, см. сведения о переходе с [AD RMS на Azure Information Protection.](https://docs.microsoft.com/azure/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms)

## <a name="how-do-i-know-if-im-using-ad-rms"></a>Как узнать, используется ли AD RMS?

Используйте эти инструкции из подготовки среды для azure Rights Management, если у вас также есть служба управления правами Active Directory [(AD RMS),](https://docs.microsoft.com/azure/information-protection/deploy-use/prepare-environment-adrms) чтобы проверить, развернута ли служба AD RMS:

1. Хотя это необязательно, большинство развертывание AD RMS публикует точку подключения службы (SCP) в Active Directory, чтобы компьютеры домена могли обнаружить кластер AD RMS.

   Используйте редактор ADSI, чтобы узнать, опубликован ли SCP в Active Directory: CN=Configuration [имя сервера], CN=Services, CN=RightsManagementServices, CN=SCP

2. Если вы не используете SCP, компьютеры с Windows, подключаемые к кластеру AD RMS, должны быть настроены для обнаружения клиентских служб или перенаправления лицензирования с помощью реестра `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC\ServiceLocation or HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\MSIPC\ServiceLocation` Windows:

Дополнительные сведения об этих конфигурациях реестра см. в подключеке "Включение обнаружения клиентских служб с помощью реестра [Windows"](https://docs.microsoft.com/azure/information-protection/rms-client/client-deployment-notes#enabling-client-side-service-discovery-by-using-the-windows-registry) и "Перенаправление трафика сервера [лицензирования".](https://docs.microsoft.com/azure/information-protection/rms-client/client-deployment-notes#redirecting-licensing-server-traffic)

## <a name="i-use-ad-rms-how-do-i-opt-out"></a>Как отказаться от использования AD RMS?

Чтобы отказаться от предстоящих изменений, выполните следующие действия:

1. Используя учетную запись для работы или учебного заведения с разрешениями глобального администратора в организации, Windows PowerShell сеанс и подключите его к Exchange Online. Инструкции см. в статье [Подключение к Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).

2. Запустите Set-IRMConfiguration с помощью следующего синтаксиса:

  ```powershell
  Set-IRMConfiguration -AutomaticServiceUpdateEnabled $false
  ```

## <a name="what-can-i-expect-after-this-change-has-been-made"></a>Чего можно ожидать после внося этого изменения?

Если вы не отключили эту функцию, вы можете начать использовать новую версию шифрования сообщений Office 365, которая была объявлена на [Microsoft Ignite 2017](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Email-Encryption-and-Rights-Protection/ba-p/110801) и использует возможности шифрования и защиты Azure Information Protection.

![Снимок экрана: защищенное сообщение OME в Outlook в Интернете.](../../media/599ca9e7-c05a-429e-ae8d-359f1291a3d8.png)

Дополнительные сведения о новых усовершенствованиях см. в сообщении [шифрования сообщений Office 365.](../../compliance/ome.md)
