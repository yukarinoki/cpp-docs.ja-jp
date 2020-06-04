---
title: コンパイラの警告 (レベル 1) C4537
ms.date: 08/27/2018
f1_keywords:
- C4537
helpviewer_keywords:
- C4537
ms.assetid: 9454493c-d419-475e-8f35-9c00233c9329
ms.openlocfilehash: 81058f153228d3d8fbf4097c140962d0cb9677e5
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80186362"
---
# <a name="compiler-warning-level-1-c4537"></a>コンパイラの警告 (レベル 1) C4537

> '*object*': UDT 以外の型に適用された '*operator*'

## <a name="remarks"></a>解説

オブジェクト (ユーザー定義型) が必要な場所に参照が渡されました。 参照はオブジェクトではありませんが、インラインアセンブラーコードでは区別できません。 コンパイラは、*オブジェクト*がインスタンスの場合と同様にコードを生成します。

## <a name="example"></a>例

次の例では、C4537 を生成し、その修正方法を示しています。

```cpp
// C4537.cpp
// compile with: /W1 /c
// processor: x86
struct S {
    int member;
};

void f1(S &s) {
    __asm mov eax, s.member;   // C4537
    // try the following code instead
    // or, make the declaration "void f1(S s)"
    /*
    mov eax, s
    mov eax, [eax]s.member
    */
}
```
