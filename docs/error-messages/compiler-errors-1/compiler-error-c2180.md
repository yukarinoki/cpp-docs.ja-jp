---
title: コンパイラ エラー C2180
ms.date: 11/04/2016
f1_keywords:
- C2180
helpviewer_keywords:
- C2180
ms.assetid: ea71b39e-b977-48a7-b7bd-af68ef5e263b
ms.openlocfilehash: 16fcf15eb29743f74bbf2edcb1016f2e15228e5a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62385915"
---
# <a name="compiler-error-c2180"></a>コンパイラ エラー C2180

制御式には、型 'type' が指定されています。

`if`、`while`、`for`、`do` のいずれかのステートメントの制御式は、`void` にキャストした式です。 この問題を解決するには、制御式を、`bool` を生成する制御式または `bool` に変換できる型に変更します。

次の例では C2180 が生成されます。

```
// C2180.c

int main() {
   while ((void)1)   // C2180
      return 1;
   while (1)         // OK
      return 0;
}
```