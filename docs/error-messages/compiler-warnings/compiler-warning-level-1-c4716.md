---
title: コンパイラの警告 (レベル 1) C4716
ms.date: 11/04/2016
f1_keywords:
- C4716
helpviewer_keywords:
- C4716
ms.assetid: d95ecfe5-870f-461f-a746-7913af98414b
ms.openlocfilehash: 91e836c9bb606d7759206788d1e3abd63b293fa8
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80175312"
---
# <a name="compiler-warning-level-1-c4716"></a>コンパイラの警告 (レベル 1) C4716

'function': 値を返さなければいけません

指定された関数は値を返しませんでした。

戻り値の型が void の関数だけが戻り値を伴う戻り値を指定することはできません。

この関数が呼び出されると、未定義の値が返されます。

この警告は、自動的にエラーになります。 この動作を変更する場合は、 [#pragma 警告](../../preprocessor/warning.md)を使用します。

次の例では、C4716 が生成されます。

```cpp
// C4716.cpp
// compile with: /c /W1
// C4716 expected
#pragma warning(default:4716)
int test() {
   // uncomment the following line to resolve
   // return 0;
}
```
