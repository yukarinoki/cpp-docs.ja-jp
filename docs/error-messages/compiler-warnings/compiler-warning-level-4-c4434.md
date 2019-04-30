---
title: コンパイラの警告 (レベル 4) C4434
ms.date: 11/04/2016
f1_keywords:
- C4434
helpviewer_keywords:
- C4434
ms.assetid: 24b8785e-353a-4c37-8bed-ed61001a871d
ms.openlocfilehash: 6a7d760a7d192c7e0a7bd5e16f77efe1a4099c31
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62391492"
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