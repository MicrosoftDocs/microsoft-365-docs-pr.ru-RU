---
title: Инфраструктура Windows 10 Enterprise для Microsoft 365 для предприятия
description: Высокоуровневая рекомендации на действия, необходимые для развертывания корпоративной 10 Windows на компьютерах в составе Microsoft 365 Enterprise.
keywords: Развертывания документации Windows 10 Enterprise Microsoft 365 365 Microsoft, Microsoft 365 корпоративный
author: greg-lindsay
localization_priority: Normal
audience: microsoft-business
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 09/18/2018
ms.author: greglin
ms.openlocfilehash: 80d7c1b56434647387b9c428ca07effdff929abf
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/28/2018
ms.locfileid: "26870443"
---
# <a name="phase-3-windows-10-enterprise"></a>Этап 3. Windows 10 Корпоративная

![](./media/deploy-foundation-infrastructure/win10enterprise_icon.png)

Microsoft 365 Enterprise включает в себя Enterprise 10 Windows, которая предоставляет средства для работы и обеспечить безопасность. Enterprise Windows 10:

- **Интегрированное для простоты** - окружения возможности облака, чтобы уменьшить сложность управления сегодня 's современных среды устройства ИТ, независимо от того, размер.
- **Интеллектуальный системы безопасности** — самый безопасный выпуске Windows когда-либо, а intelligent безопасности возможности, которые предназначены для совместной работы для улучшения защиты вашей организации.
- **Позволяет создать творческие и командную** - разблокирует, возникает творческие и командную для обеспечения максимальной эффективности при работе пользователей и сможет привлекательности.

Необходимо изучить различные способы можно развернуть в операционной системе Windows 10 и выберите нужную для вашей организации. В зависимости от вашей подписки Microsoft 365 Enterprise существует также Windows 10 служб и функций безопасности, которые помогут вам настроить для обеспечения наибольшей эффективности Windows 10.

Windows 10 позволяет эти стратегического бизнес-сценарии для Microsoft 365 для предприятия:

- обращение к опыту и знаниям сотрудников благодаря возможности находить и обрабатывать данные, файлы и идеи в организации, а также делиться ими;
- безопасная работа на любых устройствах где угодно и когда угодно для обеспечения эффективности при гибком стиле работы;
- беспроблемное применение средств контроля и реализация прозрачности согласно глобальным стандартам обеспечения соответствия требованиям;
- защита данных и снижение риска утери данных;
- Обнаружения и обеспечивает защиту от внешних угроз--монитор, отчетов и анализа активности быстро реагировать для обеспечения безопасности предприятия
- Защиты пользователей и учетных записей
- реализация в организации более эффективных средств защиты конфиденциальности и соответствия требованиям согласно GDPR.
- обновление программного обеспечения компьютера и других устройств до последней версии, снижение риска, связанного с нарушением безопасности, и увеличение эффективности ИТ-инфраструктуры.

Дополнительные сведения см. в статье [Цифровая трансформация с помощью Microsoft 365](http://transform.microsoft.com). 

>[!Note]
>Для развертывания Windows 10 Корпоративная и Office 365 профессиональный плюс вместе, а также перехода пользователей на [современные компьютеры](https://www.microsoft.com/microsoft-365/modern-desktop) см. статью [Центр развертывания современных компьютеров](http://aka.ms/howtoshift).
>

## <a name="windows-10-deployment"></a>Развертывание Windows 10

Существует несколько способов Windows 10 Enterprise можно развернуть для вашей организации. Здесь мы рассмотрим способ настройки и развертывания образа Windows 10 Enterprise через эти сценарии современных развертывания.

| Сценарий развертывания | Способы его использования |
|:--- |:--- |
| [С помощью System Center Configuration Manager, как обновление на месте](windows10-deploy-inplaceupgrade.md) | Установите этот флажок, если необходимо обновить Windows 7 или Windows 8.1 компьютеров в <a href="https://aka.ms/windows-10-release-information" target="_blank">текущей версии</a> Windows 10 Enterprise и на компьютерах в настоящее время управляются с помощью <a href="https://aka.ms/introtosccm" target="_blank">System Center Configuration Manager (текущий филиала)</a>. |
| [С помощью Windows автопилот](windows10-deploy-autopilot.md) | Установите этот флажок, если вы настраиваете новых компьютеров Windows, которые имеют Windows 10 Enterprise 1703 или более поздняя версия предварительно установленные версии. Конечные пользователи будут запустить программу установки с помощью нужную конфигурацию посредством ввода данных их работы и школы учетные данные учетной записи. |

Если эти сценарии развертывания не соответствует потребностям вашей организации, можно узнать о других сценариях и понять возможности и ограничения каждой из них в [сценарии развертывания Windows 10](https://docs.microsoft.com/windows/deployment/windows-10-deployment-scenarios). Можно также <a href="https://aka.ms/planforwin10deployment" target="_blank">план развертывания Windows 10</a> на свои собственные.

Вы можете Дополнительные сведения о Windows 10 с в этих статьях:

- [Страница продукта Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise)
- [Windows 10](https://docs.microsoft.com/windows/windows-10)
- [Развертывание и обновление Windows 10](https://docs.microsoft.com/windows/deployment/)


## <a name="additional-services-and-features"></a>Дополнительные службы и компоненты
В процессе развертывания корпоративной 10 Windows можно добавить эти дополнительные службы и компоненты.

### <a name="windows-analytics"></a>Windows Analytics

Windows использует данные диагностики для содержатся подробные, предусматривающей действие сведения, которые помогут вам получить углубленное рассмотрение эффективность работы и работоспособности устройств Windows 10 в вашей среде.

* Обновление проверки готовности к - готовность к обновлению можно переместить в Windows 10 и оставаться на связи с новой 10 обновлений Windows. 
* Соответствие Update - соответствия обновления предназначен для ИТ-администратору, чтобы получить единое представление всех своих устройств Windows 10, без требований к дополнительной инфраструктуры.
* Работоспособности устройств - позволяет работоспособности устройств проактивное обнаружение и устранение проблем оказывающих негативное воздействие конечных пользователей.

[Обзор аналитических Windows](https://docs.microsoft.com/windows/deployment/update/windows-analytics-overview) более подробные сведения.

### <a name="windows-security"></a>Безопасность Windows

Windows 10 предоставляет функции защиты от угроз, Справка защиты устройство и помощь в управлении доступом. Windows 10 вы получаете критические средства защиты ваше устройство справа от начала. Функции безопасности, такие как Windows Hello добавляет Microsoft 365 E3 для бизнеса, элемент управления приложения Защитник Windows и защита информации Windows. С E5 365 Microsoft вы получаете все защиты из Microsoft 365 E3 безопасности, а также функции обеспечения безопасности на основе облака и защиту от угроз дополнительные Защитник Windows. 

Чтобы узнать больше о функциональных возможностях безопасности, которые вы получаете с корпоративной 10 Windows, а также соответствующие get как развертывание, управление, Настройка и устранение неполадок трех основных ecurity функций, обратитесь к разделу [Шаг 5: развертывание Windows 10 Enterprise функции безопасности](windows10-enable-security-features.md).

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Как корпорация Майкрософт реализует Microsoft 365 корпоративный

Просмотр в корпорации Майкрософт и узнайте, как компания запланированных для развертывания и управление обновлениями для Windows 10, см.

- [Подготовка организации к простому развертыванию Windows 10](https://www.microsoft.com/itshowcase/windows10deployment?wt.mc_id=bmkg_itsc)
- [Внедрение модели "Windows как услуга" в Майкрософт](https://www.microsoft.com/itshowcase/Article/Content/851/Adopting-Windows-as-a-service-at-Microsoft)
- [Развертывание Windows 10 в Майкрософт путем обновления на месте](https://www.microsoft.com/itshowcase/Article/Content/668/Deploying-Windows-10-at-Microsoft-as-an-inplace-upgrade)
- [Обеспечение надежной аутентификации пользователей с помощью Windows Hello для бизнеса](https://www.microsoft.com/itshowcase/Article/Content/756/Implementing-strong-user-authentication-with-Windows-Hello-for-Business)
- [Развертывание Windows 10: советы от ИТ-специалистов Майкрософт](https://www.microsoft.com/itshowcase/Article/Content/951/Windows-10-deployment-tips-and-tricks-from-Microsoft-IT) (видео)
- [ATP в Защитнике Windows помогает определять современные угрозы](https://www.microsoft.com/itshowcase/Article/Content/854/Windows-Defender-ATP-helps-detect-sophisticated-threats)
- [Защита современного предприятия с помощью Защитника Windows и ATP в Защитнике Windows](https://www.microsoft.com/itshowcase/Article/Content/903/Securing-the-modern-enterprise-with-Windows-Defender-and-Windows-Defender-ATP) (видео)

## <a name="how-contoso-did-microsoft-365-enterprise"></a>Как корпорация Contoso реализовала Microsoft 365 корпоративный

В разделе как Contoso Corporation вымышленного, но представитель глобальной экономике бизнеса, [развернут Windows 10 Enterprise](contoso-win10.md).

![](./media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a>Следующее действие

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)| [Подготовка корпоративных 10 Windows в вашей организации](windows10-prepare-your-org.md) |
