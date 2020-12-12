---
description: 詳細については、「マージモジュールを使用したコンポーネントの再配布」をご覧ください。
title: マージ モジュールを使用したコンポーネントの再配布
ms.date: 11/04/2016
helpviewer_keywords:
- merge modules, using
- redistributing applications, using merge modules
ms.assetid: 93b84211-bf9b-4a78-9f22-474ac2ef7840
ms.openlocfilehash: ecfc2904be7451c96226e91ed8e7f98d565d35ac
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97179903"
---
# <a name="redistributing-components-by-using-merge-modules"></a>マージ モジュールを使用したコンポーネントの再配布

Visual Studio には、アプリケーションと共に再頒布することがライセンスされている Visual C++ コンポーネントごとに[マージ モジュール](/windows/win32/Msi/about-merge-modules)が用意されています。 マージ モジュールが Windows インストーラーのセットアップ ファイルにコンパイルされるときに、特定のプラットフォームのコンピューターへの特定の DLL の配置が有効になります。 セットアップ ファイルでは、そのマージ モジュールがアプリケーションの必須コンポーネントであることを指定します。 Visual Studio をインストールすると、マージ モジュールは \Program Files\Common Files\Merge Modules\\ にインストールされます  (Visual C++ Dll の非デバッグバージョンのみを再配布できます)。再配布がライセンスされているマージモジュールの一覧の詳細およびリンクについては、「 [Visual C++ ファイル](redistributing-visual-cpp-files.md)の再配布」を参照してください。

マージ モジュールを使用すると、再頒布可能な Visual C++ DLL を %SYSTEMROOT%\system32\ フォルダーにインストールできます  (Visual Studio 自体は、この手法を使用します)。ただし、インストールするユーザーが管理者権限を持っていない限り、このフォルダーへのインストールは失敗します。

アプリケーションにサービスを提供する必要がある場合、また、複数のバージョンの DLL に依存している場合は、マージ モジュールを使用することはお勧めしません。 1 つの DLL にさまざまなバージョンの DLL がある場合、その複数バージョンの DLL に対する複数のマージ モジュールを 1 つのインストーラーに含めることはできません。また、マージ モジュールによって、アプリケーションとは別に DLL にサービスを提供することが難しくなります。 代わりに、Visual C++ 再頒布可能パッケージをインストールすることをお勧めします。

## <a name="see-also"></a>関連項目

[Visual C++ ファイルの再配布](redistributing-visual-cpp-files.md)
