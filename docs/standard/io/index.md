---
title: "Файловый и потоковый ввод-вывод"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- IO namespace
- files, I/O
- System.IO namespace
- I/O [.NET Framework]
- streams, I/O
- data streams, I/O
ms.assetid: 4f4a33a9-66b7-4cd7-a285-4ad3e4276cd2
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: e9ebd1a11684afaa143d1f016f31e0a29a3478db
ms.sourcegitcommit: ba765893e3efcece67d99fd6d5ce0074b050d1d9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/02/2018
---
# <a name="file-and-stream-io"></a>Файловый и потоковый ввод-вывод
Файловый и потоковый ввод-вывод относятся к передаче данных с носителя информации или на него. В .NET Framework пространства имен `System.IO` содержат типы, которые обеспечивают как синхронные, так и асинхронные операции чтения и записи для потоков и файлов. Кроме того, эти пространства имен содержат типы, выполняющие сжатие и распаковку файлов, а также типы, которые обеспечивают взаимодействие через каналы и последовательные порты.  
  
 Файл — это упорядоченная и именованная последовательность байтов, имеющая постоянное хранилище. При работе с файлами используются пути к каталогам, запоминающие устройства, а также имена файлов и каталогов. В отличие от файла, поток — это последовательность байтов, которую можно использовать для записи или чтения из вспомогательного запоминающего устройства, являющегося одним из устройств хранения информации (например, дисков или памяти). Есть несколько видов запоминающих устройств, отличных от дисков, и существует несколько видов потоков, помимо файловых потоков, например сетевые потоки, потоки памяти и потоки каналов.  
  
## <a name="files-and-directories"></a>Файлы и каталоги  
 Типы в пространстве имен <xref:System.IO?displayProperty=nameWithType> можно использовать для взаимодействия с файлами и каталогами. Например, можно получать и задавать свойства файлов и каталогов, а также извлекать коллекции файлов и каталогов на основе критерия поиска.  
  
 Ниже перечислены некоторые часто используемые классы для файлов и каталогов:  
  
-   <xref:System.IO.File> предоставляет статические методы для создания, копирования, удаления, перемещения и открытия файлов, а также помогает создать объект <xref:System.IO.FileStream>.  
  
-   <xref:System.IO.FileInfo> предоставляет методы экземпляра для создания, копирования, удаления, перемещения и открытия файлов, а также помогает создать объект <xref:System.IO.FileStream>.  
  
-   <xref:System.IO.Directory> предоставляет статические методы для создания, перемещения и перечисления в каталогах и подкаталогах.  
  
-   <xref:System.IO.DirectoryInfo> предоставляет методы экземпляра для создания, перемещения и перечисления в каталогах и подкаталогах.  
  
-   <xref:System.IO.Path> предоставляет методы и свойства для обработки строк каталогов межплатформенным способом.  
  
 Помимо использования этих классов, пользователи Visual Basic могут использовать методы и свойства, предоставляемые классом <xref:Microsoft.VisualBasic.FileIO.FileSystem?displayProperty=nameWithType> для файлового ввода-вывода.  
  
 См. разделы [Практическое руководство. Копирование каталогов](../../../docs/standard/io/how-to-copy-directories.md), [Практическое руководство. Создание списка каталогов](http://msdn.microsoft.com/library/4d2772b1-b991-4532-a8a6-6ef733277e69) и [Практическое руководство. Перечисление каталогов и файлов](../../../docs/standard/io/how-to-enumerate-directories-and-files.md).  
  
## <a name="streams"></a>Потоки  
 Абстрактный базовый класс <xref:System.IO.Stream> поддерживает чтение и запись байтов. Все классы, представляющие потоки, являются производными от класса <xref:System.IO.Stream>. Класс <xref:System.IO.Stream> и его производные классы обеспечивают общий способ просмотра источников данных и хранилищ объектов, а также изолируют программиста от специфических особенностей операционной системы и базовых устройств.  
  
 Потоки включают три основные операции:  
  
-   Чтение — перенос информации из потока в структуру данных, такую как массив байтов.  
  
-   Запись — перенос данных в поток из источника данных.  
  
-   Поиск — определение и изменение текущей позиции внутри потока.  
  
 В зависимости от базового источника или хранилища данных поток может поддерживать лишь некоторые из этих возможностей. Например, класс <xref:System.IO.Pipes.PipeStream> не поддерживает поиск. Свойства <xref:System.IO.Stream.CanRead%2A>, <xref:System.IO.Stream.CanWrite%2A> и <xref:System.IO.Stream.CanSeek%2A> потока определяют операции, поддерживаемые потоком.  
  
 Ниже перечислены некоторые часто используемые классы потока:  
  
-   <xref:System.IO.FileStream> — для чтения и записи в файл.  
  
-   <xref:System.IO.IsolatedStorage.IsolatedStorageFileStream> — для чтения и записи в файл в изолированном хранилище.  
  
-   <xref:System.IO.MemoryStream> — для чтения и записи в память в качестве резервного хранилища.  
  
-   <xref:System.IO.BufferedStream> — для повышения быстродействия операций чтения и записи.  
  
-   <xref:System.Net.Sockets.NetworkStream> — для чтения и записи на сетевые сокеты.  
  
-   <xref:System.IO.Pipes.PipeStream> — для чтения и записи в анонимные и именованные каналы.  
  
-   <xref:System.Security.Cryptography.CryptoStream> — для связи потоков данных с криптографическими преобразованиями.  
  
 Пример асинхронной работы с потоками см. в разделе [Асинхронный файловый ввод-вывод](../../../docs/standard/io/asynchronous-file-i-o.md).  
  
## <a name="readers-and-writers"></a>Средства чтения и записи  
 Пространство имен <xref:System.IO?displayProperty=nameWithType> также предоставляет типы для чтения закодированных символов из потоков и их записи в потоки. Как правило, потоки предназначены для ввода и вывода байтов. Типы чтения и записи обрабатывают преобразование закодированных символов в байты или из байтов, чтобы поток мог завершить операцию. Каждый класс чтения и записи связан с потоком, который можно получить с помощью свойства класса `BaseStream`.  
  
 Ниже перечислены некоторые часто используемые классы для чтения и записи:  
  
-   <xref:System.IO.BinaryReader> и <xref:System.IO.BinaryWriter> — для чтения и записи простых типов данных, таких как двоичные значения.  
  
-   <xref:System.IO.StreamReader> и <xref:System.IO.StreamWriter> — для чтения и записи символов с использованием закодированного значения для преобразования символов в байты или из байтов.  
  
-   <xref:System.IO.StringReader> и <xref:System.IO.StringWriter> — для чтения и записи символов в строки или из строк.  
  
-   <xref:System.IO.TextReader> и <xref:System.IO.TextWriter> используются в качестве абстрактных базовых классов для других средств чтения и записи, которые считывают и записывают символы и строки, а не двоичные данные.  
  
 См. разделы [Практическое руководство. Считывание текста из файла](../../../docs/standard/io/how-to-read-text-from-a-file.md), [Практическое руководство. Запись текста в файл](../../../docs/standard/io/how-to-write-text-to-a-file.md), [Практическое руководство. Считывание символов из строки](../../../docs/standard/io/how-to-read-characters-from-a-string.md) и [Практическое руководство. Запись символов в строку](../../../docs/standard/io/how-to-write-characters-to-a-string.md).  
  
## <a name="asynchronous-io-operations"></a>Асинхронные операции ввода-вывода  
 Чтение и запись больших объемов данных может быть ресурсоемкой. Эти задачи необходимо выполнять асинхронно, если приложение должно продолжать отвечать на запросы пользователя. В случае синхронных операций ввода-вывода поток пользовательского интерфейса будет заблокирован до тех пор, пока ресурсоемкая операция не завершится.  При разработке приложений для [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] используйте асинхронные операции ввода-вывода, чтобы не создавалось впечатления, что приложение прекратило свою работу.  
  
 Имена асинхронных элементов содержат `Async`, например: <xref:System.IO.Stream.CopyToAsync%2A>, <xref:System.IO.Stream.FlushAsync%2A>, <xref:System.IO.Stream.ReadAsync%2A> и <xref:System.IO.Stream.WriteAsync%2A>. Используйте эти методы с ключевыми словами `async` и `await`.  
  
 Дополнительные сведения см. в разделе [Асинхронный файловый ввод-вывод](../../../docs/standard/io/asynchronous-file-i-o.md).  
  
## <a name="compression"></a>Сжатие  
 Сжатием называется процесс сокращения размера сохраняемого файла. Распаковка — это процесс извлечения содержимого сжатого файла, что приводит его в формат, пригодный для использования. Пространство имен <xref:System.IO.Compression?displayProperty=nameWithType> содержит типы для сжатия и распаковки файлов и потоков.  
  
 При сжатии и распаковке файлов и потоков часто используются следующие классы:  
  
-   <xref:System.IO.Compression.ZipArchive> — для создания и восстановления содержимого ZIP-архива.  
  
-   <xref:System.IO.Compression.ZipArchiveEntry> — для представления сжатого файла.  
  
-   <xref:System.IO.Compression.ZipFile> — для создания, извлечения и открытия сжатого пакета.  
  
-   <xref:System.IO.Compression.ZipFileExtensions> — для создания и извлечения содержимого из сжатого пакета.  
  
-   <xref:System.IO.Compression.DeflateStream> — для сжатия и распаковки потоков с помощью алгоритма Deflate.  
  
-   <xref:System.IO.Compression.GZipStream> — для сжатия и распаковки потоков в формате gzip.  
  
 См. раздел [Практическое руководство. Сжатие и извлечение файлов](../../../docs/standard/io/how-to-compress-and-extract-files.md).  
  
## <a name="isolated-storage"></a>Изолированное хранилище  
 Изолированное хранилище — это механизм хранения данных, обеспечивающий изоляцию и безопасность путем определения стандартизованных способов сопоставления кода с хранимыми данными. Хранилище предоставляет виртуальную файловую систему, изолированную по пользователю, сборке и (необязательно) домену. Изолированное хранилище особенно полезно в том случае, когда приложение не имеет разрешения на доступ к файлам пользователя. Можно сохранить параметры или файлы для приложения таким способом, который контролируется политикой безопасности компьютера.  
  
 Изолированное хранилище недоступно для приложений [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]; вместо этого используйте классы данных приложения в пространстве имен [Windows.Storage](/uwp/api/Windows.Storage). Дополнительные сведения см. в статье [Данные приложения](/previous-versions/windows/apps/hh464917(v=win.10)) в Центре разработки для Windows.  
  
 Часто используются следующие классы, реализующие изолированное хранилище:  
  
-   <xref:System.IO.IsolatedStorage.IsolatedStorage> предоставляет базовый класс для реализации изолированного хранилища.  
  
-   <xref:System.IO.IsolatedStorage.IsolatedStorageFile> предоставляет область изолированного хранилища, в которой содержатся файлы и каталоги.  
  
-   <xref:System.IO.IsolatedStorage.IsolatedStorageFileStream> представляет файл в изолированном хранилище.  
  
 См. раздел [Изолированное хранилище](../../../docs/standard/io/isolated-storage.md).  
  
## <a name="io-operations-in-windows-store-apps"></a>Операции ввода-вывода в приложениях для Магазина Windows  
 [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)] содержат множество типов для чтения и записи в потоки, однако этот набор содержит не все типы ввода-вывода платформы .NET Framework.  
  
 Следует отметить некоторые важные различия в использовании операций ввода-вывода для приложений в стиле [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]:  
  
-   Специальные типы, относящиеся к операциям с файлами, такие как <xref:System.IO.File>, <xref:System.IO.FileInfo>, <xref:System.IO.Directory> и <xref:System.IO.DirectoryInfo>, не включены в [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)]. Вместо этого используйте типы в пространстве имен [Windows.Storage](http://msdn.microsoft.com/library/windows/apps/windows.storage.aspx) [!INCLUDE[wrt](../../../includes/wrt-md.md)], например [StorageFile](http://msdn.microsoft.com/library/windows/apps/windows.storage.storagefile.aspx) и [StorageFolder](http://msdn.microsoft.com/library/windows/apps/windows.storage.storagefolder.aspx).  
  
-   Изолированное хранилище недоступно; вместо этого используйте [данные приложения](/previous-versions/windows/apps/hh464917(v=win.10)).  
  
-   Используйте асинхронные методы, такие как <xref:System.IO.Stream.ReadAsync%2A> и <xref:System.IO.Stream.WriteAsync%2A>, чтобы предотвратить блокировку потока пользовательского интерфейса.  
  
-   Типы сжатия на основе пути <xref:System.IO.Compression.ZipFile> и <xref:System.IO.Compression.ZipFileExtensions> недоступны. Вместо этого используйте типы в пространстве имен [Windows.Storage.Compression](http://msdn.microsoft.com/library/windows/apps/windows.storage.compression.aspx).  
  
 При необходимости можно осуществлять преобразование между потоками .NET Framework и потоками среды выполнения Windows. Дополнительные сведениях см. в статьях [Практическое руководство. Преобразование между потоками .NET Framework и потоками среды выполнения Windows](../../../docs/standard/io/how-to-convert-between-dotnet-streams-and-winrt-streams.md) и [System.IO.WindowsRuntimeStreamExtensions](https://msdn.microsoft.com/library/system.io.windowsruntimestreamextensions.aspx). <!--zz TODO: <xref:System.IO.WindowsRuntimeStreamExtensions>--> 
  
 Дополнительные сведения об операциях ввода-вывода в приложении [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] см. в статье [Краткое руководство: чтение и запись файла](/previous-versions/windows/apps/hh758325(v=win.10)).  
  
## <a name="io-and-security"></a>Ввод-вывод и безопасность  
 При использовании классов в пространстве имен <xref:System.IO?displayProperty=nameWithType> необходимо выполнить требования безопасности операционной системы, такие как списки управления доступом для контроля доступа к файлам и каталогам. Это требование дополняет остальные требования <xref:System.Security.Permissions.FileIOPermission>. Списками управления доступом можно управлять программно. Дополнительные сведения см. в разделе [Практическое руководство. Добавление или удаление записей списка управления доступом](../../../docs/standard/io/how-to-add-or-remove-access-control-list-entries.md).  
  
 По умолчанию политика безопасности не позволяет обращаться к файлам на компьютере пользователя через Интернет или из приложений интрасети. Поэтому при составлении кода не используйте классы ввода-вывода, которым нужен путь к физическому файлу, загружаемому через Интернет или интрасеть. Вместо этого используйте [изолированное хранилище](../../../docs/standard/io/isolated-storage.md) для обычных приложений .NET Framework или [данные приложения](/previous-versions/windows/apps/hh464917(v=win.10)) для приложений [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)].  
  
 Проверка безопасности выполняется только при создании потока. Поэтому не рекомендуется открывать поток, а затем передавать его коду с меньшим уровнем доверия или доменам приложений.  
  
## <a name="related-topics"></a>См. также  
  
-   [Распространенные задачи ввода-вывода](../../../docs/standard/io/common-i-o-tasks.md)  
  
 Содержит список задач ввода-вывода, связанных с файлами, каталогами и потоками, а также ссылки на соответствующее содержимое и примеры для каждой задачи.  
  
-   [Асинхронный файловый ввод-вывод](../../../docs/standard/io/asynchronous-file-i-o.md)  
  
 Описывает преимущества и основные операции асинхронного ввода и вывода.  
  
-   [Изолированное хранилище](../../../docs/standard/io/isolated-storage.md)  
  
 Описывает механизм хранения данных, обеспечивающий автономность и безопасность путем определения стандартизованных способов сопоставления кода с защищенными данными.  
  
-   [Каналы](../../../docs/standard/io/pipe-operations.md)  
  
 Описывает операции с анонимными и именованными каналами в .NET Framework.  
  
-   [Сопоставленные в памяти файлы](../../../docs/standard/io/memory-mapped-files.md)  
  
 Описание отображаемых в память файлов, позволяющих разместить содержимое файлов с диска в виртуальной памяти. С их помощью можно вносить изменения в очень большие файлы и создавать совместно используемую память для межпроцессного взаимодействия.
