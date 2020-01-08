---
title: Метки конфиденциальности в приложениях Office
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Сведения о том, как пользователи работают с метками конфиденциальности в приложениях Office для настольных систем, приложений Office для мобильных устройств и приложений Office для Интернета. Узнайте, какие приложения поддерживают метки конфиденциальности.
ms.openlocfilehash: 092c8510acac5cafa6417f93eae19731db5df270
ms.sourcegitcommit: af7950d9674f0eab3aee03f9afccff9ca2f4709a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2020
ms.locfileid: "40970957"
---
# <a name="sensitivity-labels-in-office-apps"></a>Метки конфиденциальности в приложениях Office

В этой статье описываются:

- Требования к среде, прежде чем применять метки конфиденциальности к электронной почте, файлам и вложениям.
- Какие возможности меток чувствительности поддерживаются каждым приложением Office.
- Что происходит при сочетании меток конфиденциальности с другими технологиями безопасности и соответствия Майкрософт, которые работают с приложениями Office.
- Сведения о том, как сотрудники Организации могут использовать метки конфиденциальности при работе с приложениями Office для Windows и приложениями Office для Интернета.
- Где, чтобы перейти к разделу "получение людей в организации" с метками конфиденциальности.

## <a name="subscription-and-licensing-requirements-for-sensitivity-labels"></a>Требования к подписке и лицензированию для меток конфиденциальности

Пользователям должна быть назначена по крайней мере одна из следующих лицензий:

- [Microsoft 365 E3](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) или более поздняя версия

- [Office 365 E3](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e3-business-software) или более поздней версии

- [Azure Information Protection Premium P1](https://azure.microsoft.com/pricing/details/information-protection/) или выше

Встроенный клиент меток Office поддерживает метки конфиденциальности с выпуском подписки Office. Этот клиент наклеек не поддерживает автономные выпуски Office, такие как Office 2016 и Office 2019. Чтобы использовать метки конфиденциальности с этими выпусками Office на компьютерах с Windows, установите клиент единой метки Azure Information Protection.

Чтобы использовать автоматические или Рекомендуемые метки чувствительности, пользователям необходима одна из следующих лицензий:

- [Microsoft 365](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) в ~ или более поздней версии

- [Office 365](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software) в ~ или более поздней версии

- [Azure Information Protection Premium P2](https://azure.microsoft.com/pricing/details/information-protection/)

## <a name="support-for-sensitivity-label-capabilities-in-word-excel-and-powerpoint"></a>Поддержка возможностей меток конфиденциальности в Word, Excel и PowerPoint

Для каждой возможности в таблице ниже перечислены минимальные версии, необходимые для поддержки меток конфиденциальности с помощью встроенных меток.

При установке клиента единой метки Azure Information Protection, который выполняется только на компьютерах под управлением Windows, доступны дополнительные возможности. Эти сведения можно найти [в статье сравнение пометок клиентов для компьютеров с Windows](https://docs.microsoft.com/azure/information-protection/rms-client/use-client#compare-the-labeling-clients-for-windows-computers).

|Возможность                                                                                                        |Рабочий стол Windows |Настольный компьютер Mac |iOS    |Android      |Web                                                         |
|------------------------------------------------------------------------------------------------------------------|----------------|------------|-------|-------------|------------------------------------------------------------|
|[Вручную применить, изменить или удалить метку](https://support.office.com/article/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)| 1910 и выше          | 16.21 +     | 2.21 и выше | 16.0.11231 и выше | [Предварительная версия](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Применение стандартной метки](sensitivity-labels.md#what-label-policies-can-do)                                         | 1910 и выше          | 16.21 +     | 2.21 и выше | 16.0.11231 и выше | Раздел "Рецензирование"                                                        |
|[Требование обоснования для изменения метки](sensitivity-labels.md#what-label-policies-can-do)                     | 1910 и выше          | 16.21 +     | 2.21 и выше | 16.0.11231 и выше | [Предварительная версия](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Ссылка справки на настраиваемую страницу справки](sensitivity-labels.md#what-label-policies-can-do)                       | 1910 и выше          | 16.21 +     | 2.21 и выше | 16.0.11231 и выше | [Предварительная версия](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Маркировка содержимого](sensitivity-labels.md#what-label-policies-can-do)                                              | 1910 и выше          | 16.21 +     | 2.21 и выше | 16.0.11231 и выше | [Предварительная версия](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Назначение разрешений сразу](encryption-sensitivity-labels.md#assign-permissions-now)                                 | 1910 и выше          | 16.21 +     | 2.21 и выше | 16.0.11231 и выше | [Предварительная версия](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Предоставление пользователям возможности назначать разрешения](encryption-sensitivity-labels.md#let-users-assign-permissions)                     | Раздел "Рецензирование"            | Раздел "Рецензирование"        | Раздел "Рецензирование"   | Раздел "Рецензирование"         | Раздел "Рецензирование"                                                        |
|[Просмотр использования меток с помощью аналитики меток](label-analytics.md) и отправка данных для администраторов                      | Раздел "Рецензирование"            | Раздел "Рецензирование"        | Раздел "Рецензирование"   | Раздел "Рецензирование"         | Раздел "Рецензирование"                                                        |
|
  [Требование применения пользователями метки к электронной почте и документам](sensitivity-labels.md#what-label-policies-can-do)   | Раздел "Рецензирование"            | Раздел "Рецензирование"        | Раздел "Рецензирование"   | Раздел "Рецензирование"         | Раздел "Рецензирование"                                                        |
|[Автоматическое применение метки конфиденциальности к содержимому](apply-sensitivity-label-automatically.md)                    | Предварительный просмотр: в [программе предварительной оценки Office](https://office.com/insider)                                  | Раздел "Рецензирование" | Раздел "Рецензирование" | Раздел "Рецензирование" | [Предварительная версия](sensitivity-labels-sharepoint-onedrive-files.md) |
|Поддержка [автосохранения](https://support.office.com/article/6d6bd723-ebfd-4e40-b5f6-ae6e8088f7a5) и [совместного редактирования](https://support.office.com/article/ee1509b4-1f6e-401e-b04a-782d26f564a4) для помеченных и защищенных документов | Раздел "Рецензирование" | Раздел "Рецензирование" | Раздел "Рецензирование" | Раздел "Рецензирование" | [Предварительная версия](sensitivity-labels-sharepoint-onedrive-files.md) |
|

## <a name="support-for-sensitivity-label-capabilities-in-outlook"></a>Поддержка возможностей меток конфиденциальности в Outlook

Для каждой возможности в следующей таблице перечислены минимальные версии, необходимые для этого приложения.

При установке клиента единой метки Azure Information Protection, который выполняется только на компьютерах под управлением Windows, доступны дополнительные возможности. Эти сведения можно найти [в статье сравнение пометок клиентов для компьютеров с Windows](https://docs.microsoft.com/azure/information-protection/rms-client/use-client#compare-the-labeling-clients-for-windows-computers).

|Возможность                                                                                                        |Рабочий стол Outlook для Windows |Настольные компьютеры с Outlook на Mac  |Outlook для iOS |Outlook для Android |Outlook в Интернете |
|------------------------------------------------------------------------------------------------------------------|---------------------------|------------------------|---------------|-------------------|-------------------|
|[Вручную применить, изменить или удалить метку](https://support.office.com/article/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)| 1910 и выше                     | 16.21 +                 | 4.71 +         | 4.0.39 +           | Да               |
|[Применение стандартной метки](sensitivity-labels.md#what-label-policies-can-do)                                         | 1910 и выше                     | 16.21 +                 | 4.71 +         | 4.0.39 +           | Да               |
|[Требование обоснования для изменения метки](sensitivity-labels.md#what-label-policies-can-do)                     | 1910 и выше                     | 16.21 +                 | 4.71 +         | 4.0.39 +           | Да               |
|[Ссылка справки на настраиваемую страницу справки](sensitivity-labels.md#what-label-policies-can-do)                       | 1910 и выше                     | 16.21 +                 | 4.71 +         | 4.0.39 +           | Да               |
|[Маркировка содержимого](sensitivity-labels.md#what-label-policies-can-do)                                              | 1910 и выше                     | 16.21 +                 | 4.71 +         | 4.0.39 +           | Да               |
|[Назначение разрешений сразу](encryption-sensitivity-labels.md#assign-permissions-now)                                 | 1910 и выше                     | 16.21 +                 | 4.71 +         | 4.0.39 +           | Да               |
|[Предоставление пользователям возможности назначать разрешения](encryption-sensitivity-labels.md#let-users-assign-permissions)                     | 1910 и выше                     | 16.21 +                 | 4.71 +         | 4.0.39 +           | Да               |
|[Просмотр использования меток с помощью аналитики меток](label-analytics.md) и отправка данных для администраторов                      | Раздел "Рецензирование"                       | Раздел "Рецензирование"                    | Раздел "Рецензирование"           | Раздел "Рецензирование"               | Раздел "Рецензирование"               |
|
  [Требование применения пользователями метки к электронной почте и документам](sensitivity-labels.md#what-label-policies-can-do)   | Раздел "Рецензирование"                       | Раздел "Рецензирование"                    | Раздел "Рецензирование"           | Раздел "Рецензирование"               | Раздел "Рецензирование"               |
|[Автоматическое применение метки конфиденциальности к содержимому](apply-sensitivity-label-automatically.md)                    | Раздел "Рецензирование"                       | Раздел "Рецензирование"                    | Раздел "Рецензирование"           | Раздел "Рецензирование"               | Предварительный просмотр: при развертывании в [целевом выпуске](https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365?view=o365-worldwide) |
|

## <a name="about-the-office-built-in-labeling-client"></a>О встроенном клиенте меток для Office

Встроенный клиент наклеек Office загружает метки и параметры политики из следующих центров администрирования:

- Центр безопасности и соответствия требованиям Office 365

- Центр безопасности Microsoft 365

- Центр соответствия требованиям Microsoft 365

Чтобы использовать встроенный клиент меток Office, необходимо иметь одну или несколько [политик меток, опубликованных](sensitivity-labels.md#what-label-policies-can-do) пользователям из одного из указанных в списке центров администрирования.

Тем не менее, если пользователи имеют один из установленных клиентов Azure Information Protection ([клиент единой метки](https://docs.microsoft.com/azure/information-protection/rms-client/aip-clientv2) или [классического клиента](https://docs.microsoft.com/azure/information-protection/rms-client/aip-client)), по умолчанию встроенный клиент меток отключен в приложениях Office. Чтобы использовать встроенные метки, а не клиент Azure Information Protection для приложений Office, отключите или удалите надстройку Office для Azure Information Protection:

1. Выполните одно из следующих действий:
    
    - **Для нескольких компьютеров:** Настройка **использования функции учета конфиденциальности в Office для применения и просмотра** параметров групповой политики меток конфиденциальности. Этот параметр находится в разделе **Конфигурация пользователя/Административные шаблоны/Microsoft Office 2016/параметры безопасности**. Разверните этот параметр с помощью групповой политики или [службы Microsoft Cloud Policy Service](https://docs.microsoft.com/DeployOffice/overview-office-cloud-policy-service).
    
    - **Для одного компьютера:** Сведения о том, как [окончательно отключить или удалить](https://support.office.com/article/16278816-1948-4028-91e5-76dca5380f8d) надстройку Azure Information Protection на одном компьютере, можно в разделе "Просмотр, управление и установка надстроек в приложениях Office".

2. Перезапустите все приложения Office.

Когда вы отключаете или удаляете надстройку Office, клиент Azure Information Protection остается установленным, чтобы вы могли продолжать помечать файлы, не входящие в ваши приложения Office. Например, с помощью проводника или PowerShell.

Сведения о функциях, поддерживаемых клиентами Azure Information Protection и встроенным пометокми клиента Office, можно узнать в статье [Выбор меток, которые будут использоваться для компьютеров под управлением Windows](https://docs.microsoft.com/azure/information-protection/rms-client/use-client#choose-which-labeling-client-to-use-for-windows-computers) в документации Azure Information Protection.

## <a name="protection-templates-and-sensitivity-labels"></a>Шаблоны защиты и метки конфиденциальности

[Шаблоны защиты](https://docs.microsoft.com/azure/information-protection/configure-policy-templates), определенные администратором, например, указанные для шифрования сообщений Office 365, не отображаются в приложениях Office при использовании встроенных меток. Этот упрощенный интерфейс показывает, что нет необходимости выбирать шаблон защиты, так как те же параметры включаются в метки чувствительности с включенным шифрованием.

Если вам нужно преобразовать существующие шаблоны защиты в метки, используйте портал Azure и следующие инструкции: [чтобы преобразовать шаблоны в метки](https://docs.microsoft.com/azure/information-protection/configure-policy-templates#to-convert-templates-to-labels).

## <a name="apply-sensitivity-labels-to-files-emails-and-attachments"></a>Применение меток конфиденциальности к файлам, сообщениям электронной почты и вложениям

Пользователи могут одновременно применять только одну метку для каждого документа или электронной почты.

Если вы настроили метку сообщения электронной почты с вложениями, то вложения не наследуют метку. Если вложение снабжено меткой, оно будет храниться в отдельной метке. Если у вложения нет метки, вложения сохраняются без метки. Однако если метка для сообщения электронной почты обеспечивает применение защиты, эта защита применяется к вложениям Office.

## <a name="sensitivity-label-compatibility"></a>Совместимость меток конфиденциальности

**С приложениями RMS – енлигхтенед**. Если вы откроете подписанный _и зашифрованный_ документ или электронную почту в [приложении RMS-енлигхтенед](https://docs.microsoft.com/azure/information-protection/requirements-applications#rms-enlightened-applications) , не поддерживающем метки конфиденциальности, приложение по-прежнему будет применять шифрование и управление правами.

**С клиентом Azure Information Protection**. Вы можете просматривать и изменять метки конфиденциальности, которые применяются к документам и сообщениям электронной почты с помощью встроенного клиента с метками Office с помощью клиента Azure Information Protection и наоборот.

**С другими версиями Office**. Любой уполномоченный пользователь может открывать помеченные документы и сообщения электронной почты в других версиях Office. Тем не менее, вы можете просматривать и изменять метки в поддерживаемых версиях Office или в клиенте Azure Information Protection. Поддерживаемые версии приложений Office перечислены в таблицах этой статьи.

## <a name="support-for-sharepoint-and-onedrive-files-protected-by-sensitivity-labels"></a>Поддержка файлов SharePoint и OneDrive, защищенных с помощью меток конфиденциальности

Чтобы использовать встроенный клиент наклеек Office в Office в Интернете, документ должен находиться в экземпляре OneDrive для бизнеса или SharePoint Online, который выбрал параметр [Включить метки конфиденциальности для файлов Office в SharePoint и OneDrive](sensitivity-labels-sharepoint-onedrive-files.md).

## <a name="when-office-365-applies-marks-and-encryption-to-content"></a>Когда Office 365 применяет метки и шифрование к содержимому

Office 365 применяет метки содержимого или шифрование по-разному в зависимости от используемого приложения.

| Приложение | Маркировка содержимого | Шифрование |
| --- | --- | --- |
| Word, Excel, PowerPoint на всех платформах | Сразу | Сразу |
| Outlook для ПК и Mac | После отправки электронной почты в Exchange Online | Сразу |
| Outlook в Интернете, для iOS и Android | После отправки электронной почты в Exchange Online | После отправки электронной почты в Exchange Online |
|

## <a name="more-resources"></a>Дополнительные ресурсы

[Вопросы и ответы о классификации и присвоении меток в Azure Information Protection](https://docs.microsoft.com/azure/information-protection/faqs-infoprotect)

[Применение меток конфиденциальности к документам и сообщениям электронной почты в Office](https://support.office.com/article/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)
