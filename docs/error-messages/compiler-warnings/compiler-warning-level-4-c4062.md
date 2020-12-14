---
description: '詳細情報: コンパイラの警告 (レベル 4) C4062'
title: コンパイラの警告 (レベル 4) C4062
ms.date: 04/05/2019
f1_keywords:
- C4062
helpviewer_keywords:
- C4062
ms.assetid: 36d1c6ae-c917-4b08-bf30-2eb49ee94169
ms.openlocfilehash: 3aee4286fb8d06d98617ea6fa71929768cbd23c0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97262049"
---
# <a name="compiler-warning-level-4-c4062"></a>コンパイラの警告 (レベル 4) C4062

> 列挙型 '*enumeration*' の switch の列挙子 '*identifier*' は処理されていません

列挙子 *識別子* には、ステートメント内に関連付けられたハンドラーがなく、 `case` **`switch`** それをキャッチできるラベルがありません **`default`** 。 見つからないケースは、監視であり、コードでエラーが発生する可能性があります。 ステートメントで使用されていない列挙子に関する関連する警告につい **`switch`** **`default`** ては、「 [C4061](compiler-warning-level-4-c4061.md)」を参照してください。

既定では、この警告はオフに設定されています。 既定でオフになっている警告を有効にする方法の詳細については、「 [既定でオフになっているコンパイラ警告](../../preprocessor/compiler-warnings-that-are-off-by-default.md)」を参照してください。

## <a name="example"></a>例

次の例では、C4062 を生成し、その修正方法を示しています。

```cpp
// C4062.cpp
// compile with: /EHsc /W4
#pragma warning(default : 4062)
enum E { a, b, c };
void func ( E e ) {
   switch(e) {
      case a:
      case b:
   // case c:  // to fix, uncomment this line
      break;   // no default label
   }   // C4062, enumerator 'c' not handled
}

int main() {
}
```

## <a name="see-also"></a>関連項目

[コンパイラの警告 (レベル 4) C4061](compiler-warning-level-4-c4061.md)
