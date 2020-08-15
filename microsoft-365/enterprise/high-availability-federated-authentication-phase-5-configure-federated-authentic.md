---
title: Этап 5 высокой доступности федеративных проверок подлинности 5 Настройка федеративной проверки подлинности для Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/25/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: Ent_Solutions
ms.assetid: 0f1dbf52-5bff-44cc-a264-1b48641af98f
description: 'Сводка: Настройка Azure AD Connect для вашей федеративной проверки подлинности с высоким уровнем доступности для Microsoft 365 в Microsoft Azure.'
ms.openlocfilehash: f00763487261b62940ac5def38d35158db77a699
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2020
ms.locfileid: "46693340"
---
# <a name="high-availability-federated-authentication-phase-5-configure-federated-authentication-for-microsoft-365"></a><span data-ttu-id="5de11-103">Этап 5 высокой доступности для федеративной проверки подлинности: Настройка федеративной проверки подлинности для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5de11-103">High availability federated authentication Phase 5: Configure federated authentication for Microsoft 365</span></span>

<span data-ttu-id="5de11-104">На последнем этапе развертывания федеративной проверки подлинности с высоким уровнем доступности для Microsoft 365 в службах инфраструктуры Azure можно получить и установить сертификат, выданный общедоступным центром сертификации, проверить конфигурацию, а затем установить и запустить Azure AD Connect на сервере синхронизации службы каталогов.</span><span class="sxs-lookup"><span data-stu-id="5de11-104">In this final phase of deploying high availability federated authentication for Microsoft 365 in Azure infrastructure services, you get and install a certificate issued by a public certification authority, verify your configuration, and then install and run Azure AD Connect on the directory synchronization server.</span></span> <span data-ttu-id="5de11-105">Azure AD Connect настраивает свою подписку на Microsoft 365 и прокси-серверы служб федерации Active Directory и прокси-серверов веб-приложений для федеративной проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="5de11-105">Azure AD Connect configures your Microsoft 365 subscription and your Active Directory Federation Services (AD FS) and web application proxy servers for federated authentication.</span></span>
  
<span data-ttu-id="5de11-106">[В статье Развертывание федеративной проверки подлинности с высоким уровнем доступности для Microsoft 365 в Azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md) для всех фаз.</span><span class="sxs-lookup"><span data-stu-id="5de11-106">See [Deploy high availability federated authentication for Microsoft 365 in Azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md) for all of the phases.</span></span>
  
## <a name="get-a-public-certificate-and-copy-it-to-the-directory-synchronization-server"></a><span data-ttu-id="5de11-107">Получение общедоступного сертификата и его копирование на сервер синхронизации каталогов</span><span class="sxs-lookup"><span data-stu-id="5de11-107">Get a public certificate and copy it to the directory synchronization server</span></span>

<span data-ttu-id="5de11-108">Получите цифровой сертификат из общедоступного центра сертификации со следующими свойствами:</span><span class="sxs-lookup"><span data-stu-id="5de11-108">Get a digital certificate from a public certification authority with the following properties:</span></span>
  
- <span data-ttu-id="5de11-109">Сертификат X.509 подходит для создания SSL-соединений.</span><span class="sxs-lookup"><span data-stu-id="5de11-109">An X.509 certificate suitable for creating SSL connections.</span></span>
    
- <span data-ttu-id="5de11-110">Расширенному свойству "Альтернативное имя субъекта" (SAN) присвоено полное доменное имя службы федерации (например, fs.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="5de11-110">The Subject Alternative Name (SAN) extended property is set to your federation service FQDN (example: fs.contoso.com).</span></span>
    
- <span data-ttu-id="5de11-111">Сертификат должен иметь закрытый ключ и формат PFX.</span><span class="sxs-lookup"><span data-stu-id="5de11-111">The certificate must have the private key and be stored in PFX format.</span></span>
    
<span data-ttu-id="5de11-p102">Кроме того, компьютеры и устройства организации должны доверять общедоступному центру сертификации, выдающему цифровой сертификат. Для этого в хранилище доверенных корневых центров сертификации на компьютерах и устройствах должен быть установлен корневой сертификат из общедоступного центра сертификации. На компьютерах с Microsoft Windows обычно установлен набор этих сертификатов из часто используемых центров сертификации. Если корневой сертификат из вашего общедоступного центра сертификации еще не установлен, разверните его на компьютерах и устройствах организации.</span><span class="sxs-lookup"><span data-stu-id="5de11-p102">Additionally, your organization computers and devices must trust the public certification authority that is issuing the digital certificate. This trust is established by having a root certificate from the public certification authority installed in the trusted root certification authorities store on your computers and devices. Computers running Microsoft Windows typically have a set of these types of certificates installed from commonly-used certification authorities. If the root certificate from your public certification authority is not already installed, you must deploy this to the computers and devices of your organization.</span></span>
  
<span data-ttu-id="5de11-116">Дополнительные сведения о требованиях к сертификатам для федеративной проверки подлинности см. в разделе [Предварительные требования для установки и настройки федерации](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-prerequisites#prerequisites-for-federation-installation-and-configuration).</span><span class="sxs-lookup"><span data-stu-id="5de11-116">For more information about certificate requirements for federated authentication, see [Prerequisites for federation installation and configuration](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-prerequisites#prerequisites-for-federation-installation-and-configuration).</span></span>
  
<span data-ttu-id="5de11-117">Получив сертификат, скопируйте его в папку на диске C: на сервере синхронизации службы каталогов.</span><span class="sxs-lookup"><span data-stu-id="5de11-117">When you receive the certificate, copy it to a folder on the C: drive of the directory synchronization server.</span></span> <span data-ttu-id="5de11-118">Например, назовите файл SSL. pfx и сохраните его в папке C: \\ certs на сервере синхронизации каталогов.</span><span class="sxs-lookup"><span data-stu-id="5de11-118">For example, name the file SSL.pfx and store it in the C:\\Certs folder on the directory synchronization server.</span></span>
  
## <a name="verify-your-configuration"></a><span data-ttu-id="5de11-119">Проверка конфигурации</span><span class="sxs-lookup"><span data-stu-id="5de11-119">Verify your configuration</span></span>

<span data-ttu-id="5de11-120">Теперь необходимо подготовиться к настройке Azure AD Connect и федеративной проверки подлинности для Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5de11-120">You should now be ready to configure Azure AD Connect and federated authentication for Microsoft 365.</span></span> <span data-ttu-id="5de11-121">Проверьте, так ли это, с помощью этого контрольного списка:</span><span class="sxs-lookup"><span data-stu-id="5de11-121">To ensure that you are, here is a checklist:</span></span>
  
- <span data-ttu-id="5de11-122">Общедоступный домен вашей организации добавляется в вашу подписку на Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5de11-122">Your organization's public domain is added to your Microsoft 365 subscription.</span></span>
    
- <span data-ttu-id="5de11-123">Учетные записи пользователей Microsoft 365 настроены на общедоступное доменное имя вашей организации и могут войти в систему.</span><span class="sxs-lookup"><span data-stu-id="5de11-123">Your organization's Microsoft 365 user accounts are configured to your organization's public domain name and can successfully sign in.</span></span>
    
- <span data-ttu-id="5de11-124">Вы определили полное доменное имя службы федерации на основе вашего общедоступного доменного имени.</span><span class="sxs-lookup"><span data-stu-id="5de11-124">You have determined a federation service FQDN based your public domain name.</span></span>
    
- <span data-ttu-id="5de11-125">Запись A общедоступного домена DNS для полного доменного имени службы федерации указывает на общедоступный IP-адрес внешнего балансировщика нагрузки Azure для прокси-серверов веб-приложений.</span><span class="sxs-lookup"><span data-stu-id="5de11-125">A public DNS A record for your federation service FQDN points to the public IP address of the Internet-facing Azure load balancer for the web application proxy servers.</span></span>
    
- <span data-ttu-id="5de11-126">Запись A частного домена DNS для полного доменного имени службы федерации указывает на частный IP-адрес внутреннего балансировщика нагрузки Azure для серверов AD FS.</span><span class="sxs-lookup"><span data-stu-id="5de11-126">A private DNS A record for your federation service FQDN points to the private IP address of the internal Azure load balancer for the AD FS servers.</span></span>
    
- <span data-ttu-id="5de11-127">Общедоступный центр сертификации — цифровой сертификат соединений, подходящие для SSL-соединений со службой SAN, настроенной на полное доменное имя службы федерации — это PFX-файл, хранящийся на сервере синхронизации службы каталогов.</span><span class="sxs-lookup"><span data-stu-id="5de11-127">A public certification authority-isssued digital certificate suitable for SSL connections with the SAN set to your federation service FQDN is a PFX file stored on your directory synchronization server.</span></span>
    
- <span data-ttu-id="5de11-128">Корневой сертификат для общедоступного центра сертификации установлен в хранилище доверенных корневых центров сертификации на компьютерах и устройствах.</span><span class="sxs-lookup"><span data-stu-id="5de11-128">The root certificate for the public certification authority is installed in the Trusted Root Certification Authorities store on your computers and devices.</span></span>
    
<span data-ttu-id="5de11-129">Ниже приведен пример для организации Contoso.</span><span class="sxs-lookup"><span data-stu-id="5de11-129">Here is an example for the Contoso organization:</span></span>
  
<span data-ttu-id="5de11-130">**Пример конфигурации инфраструктуры федеративной проверки подлинности с высоким уровнем доступности в Azure**</span><span class="sxs-lookup"><span data-stu-id="5de11-130">**An example configuration for a high availability federated authentication infrastructure in Azure**</span></span>

![Пример конфигурации инфраструктуры федеративной проверки подлинности Microsoft 365 с высоким уровнем доступности в Azure](../media/ac1a6a0d-0156-4407-9336-6e4cd6db8633.png)
  
## <a name="run-azure-ad-connect-to-configure-federated-authentication"></a><span data-ttu-id="5de11-132">Настройка федеративной проверки подлинности с помощью Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="5de11-132">Run Azure AD Connect to configure federated authentication</span></span>

<span data-ttu-id="5de11-133">Средство Azure AD Connect позволяет настроить серверы AD FS, прокси-серверы веб-приложений и Microsoft 365 для федеративной проверки подлинности, выполнив следующие действия:</span><span class="sxs-lookup"><span data-stu-id="5de11-133">The Azure AD Connect tool configures the AD FS servers, the web application proxy servers, and Microsoft 365 for federated authentication with these steps:</span></span>
  
1. <span data-ttu-id="5de11-134">Создайте подключение к удаленному рабочему столу сервера синхронизации каталогов с учетной записью домена с правами локального администратора.</span><span class="sxs-lookup"><span data-stu-id="5de11-134">Create a remote desktop connection to your directory synchronization server with a domain account that has local administrator privileges.</span></span>
    
2. <span data-ttu-id="5de11-135">На рабочем столе сервера синхронизации службы каталогов откройте Internet Explorer и перейдите по адресу [https://aka.ms/aadconnect](https://aka.ms/aadconnect) .</span><span class="sxs-lookup"><span data-stu-id="5de11-135">From the desktop of the directory synchronization server, open Internet Explorer and go to [https://aka.ms/aadconnect](https://aka.ms/aadconnect).</span></span>
    
3. <span data-ttu-id="5de11-136">На странице **Microsoft Azure Active Directory Connect** нажмите **Скачать**, а затем **Запустить**.</span><span class="sxs-lookup"><span data-stu-id="5de11-136">On the **Microsoft Azure Active Directory Connect** page, click **Download**, and then click **Run**.</span></span>
    
4. <span data-ttu-id="5de11-137">На странице **Добро пожаловать в Azure AD Connect** установите флажок **Принимаю** и нажмите кнопку **Продолжить**.</span><span class="sxs-lookup"><span data-stu-id="5de11-137">On the **Welcome to Azure AD Connect** page, click **I agree**, and then click **Continue.**</span></span>
    
5. <span data-ttu-id="5de11-138">На странице **Стандартные параметры** нажмите кнопку **Настроить**.</span><span class="sxs-lookup"><span data-stu-id="5de11-138">On the **Express Settings** page, click **Customize**.</span></span>
    
6. <span data-ttu-id="5de11-139">На странице **Установка обязательных компонентов** нажмите кнопку **Установить**.</span><span class="sxs-lookup"><span data-stu-id="5de11-139">On the **Install required components** page, click **Install**.</span></span>
    
7. <span data-ttu-id="5de11-140">На странице **Вход пользователя** выберите **Федерация с AD FS** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="5de11-140">On the **User sign-in** page, click **Federation with AD FS**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="5de11-141">На странице **Подключение к Azure AD** введите имя и пароль учетной записи глобального администратора для своей подписки на Microsoft 365, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="5de11-141">On the **Connect to Azure AD** page, type the name and password of a global administrator account for your Microsoft 365 subscription, and then click **Next**.</span></span>
    
9. <span data-ttu-id="5de11-142">На странице **Подключение каталогов** убедитесь, что локальный лес доменных служб Active Directory (AD DS) выбран в **лесу**, введите имя и пароль учетной записи администратора домена, нажмите кнопку **Добавить каталог**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="5de11-142">On the **Connect your directories** page, ensure that your on-premises Active Directory Domain Services (AD DS) forest is selected in **Forest**, type the name and password of a domain administrator account, click **Add Directory**, and then click **Next**.</span></span>
    
10. <span data-ttu-id="5de11-143">На странице **Настройка входа в Azure AD** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="5de11-143">On the **Azure AD sign-in configuration** page, click **Next**.</span></span>
    
11. <span data-ttu-id="5de11-144">На странице **Фильтрация доменов и подразделений** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="5de11-144">On the **Domain and OU filtering** page, click **Next**.</span></span>
    
12. <span data-ttu-id="5de11-145">На странице **Уникальная идентификация пользователей** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="5de11-145">On the **Uniquely identifying your users** page, click **Next**.</span></span>
    
13. <span data-ttu-id="5de11-146">На **Фильтрация пользователей и устройств** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="5de11-146">On the **Filter users and devices** page, click **Next**.</span></span>
    
14. <span data-ttu-id="5de11-147">На странице **Дополнительные возможности** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="5de11-147">On the **Optional features** page, click **Next**.</span></span>
    
15. <span data-ttu-id="5de11-148">На странице **Ферма AD FS** нажмите кнопку **Настроить новую ферму AD FS**.</span><span class="sxs-lookup"><span data-stu-id="5de11-148">On the **AD FS farm** page, click **Configure a new AD FS farm**.</span></span>
    
16. <span data-ttu-id="5de11-149">Нажмите кнопку **Обзор** и укажите расположение и имя SSL-сертификата из общедоступного центра сертификации.</span><span class="sxs-lookup"><span data-stu-id="5de11-149">Click **Browse** and specify the location and name of the SSL certificate from the public certification authority.</span></span>
    
17. <span data-ttu-id="5de11-150">Введите пароль сертификата и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="5de11-150">When prompted, type the certificate password, and then click **OK**.</span></span>
    
18. <span data-ttu-id="5de11-151">Убедитесь, что в полях **Имя субъекта** и **Имя службы федерации** указано полное доменное имя службы федерации, и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="5de11-151">Verify that the **Subject Name** and **Federation Service Name** are set to your federation service FQDN, and then click **Next**.</span></span>
    
19. <span data-ttu-id="5de11-152">На странице **Серверы AD FS** введите имя первого сервера AD FS (таблица M, элемент 4, "Имя виртуальной машины") и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="5de11-152">On the **AD FS servers** page, type your first AD FS server's name (Table M - Item 4 - Virtual machine name column), and then click **Add**.</span></span>
    
20. <span data-ttu-id="5de11-153">Введите имя второго сервера AD FS (таблица M, элемент 5, столбец "Имя виртуальной машины"), нажмите кнопку **Добавить**, а затем кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="5de11-153">Type your second AD FS server's name (Table M - Item 5 - Virtual machine name column), click **Add**, and then click **Next**.</span></span>
    
21. <span data-ttu-id="5de11-154">На странице **Прокси-серверы веб-приложений** введите имя первого прокси-сервера веб приложений (таблица M, элемент 6, столбец "Имя виртуальной машины") и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="5de11-154">On the **Web Application Proxy servers** page, type your first web application proxy server's name (Table M - Item 6 - Virtual machine name column), and then click **Add**.</span></span>
    
22. <span data-ttu-id="5de11-155">Введите имя второго прокси-сервера веб-приложений (таблица M, элемент 7, столбец "Имя виртуальной машины"), нажмите кнопку **Добавить**, а затем кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="5de11-155">Type your second web application proxy server's name (Table M - Item 7 - Virtual machine name column), click **Add**, and then click **Next**.</span></span>
    
23. <span data-ttu-id="5de11-156">На странице **Учетные данные администратора домена** введите имя пользователя и пароль администратора домена и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="5de11-156">On the **Domain Administrator credentials** page, type the user name and password of a domain administrator account, and then click **Next**.</span></span>
    
24. <span data-ttu-id="5de11-157">На странице **Учетная запись службы AD FS** введите имя пользователя и пароль администратора предприятия и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="5de11-157">On the **AD FS service account** page, type the user name and password of an enterprise administrator account, and then click **Next**.</span></span>
    
25. <span data-ttu-id="5de11-158">На странице **Домен Azure AD**, в разделе **Домен**, выберите DNS-имя домена организации и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="5de11-158">On the **Azure AD Domain** page, in **Domain**, select your organization's DNS domain name, and then click **Next**.</span></span>
    
26. <span data-ttu-id="5de11-159">На странице **Готово к настройке** нажмите кнопку **Установить**.</span><span class="sxs-lookup"><span data-stu-id="5de11-159">On the **Ready to configure** page, click **Install**.</span></span>
    
27. <span data-ttu-id="5de11-p105">На странице **Установка завершена** нажмите **Проверить**. Появятся два сообщения о том, что конфигурации интрасети и Интернета проверены.</span><span class="sxs-lookup"><span data-stu-id="5de11-p105">On the **Installation complete** page, click **Verify**. You should see two messages indicating that both the intranet and Internet configuration was successfully verified.</span></span>
    
  - <span data-ttu-id="5de11-162">В сообщении интрасети должен быть указан частный IP-адрес внутреннего балансировщика нагрузки Azure для серверов AD FS.</span><span class="sxs-lookup"><span data-stu-id="5de11-162">The intranet message should list the private IP address of your Azure internal load balancer for your AD FS servers.</span></span>
    
  - <span data-ttu-id="5de11-163">В сообщении Интернета должен быть указан публичный IP-адрес внешнего балансировщика нагрузки Azure для прокси-серверов веб-приложений.</span><span class="sxs-lookup"><span data-stu-id="5de11-163">The Internet message should list the public IP address of your Azure Internet-facing load balancer for your web application proxy servers.</span></span>
    
28. <span data-ttu-id="5de11-164">На странице **Установка завершена** нажмите **Выход**.</span><span class="sxs-lookup"><span data-stu-id="5de11-164">On the **Installation complete** page, click **Exit**.</span></span>
    
<span data-ttu-id="5de11-165">Ниже приводится окончательная конфигурация с именами-заполнителями для серверов.</span><span class="sxs-lookup"><span data-stu-id="5de11-165">Here is the final configuration, with placeholder names for the servers.</span></span>
  
<span data-ttu-id="5de11-166">**Этап 5. Окончательная конфигурация инфраструктуры федеративной проверки подлинности с высоким уровнем доступности в Azure**</span><span class="sxs-lookup"><span data-stu-id="5de11-166">**Phase 5: The final configuration of a high availability federated authentication infrastructure in Azure**</span></span>

![Последняя конфигурация инфраструктуры федеративной проверки подлинности Microsoft 365 в Azure](../media/c5da470a-f2aa-489a-a050-df09b4d641df.png)
  
<span data-ttu-id="5de11-168">Инфраструктура федеративной проверки подлинности с высоким уровнем доступности для Microsoft 365 в Azure завершена.</span><span class="sxs-lookup"><span data-stu-id="5de11-168">Your high availability federated authentication infrastructure for Microsoft 365 in Azure is complete.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="5de11-169">См. также</span><span class="sxs-lookup"><span data-stu-id="5de11-169">See Also</span></span>

[<span data-ttu-id="5de11-170">Развертывание федеративной проверки подлинности для обеспечения высокой доступности Microsoft 365 в Azure</span><span class="sxs-lookup"><span data-stu-id="5de11-170">Deploy high availability federated authentication for Microsoft 365 in Azure</span></span>](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md)
  
[<span data-ttu-id="5de11-171">Федеративная идентификация для среды разработки и тестирования Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5de11-171">Federated identity for your Microsoft 365 dev/test environment</span></span>](federated-identity-for-your-microsoft-365-dev-test-environment.md)
  
[<span data-ttu-id="5de11-172">Центр архитектуры и решений Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5de11-172">Microsoft 365 solution and architecture center</span></span>](../solutions/solution-architecture-center.md)

[<span data-ttu-id="5de11-173">Федеративная идентификация для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5de11-173">Federated identity for Microsoft 365</span></span>](https://support.office.com/article/Understanding-Office-365-identity-and-Azure-Active-Directory-06a189e7-5ec6-4af2-94bf-a22ea225a7a9#bk_federated)


