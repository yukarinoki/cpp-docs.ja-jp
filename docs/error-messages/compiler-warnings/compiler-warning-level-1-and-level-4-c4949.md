---
description: '詳細情報: コンパイラの警告 (レベル1およびレベル 4) C4949'
title: コンパイラの警告 (レベル 1 およびレベル 4) C4949
ms.date: 11/04/2016
f1_keywords:
- C4949
helpviewer_keywords:
- C4949
ms.assetid: 34f45a05-c115-49cb-9f67-0bd4f0735d9b
ms.openlocfilehash: 2330843c34207edbe99607208baff634836044cc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97336017"
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

**/Clr** を指定せずに **#pragma アンマネージ** を使用すると、C4949 はレベル4の警告になります。

次の例では、C4949 が生成されます。

```cpp
// C4949b.cpp
// compile with: /LD /W4
#pragma unmanaged   // C4949
```
