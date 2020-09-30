---
title: コンパイラ エラー C2504
ms.date: 11/04/2016
f1_keywords:
- C2504
helpviewer_keywords:
- C2504
ms.assetid: c9e002a6-a4ee-4ba7-970e-edf4adb83692
ms.openlocfilehash: 0860f4b860b370f96c2c29046b090d5b205c63ba
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/29/2020
ms.locfileid: "91509391"
---
# <a name="compiler-error-c2504"></a>コンパイラ エラー C2504

' class ': 基底クラスが定義されていません。

基底クラスが宣言されていますが、定義されていません。  考えられる原因:

1. インクルードファイルがありません。

1. 外部基底クラスが [extern](../../cpp/extern-cpp.md)で宣言されていません。

次の例では、C2504 が生成されます。

```cpp
// C2504.cpp
// compile with: /c
class A;
class B : public A {};   // C2504
```

わかりました

```
class C{};
class D : public C {};
```
