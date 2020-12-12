---
description: 詳細については、「アプリケーションドメインと Visual C++」を参照してください。
title: アプリケーション ドメインと Visual C++
ms.date: 11/04/2016
helpviewer_keywords:
- interop [C++], application domains
- application domains [C++], C++
- /clr compiler option [C++], application domains
- interoperability [C++], application domains
- mixed assemblies [C++], application domains
ms.assetid: 75a08efc-9b02-40ba-99b7-dcbd71010bbf
ms.openlocfilehash: 55f02aec7b3b2d23f10ae9142dba7c61ff60683f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97282823"
---
# <a name="application-domains-and-visual-c"></a>アプリケーション ドメインと Visual C++

仮想関数がある場合 `__clrcall` 、vtable はアプリケーションドメイン (appdomain) ごとになります。 1つの appdomain にオブジェクトを作成する場合は、その appdomain 内からのみ仮想関数を呼び出すことができます。 混合モード (**/clr**) では、型に仮想関数がない場合は、プロセスごとの vtable があり `__clrcall` ます。 **/Clr: pure** および **/clr: safe** コンパイラオプションは visual studio 2015 で非推奨とされており、visual studio 2017 ではサポートされていません。

詳細については、次を参照してください。

- [伴う](../cpp/appdomain.md)

- [__clrcall](../cpp/clrcall.md)

- [process](../cpp/process.md)

## <a name="see-also"></a>関連項目

- [混合 (ネイティブおよびマネージ) アセンブリ](../dotnet/mixed-native-and-managed-assemblies.md)
