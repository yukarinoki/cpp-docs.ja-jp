---
description: 詳細については、「コンパイラエラー C2180」を参照してください。
title: コンパイラ エラー C2180
ms.date: 11/04/2016
f1_keywords:
- C2180
helpviewer_keywords:
- C2180
ms.assetid: ea71b39e-b977-48a7-b7bd-af68ef5e263b
ms.openlocfilehash: 46ab20e3abfc35355543f90389677737e231257f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97335183"
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
