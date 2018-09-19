---
title: コンパイラの警告 (レベル 4) C4434 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4434
dev_langs:
- C++
helpviewer_keywords:
- C4434
ms.assetid: 24b8785e-353a-4c37-8bed-ed61001a871d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ec0d9e4cfbed2d2871e35631df918f17a342f653
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46025764"
---
# <a name="compiler-warning-level-4-c4434"></a>コンパイラの警告 (レベル 4) C4434

クラス コンストラクターはプライベート アクセシビリティを含んでいなければなりません。プライベート アクセスに変更します

C4434 は、コンパイラが静的コンストラクターのアクセシビリティを変更したことを示します。 静的コンストラクターは共通言語ランタイムからのみ呼び出されるものであるため、専用のアクセシビリティが必要です。 詳細については、次を参照してください。[静的コンス トラクター](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Static_constructors)します。

## <a name="example"></a>例

次の例では、C4434 が生成されます。

```
// C4434.cpp
// compile with: /W4 /c /clr
public ref struct R {
   static R(){}   // C4434
};
```