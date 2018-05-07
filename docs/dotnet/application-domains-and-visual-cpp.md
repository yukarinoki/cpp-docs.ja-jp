---
title: アプリケーション ドメインと Visual C |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- interop [C++], application domains
- application domains [C++], C++
- /clr compiler option [C++], application domains
- interoperability [C++], application domains
- mixed assemblies [C++], application domains
ms.assetid: 75a08efc-9b02-40ba-99b7-dcbd71010bbf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 8ddb60b3fad6c230677e2098dd89a723198bea8b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="application-domains-and-visual-c"></a>アプリケーション ドメインと Visual C++
ある場合、`__clrcall`仮想関数は、vtable なりますあたりのアプリケーション ドメイン (appdomain)。 1 つの appdomain でオブジェクトを作成する場合は、appdomain 内から仮想関数のみ呼び出すことができます。 混在モードで (**/clr**)、型を持たない場合プロセス vtable あたりが`__clrcall`仮想関数。 コンパイラ オプションの **/clr:pure** と **/clr:safe** は Visual Studio 2015 で非推奨とされています。  
  
 詳細については、次のトピックを参照してください。  
  
-   [appdomain](../cpp/appdomain.md)  
  
-   [__clrcall](../cpp/clrcall.md)  
  
-   [process](../cpp/process.md)  
  
## <a name="see-also"></a>関連項目  
 [混在 (ネイティブおよびマネージ) アセンブリ](../dotnet/mixed-native-and-managed-assemblies.md)