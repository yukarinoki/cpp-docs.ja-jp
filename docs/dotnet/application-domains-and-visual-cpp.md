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
ms.openlocfilehash: 16c02bb58681ecb241d3552f57e0b05f2d6711b4
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80208804"
---
# <a name="application-domains-and-visual-c"></a>アプリケーション ドメインと Visual C++

`__clrcall` の仮想関数がある場合、vtable はアプリケーションドメイン (appdomain) ごとになります。 1つの appdomain にオブジェクトを作成する場合は、その appdomain 内からのみ仮想関数を呼び出すことができます。 混合モード ( **/clr**) では、型に `__clrcall` 仮想関数がない場合は、プロセスごとの vtable があります。 **/Clr: pure**および **/clr: safe**コンパイラオプションは visual studio 2015 で非推奨とされており、visual studio 2017 ではサポートされていません。

詳細については、次を参照してください。

- [appdomain](../cpp/appdomain.md)

- [__clrcall](../cpp/clrcall.md)

- [process](../cpp/process.md)

## <a name="see-also"></a>参照

- [混在 (ネイティブおよびマネージド) アセンブリ](../dotnet/mixed-native-and-managed-assemblies.md)
