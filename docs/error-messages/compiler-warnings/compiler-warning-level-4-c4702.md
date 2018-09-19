---
title: コンパイラの警告 (レベル 4) C4702 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4702
dev_langs:
- C++
helpviewer_keywords:
- C4702
ms.assetid: d8198c1e-8762-42a6-9e6b-cb568b7a1686
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1d15072099c6329eced8ab9dd9c78f8f48c31fe7
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46057139"
---
# <a name="compiler-warning-level-4-c4702"></a>コンパイラの警告 (レベル 4) C4702

到達できないコード

この警告は、Visual Studio .NET 2003 で行ったコンパイラ準拠作業の結果: 制御が渡らないコードです。 C4702 が生成されます (バック エンド) のコンパイラでは、到達できないコードを検出すると、レベル 4 の警告。

コードでは、Visual Studio .NET 2003 と Visual Studio .NET のバージョンの Visual C では有効で、到達できないコードを削除するか、すべてのソース コードが実行の一部のフローによってアクセスできることを保証します。

## <a name="example"></a>例

次の例では、C4702 が生成されます。

```
// C4702.cpp
// compile with: /W4
#include <stdio.h>

int main() {
   return 1;
   printf_s("I won't print.\n");   // C4702 unreachable
}
```

## <a name="example"></a>例

コンパイルするときに **/GX**、 **/EHc**、 **/EHsc**、または **/EHac**になり、extern C 関数を使用して、コードは到達できないため、extern Cしたがって、catch ブロックで到達可能なはないの関数はスローしないと見なされます。  この警告が無効であるため、関数はスローできる場合、使用してコンパイル **/EHa**または **/EHs**によってスローされる例外。

詳細については、次を参照してください。 [/EH (例外処理モデル)](../../build/reference/eh-exception-handling-model.md)詳細についてはします。

次の例では、C4702 が生成されます。

```
// C4702b.cpp
// compile with: /W4 /EHsc
#include <iostream>

using namespace std;
extern "C" __declspec(dllexport) void Function2(){}

int main() {
   try {
      Function2();
   }
   catch (...) {
      cout << "Exp: Function2!" << endl;   // C4702
   }
}
```