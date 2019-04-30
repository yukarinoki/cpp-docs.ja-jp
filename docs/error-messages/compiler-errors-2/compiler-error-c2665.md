---
title: コンパイラ エラー C2665
ms.date: 11/04/2016
f1_keywords:
- C2665
helpviewer_keywords:
- C2665
ms.assetid: a7f99b61-2eae-4f2b-ba75-ea68fd1e8312
ms.openlocfilehash: 63817c4181edb942f43f41c24fb10278d14f397e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62386890"
---
# <a name="compiler-error-c2665"></a>コンパイラ エラー C2665

'function': パラメーターの数値 2 を型 'type' から変換 number1 オーバー ロードはないことができます

オーバー ロードされた関数のパラメーターは、必要な型に変換できません。  考えられる解決策:

- 変換演算子を指定します。

- 明示的な変換を使用します。

## <a name="example"></a>例

次の例では、C2665 が生成されます。

```
// C2665.cpp
void func(short, char*){}
void func(char*, char*){}

int main() {
   func(0, 1);   // C2665
   func((short)0, (char*)1);   // OK
}
```