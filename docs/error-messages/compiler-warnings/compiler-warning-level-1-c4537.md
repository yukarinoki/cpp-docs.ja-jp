---
title: コンパイラの警告 (レベル 1) C4537 |Microsoft Docs
ms.custom: ''
ms.date: 08/27/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4537
dev_langs:
- C++
helpviewer_keywords:
- C4537
ms.assetid: 9454493c-d419-475e-8f35-9c00233c9329
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 052d11d5bdf269d950abe1ef761adc055cbc6ce3
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43213364"
---
# <a name="compiler-warning-level-1-c4537"></a>コンパイラの警告 (レベル 1) C4537

> '*オブジェクト*':'*演算子*' UDT 以外の型に適用

## <a name="remarks"></a>Remarks

オブジェクト (ユーザー定義型) が必要な場所の参照が渡されました。 参照がオブジェクトではありませんが、インライン アセンブラー コードでは区別できません。 コンパイラがいなくてもコードを生成*オブジェクト*インスタンスします。

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