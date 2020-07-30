---
title: コンパイラ エラー C3116
ms.date: 11/04/2016
f1_keywords:
- C3116
helpviewer_keywords:
- C3116
ms.assetid: 597463e1-a5cc-4ed3-a917-eae9a61d3312
ms.openlocfilehash: b336588d732fca2fd45b753429a563360f575912
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87223448"
---
# <a name="compiler-error-c3116"></a>コンパイラ エラー C3116

' storage 指定子 ': インターフェイスメソッドのストレージクラスが無効です

**`typedef`** **`register`** **`static`** インターフェイスメソッドのストレージクラスとして、、またはを使用しています。 これらのストレージクラスは、インターフェイスメンバーでは許可されていません。

次の例では、C3116 が生成されます。

```cpp
// C3116.cpp
__interface ImyInterface
{
   static void myFunc();   // C3116
};
```
