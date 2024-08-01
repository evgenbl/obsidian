Что ж, многие пользователи либо удаленно используют серверы Windows, либо серверы Microsoft без графического интерфейса. Или, как правило, те, кто не хочет проходить через различные шаги графического интерфейса для включения IIS, могут использовать командную строку. 

- Щелкните правой кнопкой мыши кнопку «Пуск» в Windows 11. 
    
- Выберите Терминал Windows (администратор) 
    
- Вставьте приведенную ниже команду и нажмите клавишу Enter: 
    

_________________________________________________________________ 

Enable-WindowsOptionalFeature -Online -FeatureName IIS-WebServerRole, IIS-WebServer, IIS-CommonHttpFeatures, IIS-ManagementConsole, IIS-HttpErrors, IIS-HttpRedirect, IIS-WindowsAuthentication, IIS-StaticContent, IIS-DefaultDocument, IIS-HttpCompressionStatic, IIS-DirectoryBrowsing 

_________________________________________________________________ 

После этого нажмите клавишу Y, чтобы перезагрузить и правильно интегрировать информационную систему Интернета в Windows 11. 

Команда для отключения 

Когда вам больше не нужен IIS, его можно отключить с помощью командной строки, вставить заданную команду в Терминал Windows и нажать клавишу Enter, чтобы продолжить. 

Disable-WindowsOptionalFeature -Online -FeatureName IIS-WebServerRole, IIS-WebServer 

Источник <[https://www.how2shout.com/how-to/how-to-enable-iis-internet-information-services-on-windows-11.html](https://www.how2shout.com/how-to/how-to-enable-iis-internet-information-services-on-windows-11.html)>