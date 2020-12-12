---
description: '詳細情報: コンパイラの警告 (レベル 1) C4036'
title: コンパイラの警告 (レベル 1) C4036
ms.date: 11/04/2016
f1_keywords:
- C4036
helpviewer_keywords:
- C4036
ms.assetid: f0b15359-4d62-48ec-8cb1-a7b36587a47f
ms.openlocfilehash: 6547cd068b39ff3db54829dfc20fb47a52113e2a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97318924"
---
# <a name="compiler-warning-level-1-c4036"></a>コンパイラの警告 (レベル 1) C4036

実パラメーターとして渡される 'type' に型指定がありません

実パラメーターとして使用される構造体、共用体、列挙型、またはクラスの型名が指定されていません。 コンパイラは、 [/Zg](../../build/reference/zg-generate-function-prototypes.md) を使用して関数プロトタイプを生成するとこの警告を発行し、生成されたプロトタイプの仮パラメーターをコメントアウトします。

この警告を解決するには、型名を指定します。

## <a name="example"></a>例

次の例では C4036 が生成されます。

```c
// C4036.c
// compile with: /Zg /W1
// D9035 expected
typedef struct { int i; } T;
void f(T* t) {}   // C4036

// OK
typedef struct MyStruct { int i; } T2;
void f2(T2 * t) {}
```
