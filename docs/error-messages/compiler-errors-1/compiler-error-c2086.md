---
description: 詳細については、「コンパイラエラー C2086」を参照してください。
title: コンパイラエラー C2086
ms.date: 11/04/2016
f1_keywords:
- C2086
helpviewer_keywords:
- C2086
ms.assetid: 4329bf72-90c8-444c-8524-4ef75e6b2139
ms.openlocfilehash: b98b4ed3896b11d8df434935c1b539f76640f24c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97252078"
---
# <a name="compiler-error-c2086"></a>コンパイラエラー C2086

' identifier ': 再定義

識別子が2回以上定義されているか、それ以降の宣言が前の宣言と異なっています。

C2086 は、参照されている C# アセンブリのインクリメンタルビルドの結果である場合もあります。 このエラーを解決するには、C# アセンブリをリビルドします。

次の例では、C2086 が生成されます。

```cpp
// C2086.cpp
main() {
  int a;
  int a;   // C2086 not an error in ANSI C
}
```
