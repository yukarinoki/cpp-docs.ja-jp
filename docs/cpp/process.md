---
title: プロセス |Microsoft Docs
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
ms.openlocfilehash: 65ae8eef828a8abd4bf726c99850089c0f30b71b
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46032569"
---
# <a name="process"></a>process

マネージド アプリケーション プロセスが、プロセス内のすべてのアプリケーション ドメイン間で共有される特定のグローバル変数、静的メンバー変数、または静的ローカル変数のコピーを 1 つ持つことを指定します。 コンパイルするときに使用される、主にものがこの **/clr: 純粋な**は Visual Studio 2017 では非推奨し、Visual Studio 2017 でサポートされていません。 コンパイルするときに **/clr**、グローバルと静的変数は、既定では、プロセスごとおよび使用する必要はありません **__declspec(process)** します。

グローバル変数のみ、静的メンバー変数、またはネイティブ型の静的ローカル変数とマークできます **__declspec(process)** します。

**プロセス**はでコンパイルする場合にのみ有効です[/clr](../build/reference/clr-common-language-runtime-compilation.md)します。

グローバル変数の独自のコピーが存在する場合は、各アプリケーション ドメインにする場合は、使用[appdomain](../cpp/appdomain.md)します。

参照してください[アプリケーション ドメインと Visual C](../dotnet/application-domains-and-visual-cpp.md)詳細についてはします。

## <a name="see-also"></a>関連項目

[__declspec](../cpp/declspec.md)<br/>
[キーワード](../cpp/keywords-cpp.md)
