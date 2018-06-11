---
title: プロセス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- process_cpp
dev_langs:
- C++
helpviewer_keywords:
- __declspec keyword [C++], process
- process __declspec keyword
ms.assetid: 60eecc2f-4eef-4567-b9db-aaed34733023
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b36ec42447aa076d0623707951f82b7b9c95d563
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2018
ms.locfileid: "34704907"
---
# <a name="process"></a>process

マネージ アプリケーション プロセスが、プロセス内のすべてのアプリケーション ドメイン間で共有される特定のグローバル変数、静的メンバー変数、または静的ローカル変数のコピーを 1 つ持つことを指定します。 これが、主に使用するためでコンパイルするときに **/clr: 純粋な**、これは Visual Studio 2017 で廃止され、Visual Studio 2017 でサポートされていません。 コンパイルするときに **/clr**、グローバルと静的変数は、プロセスごとの既定では、使用する必要はありません`__declspec(process)`です。

`__declspec(process)` でマークできるのは、グローバル変数、静的メンバー変数、またはネイティブ型の静的ローカル変数だけです。

`process` コンパイルするときに、有効なのみ[/clr](../build/reference/clr-common-language-runtime-compilation.md)です。

使用する場合は、グローバル変数の独自のコピーが存在する場合は、各アプリケーション ドメイン、 [appdomain](../cpp/appdomain.md)です。

参照してください[アプリケーション ドメインと Visual C](../dotnet/application-domains-and-visual-cpp.md)詳細についてはします。

## <a name="see-also"></a>関連項目

- [__declspec](../cpp/declspec.md)
- [キーワード](../cpp/keywords-cpp.md)
