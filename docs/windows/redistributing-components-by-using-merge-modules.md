---
title: マージ モジュールを使用したコンポーネントの再配布
ms.date: 11/04/2016
helpviewer_keywords:
- merge modules, using
- redistributing applications, using merge modules
ms.assetid: 93b84211-bf9b-4a78-9f22-474ac2ef7840
ms.openlocfilehash: 7a110826e21f33986d68dcd46417ec5cbd5171bc
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/01/2019
ms.locfileid: "58786532"
---
# <a name="redistributing-components-by-using-merge-modules"></a>マージ モジュールを使用したコンポーネントの再配布

Visual Studio には、アプリケーションと共に再頒布することがライセンスされている Visual C++ コンポーネントごとに[マージ モジュール](/windows/desktop/Msi/about-merge-modules)が用意されています。 マージ モジュールが Windows インストーラーのセットアップ ファイルにコンパイルされるときに、特定のプラットフォームのコンピューターへの特定の DLL の配置が有効になります。 セットアップ ファイルでは、そのマージ モジュールがアプリケーションの必須コンポーネントであることを指定します。 Visual Studio をインストールすると、マージ モジュールは \Program Files\Common Files\Merge Modules\\ にインストールされます  (再頒布できるのは非デバッグ バージョンの Visual C++ DLL だけです)。詳細については、「[Visual C++ ファイルの再配布](redistributing-visual-cpp-files.md)」を参照してください。このサイトには、再頒布用にライセンスされたマージ モジュールの一覧へのリンクもあります。

マージ モジュールを使用すると、再頒布可能な Visual C++ DLL を %SYSTEMROOT%\system32\ フォルダーにインストールできます  (Visual Studio 自体がこの方法を使用します)。ただし、このフォルダーへのインストールは、インストールしているユーザーに管理者権限がないと失敗します。

アプリケーションにサービスを提供する必要がある場合、また、複数のバージョンの DLL に依存している場合は、マージ モジュールを使用することはお勧めしません。 1 つの DLL にさまざまなバージョンの DLL がある場合、その複数バージョンの DLL に対する複数のマージ モジュールを 1 つのインストーラーに含めることはできません。また、マージ モジュールによって、アプリケーションとは別に DLL にサービスを提供することが難しくなります。 代わりに、Visual C++ 再頒布可能パッケージをインストールすることをお勧めします。

## <a name="see-also"></a>関連項目

[Visual C++ ファイルの再配布](redistributing-visual-cpp-files.md)
