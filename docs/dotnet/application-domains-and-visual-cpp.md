---
title: アプリケーション ドメインと Visual C++
ms.date: 11/04/2016
helpviewer_keywords:
- interop [C++], application domains
- application domains [C++], C++
- /clr compiler option [C++], application domains
- interoperability [C++], application domains
- mixed assemblies [C++], application domains
ms.assetid: 75a08efc-9b02-40ba-99b7-dcbd71010bbf
ms.openlocfilehash: 2296654e6935bc40f301226b184cf34f77cb126d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50539270"
---
# <a name="application-domains-and-visual-c"></a>アプリケーション ドメインと Visual C

ある場合、`__clrcall`仮想関数は、vtable がアプリケーション ドメイン (appdomain) ごとになります。 1 つの appdomain でオブジェクトを作成する場合は、その appdomain 内で仮想関数からのみ呼び出すことができます。 混在モードで (**/clr**) の種類がにない場合、プロセスごとの vtable が`__clrcall`仮想関数。 **/Clr: 純粋な**と **/clr:safe**コンパイラ オプションは Visual Studio 2015 で非推奨とされ、Visual Studio 2017 でサポートされていません。

詳細については次を参照してください:

- [appdomain](../cpp/appdomain.md)

- [__clrcall](../cpp/clrcall.md)

- [process](../cpp/process.md)

## <a name="see-also"></a>関連項目

- [混在 (ネイティブおよびマネージド) アセンブリ](../dotnet/mixed-native-and-managed-assemblies.md)