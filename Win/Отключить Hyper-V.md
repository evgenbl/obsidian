Некоторые сторонние приложения не могут работать, когда используется Hyper-V, что означает,  

  что они не смогут работать при включенной WSL . К сожалению, к ним относятся       VMWare  и  

 Virtual Box. 

Запустить в терминале: 

bcdedit /set hypervisorlaunchtype off 

Источник-ссылка: [https://lumpics.ru/does-not-start-virtualbox/](https://lumpics.ru/does-not-start-virtualbox/)