---
title: コンパイラ エラー C2180 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2180
dev_langs:
- C++
helpviewer_keywords:
- C2180
ms.assetid: ea71b39e-b977-48a7-b7bd-af68ef5e263b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9c74912b92162cbfcada3630ed6a6845b67045d0
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46084147"
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