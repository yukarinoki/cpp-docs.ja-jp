---
title: コンパイラ エラー C2180
ms.date: 11/04/2016
f1_keywords:
- C2180
helpviewer_keywords:
- C2180
ms.assetid: ea71b39e-b977-48a7-b7bd-af68ef5e263b
ms.openlocfilehash: 3794a1ce0fcbe60c06cb3efca45a3081e85c17ce
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87210021"
---
# <a name="compiler-error-c2180"></a>コンパイラ エラー C2180

制御式には、型 'type' が指定されています。

**`if`**、、 **`while`** **`for`** 、またはステートメントの制御式 **`do`** は、にキャストされた式です **`void`** 。 この問題を解決するには、制御式を、 **`bool`** に変換できる型または型を生成する式に変更し **`bool`** ます。

次の例では C2180 が生成されます。

```c
// C2180.c

int main() {
   while ((void)1)   // C2180
      return 1;
   while (1)         // OK
      return 0;
}
```
