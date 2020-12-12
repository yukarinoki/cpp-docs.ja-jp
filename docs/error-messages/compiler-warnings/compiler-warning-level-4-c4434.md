---
description: '詳細情報: コンパイラの警告 (レベル 4) C4434'
title: コンパイラの警告 (レベル 4) C4434
ms.date: 11/04/2016
f1_keywords:
- C4434
helpviewer_keywords:
- C4434
ms.assetid: 24b8785e-353a-4c37-8bed-ed61001a871d
ms.openlocfilehash: 24e8066ec415293eddf6de1d5a2dd2644623f2ac
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97251467"
---
# <a name="compiler-warning-level-4-c4434"></a>コンパイラの警告 (レベル 4) C4434

クラス コンストラクターはプライベート アクセシビリティを含んでいなければなりません。プライベート アクセスに変更します

C4434 は、コンパイラが静的コンストラクターのアクセシビリティを変更したことを示します。 静的コンストラクターは共通言語ランタイムからのみ呼び出されるものであるため、専用のアクセシビリティが必要です。 詳細については、「 [静的コンストラクター](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Static_constructors)」を参照してください。

## <a name="example"></a>例

次の例では、C4434 が生成されます。

```cpp
// C4434.cpp
// compile with: /W4 /c /clr
public ref struct R {
   static R(){}   // C4434
};
```
