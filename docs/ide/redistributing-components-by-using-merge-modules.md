---
title: マージ モジュールを使用したコンポーネントの再配布 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- merge modules, using
- redistributing applications, using merge modules
ms.assetid: 93b84211-bf9b-4a78-9f22-474ac2ef7840
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d816d932ce518e006e5537075fe4ac7782362ad4
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43206985"
---
# <a name="redistributing-components-by-using-merge-modules"></a>マージ モジュールを使用したコンポーネントの再配布
Visual Studio には、アプリケーションと共に再頒布することがライセンスされている Visual C++ コンポーネントごとに[マージ モジュール](/windows/desktop/Msi/about-merge-modules)が用意されています。 マージ モジュールが Windows インストーラーのセットアップ ファイルにコンパイルされるときに、特定のプラットフォームのコンピューターへの特定の DLL の配置が有効になります。 セットアップ ファイルでは、そのマージ モジュールがアプリケーションの必須コンポーネントであることを指定します。 Visual Studio をインストールすると、マージ モジュールは \Program Files\Common Files\Merge Modules\\ にインストールされます  (再頒布できるのは非デバッグ バージョンの Visual C++ DLL だけです)。詳細については、「[Visual C++ ファイルの再配布](../ide/redistributing-visual-cpp-files.md)」を参照してください。このサイトには、再頒布用にライセンスされたマージ モジュールの一覧へのリンクもあります。  
  
 マージ モジュールを使用すると、再頒布可能な Visual C++ DLL を %SYSTEMROOT%\system32\ フォルダーにインストールできます  (Visual Studio 自体がこの方法を使用します)。ただし、このフォルダーへのインストールは、インストールしているユーザーに管理者権限がないと失敗します。  
  
 アプリケーションにサービスを提供する必要がある場合、また、複数のバージョンの DLL に依存している場合は、マージ モジュールを使用することはお勧めしません。 1 つの DLL にさまざまなバージョンの DLL がある場合、その複数バージョンの DLL に対する複数のマージ モジュールを 1 つのインストーラーに含めることはできません。また、マージ モジュールによって、アプリケーションとは別に DLL にサービスを提供することが難しくなります。 代わりに、Visual C++ 再頒布可能パッケージをインストールすることをお勧めします。  
  
## <a name="see-also"></a>参照  
 [Visual C++ ファイルの再配布](../ide/redistributing-visual-cpp-files.md)