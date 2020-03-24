---
title: コンパイラの警告 (レベル 1 およびレベル 4) C4949
ms.date: 11/04/2016
f1_keywords:
- C4949
helpviewer_keywords:
- C4949
ms.assetid: 34f45a05-c115-49cb-9f67-0bd4f0735d9b
ms.openlocfilehash: 7ce8b3242def187e4b8b442f403f92f013a9ca6e
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80164782"
---
# <a name="compiler-warning-level-1-and-level-4-c4949"></a>コンパイラの警告 (レベル 1 およびレベル 4) C4949

プラグマ ' managed ' と ' unmanaged ' は、'/clr [: option] ' でコンパイルされた場合にのみ意味があります

ソースコードが[/clr](../../build/reference/clr-common-language-runtime-compilation.md)でコンパイルされていない場合、コンパイラは[マネージ](../../preprocessor/managed-unmanaged.md)プラグマおよびアンマネージプラグマを無視します。 これは、情報提供の警告です。

次の例では、C4949 が生成されます。

```cpp
// C4949.cpp
// compile with: /LD /W1
#pragma managed   // C4949
```

**/Clr**を指定せずに **#pragma アンマネージ**を使用すると、C4949 はレベル4の警告になります。

次の例では、C4949 が生成されます。

```cpp
// C4949b.cpp
// compile with: /LD /W4
#pragma unmanaged   // C4949
```
