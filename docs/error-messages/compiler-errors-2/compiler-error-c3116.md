---
description: 詳細については、「コンパイラエラー C3116」を参照してください。
title: コンパイラ エラー C3116
ms.date: 11/04/2016
f1_keywords:
- C3116
helpviewer_keywords:
- C3116
ms.assetid: 597463e1-a5cc-4ed3-a917-eae9a61d3312
ms.openlocfilehash: ea11d851c4348725c48e408ffdd0ed6de4393e6e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97115938"
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
