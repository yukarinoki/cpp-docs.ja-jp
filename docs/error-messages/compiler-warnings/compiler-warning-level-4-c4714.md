---
title: コンパイラの警告 (レベル 4) C4714
ms.date: 11/04/2016
f1_keywords:
- C4714
helpviewer_keywords:
- C4714
ms.assetid: 22c7fd0c-899d-4e9b-95f3-725b2c49fb46
ms.openlocfilehash: ed94e5b716a697ec96d7fecac75433823c9a67e9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50553856"
---
# <a name="compiler-warning-level-4-c4714"></a>コンパイラの警告 (レベル 4) C4714

関数 'function' がマークされている _ _forceinline として記述しないインライン

指定された関数がインライン展開の選択されたが、コンパイラが実行されなかった、インライン化します。

`__forceinline`よりも、コンパイラにより強力な通知`__inline`、インライン化も、コンパイラの裁量により、実行しないヒューリスティックを使用して決定から利点がありますが、インライン展開この関数。

場合によっては、コンパイラはインラインではなく、特定の関数の機械的な理由からします。 たとえば、コンパイラは、インラインではなくを行います。

- SEH と C++ EH の両方を混在させることになる場合の関数。

- コピーを使用して一部の関数は、-GX EHs//eha がオンの場合は、値渡しのオブジェクトを構築します。

- -GX EHs//eha がオンの場合、値によってアンワインド可能オブジェクトを返す関数。

- Og、Ox、O1/O2 なしでコンパイルするときに、インライン アセンブリでの関数。

- 可変個引数リスト機能します。

- 関数を**お試しください**(C++ 例外処理) のステートメント。

次の例では、C4714 が生成されます。

```
// C4714.cpp
// compile with: /Ob1 /GX /W4
__forceinline void func1()
{
   try
   {
   }
   catch (...)
   {
   }
}

void func2()
{
   func1();   // C4714
}

int main()
{
}
```