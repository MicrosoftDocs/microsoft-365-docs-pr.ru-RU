---
title: Настройка пробной лабораторной среды Майкрософт для защиты от угроз
description: Доступ к центру обеспечения безопасности Microsoft 365 и Настройка лабораторной среды лаборатории Майкрософт по защите от угроз
keywords: Пробная версия системы защиты от угроз Майкрософт, проверка Microsoft Threat Protection, Настройка лаборатории оценки защиты от угроз Майкрософт
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 50557b0824999f0220af4d12b906b0274db4471e
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2020
ms.locfileid: "44049619"
---
# <a name="set-up-your-microsoft-threat-protection-trial-lab-environment"></a>Настройка пробной лабораторной среды Майкрософт для защиты от угроз 

**Область применения:**
- Защита от угроз (Майкрософт) 


Создание пробной лабораторной среды Майкрософт для защиты от угроз и развертывание выполняется в три этапа:

<br>
<table border="0" width="100%" align="center">
  <tr style="text-align:center;">
    <td align="center" style="width:25%; border:0;" >
      <a href= "https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval?view=o365-worldwide"> 
        <img src="../../media/prepare.png" alt="Prepare your Microsoft Threat Protection trial lab environment" title="Подготовка лаборатории оценки Microsoft Threat protection" />
      <br/>Этап 1: подготовка</a><br>
    </td>
     <td align="center"bgcolor="#d5f5e3">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/setup-mtpeval?view=o365-worldwide">
        <img src="../../media/setup.png" alt="Set up your Microsoft Threat Protection trial lab environment" title="Настройка лаборатории оценки Microsoft Threat protection" />
      <br/>Этап 2: Настройка</a><br>
    </td>
    <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/config-mtpeval?view=o365-worldwide">
        <img src="../../media/config-onboard.png" alt="
Configure each Microsoft Threat Protection pillar for your Microsoft Threat Protection trial lab environment and onboard your endpoints" title="
Настройте каждый из принципов защиты от угроз Майкрософт для лаборатории пробной среды Майкрософт по защите от угроз и конечных точек." />
      <br/>Этап 3: Настройка встроенного &</a><br>
</td>


  </tr>
</table>

В данный момент вы настраиваете этап настройки. Выполните начальные действия, чтобы получить доступ к центру безопасности Microsoft 365, а затем настройте свою лабораторную среду.

Подпишитесь на Office 365 или Azure Active Directory, чтобы создать клиент *. onmicrosoft.com* , который вы можете использовать для подписки на лицензию Майкрософт 365. 

>[!NOTE]
>Если у вас уже есть подписка на Office 365 или Azure Active Directory, вы можете пропустить этапы создания пробных клиентов Office 365

На этом этапе вы найдете следующие руководства:
- Создание пробного клиента Office 365
- Включение пробной подписки на Microsoft 365


## <a name="create-an-office-365-e5-trial-tenant"></a>Создание пробного клиента Office 365
>[!NOTE]
>Если у вас уже есть подписка на Office 365 или Azure Active Directory, вы можете пропустить этапы создания пробных клиентов Office 365

1. Перейдите на [портал продуктов Office 365](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab) и выберите **бесплатную пробную версию**.
![Of_page изображений](../../media/mtp-eval-9.png) <br>
  
2. Выполните пробную регистрацию, указав свой адрес электронной почты (персональный или корпоративный). Нажмите кнопку **Настройка учетной записи**.
![Of_page изображений](../../media/mtp-eval-10.png) <br> 

3. Введите имя, фамилию, номер рабочего телефона, название компании, размер и страну или регион.  
<br>![Of_page изображений](../../media/mtp-eval-11.png) <br>
>[!NOTE]
>Страна или регион, которые вы настроили, определяет регион центра обработки данных, в котором будет размещаться Office 365.
  
4. Выберите предпочтения проверки: в текстовом сообщении или вызове. Нажмите кнопку **Отправить проверочный код**. 
![Of_page изображений](../../media/mtp-eval-12.png) <br>

5. Задайте имя пользовательского домена для клиента, а затем нажмите кнопку **Далее**.
<br>![Of_page изображений](../../media/mtp-eval-13.png) <br>
 
6. Настройте первое удостоверение, которое будет глобальным администратором клиента. Введите **имя** и **пароль**. Нажмите кнопку **Зарегистрироваться**.
![Of_page изображений](../../media/mtp-eval-14.png) <br>
c
7. Нажмите кнопку **Перейти к программе установки** , чтобы завершить подготовку пробного клиента Office 365 в Office.
<br>![Of_page изображений](../../media/mtp-eval-15.png) <br>

8. Подключите корпоративный домен к клиенту Office 365. Необязательно Выберите **подключить домен, который вы уже владеете** , и введите имя своего домена. Нажмите кнопку **Далее**.
<br>![Of_page изображений](../../media/mtp-eval-16.png) <br>
 
9. Чтобы проверить владение доменом, необходимо добавить запись TXT или MX. Добавив запись TXT или MX в свой домен, нажмите кнопку **проверить**.
<br>![Of_page изображений](../../media/mtp-eval-17.png) <br>
 
10. Необязательно Создайте дополнительные учетные записи пользователей для клиента. Вы можете пропустить этот шаг, нажав кнопку **Далее**.
![Of_page изображений](../../media/mtp-eval-18.png) <br>
 
11. Необязательно Скачайте приложения Office. Нажмите кнопку **Далее** , чтобы пропустить этот шаг. 
<br>![Of_page изображений](../../media/mtp-eval-19.png) <br>

12. Необязательно Перенос сообщений электронной почты. Опять же, вы можете пропустить этот шаг.
<br>![Of_page изображений](../../media/mtp-eval-20.png) <br>
 
13. Выберите веб-службы. Выберите **Exchange** и нажмите кнопку **Далее**. 
<br>![Of_page изображений](../../media/mtp-eval-21.png) <br>

14. Добавьте записи MX, CNAME и TXT в свой домен. По завершении нажмите кнопку **проверить**.
<br>![Of_page изображений](../../media/mtp-eval-22.png) <br>
 
15. Поздравляем, вы завершили подготовку клиента Office 365.
<br>![Of_page изображений](../../media/mtp-eval-23.png) <br>

## <a name="enable-microsoft-365-trial-subscription"></a>Включение пробной подписки на Microsoft 365

>[!NOTE]
>При регистрации пробной версии вы получите 25 пользовательских лицензий, которые будут использоваться в течение месяца. Сведения о том, [как испытать или приобрести подписку на M365](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365?view=o365-worldwide#try-or-buy-a-microsoft-365-subscription-1) .

1. В [центре администрирования Microsoft 365](https://admin.microsoft.com/)щелкните **выставление счетов** , а затем перейдите к разделу **Услуги по приобретению**.

2. Выберите **Microsoft 365** и щелкните **начать бесплатную пробную версию**. 
![Of_page изображений](../../media/mtp-eval-24.png) <br>

3. Выберите предпочтения проверки: в текстовом сообщении или вызове. После того как вы решили, введите номер телефона, выберите пункт **текстовые** или **позвонить мне** в зависимости от выбранного варианта.
![Of_page изображений](../../media/mtp-eval-25.png) <br>
 
4. Введите код проверки и нажмите кнопку **начать бесплатную пробную версию**. 
<br>![Of_page изображений](../../media/mtp-eval-26.png) <br>

5. Нажмите кнопку **проверить** , чтобы подтвердить пробную версию Microsoft 365.
<br>![Of_page изображений](../../media/mtp-eval-27.png) <br>
 
6. Перейдите в**Users** > раздел >  **центр администрирования Microsoft 365****Активные пользователи**. Выберите свою учетную запись пользователя, выберите **Управление лицензиями на продукты**, затем замените лицензию из Office 365 в ~ на **Microsoft 365**. Нажмите кнопку **Сохранить**.
![Of_page изображений](../../media/mtp-eval-28.png) <br>
 
7. Снова выберите учетную запись глобального администратора и нажмите кнопку **Управление именем пользователя**.
<br>![Of_page изображений](../../media/mtp-eval-29.png) <br>

8. Необязательно Замените домен с *onmicrosoft.com* на свой домен в зависимости от того, что было выбрано на предыдущих шагах. Нажмите кнопку **Сохранить изменения**.
<br>![Of_page изображений](../../media/mtp-eval-30.png) <br>



## <a name="next-step"></a>Следующий этап
||| |:-------|:-----| конфиг-онбоард. png) <br>[Этап 3: настройка & Onboard](config-mtpeval.md) | Настройте каждый из принципов защиты от угроз Майкрософт для испытательной лаборатории Microsoft Threat Protection и встроенных конечных точек.
