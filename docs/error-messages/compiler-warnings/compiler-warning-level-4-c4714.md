---
title: コンパイラの警告 (レベル 4) C4714
ms.date: 11/04/2016
f1_keywords:
- C4714
helpviewer_keywords:
- C4714
ms.assetid: 22c7fd0c-899d-4e9b-95f3-725b2c49fb46
ms.openlocfilehash: 286a9e6e12643d3dadd070e7c4cf4b2dd350c02c
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87219860"
---
# <a name="compiler-warning-level-4-c4714"></a>コンパイラの警告 (レベル 4) C4714

> 関数 ' function ' はインライン __forceinline としてマークされていません

指定された関数はインライン展開のために選択されましたが、コンパイラはインライン展開を実行しませんでした。

**`__forceinline`** はよりもコンパイラに対するより強い表示ですが、 **`__inline`** コンパイラの判断でインライン展開が実行されますが、この関数をインライン展開することによる利点を判断するためのヒューリスティックは使用されません。

場合によっては、コンパイラが特定の関数を機械的にインライン化することはありません。 たとえば、コンパイラはインラインになりません。

- SEH と C++ EH の両方を混在させる場合は、関数。

- コピーによって作成されたオブジェクトを含む一部の関数は、-GX/EHs/Ehs がオンのときに値によって渡されます。

- -GX/EHs/Ehs が on の場合、値によって unwindable オブジェクトを返す関数。

- -Og/を使用せずにコンパイルするときにインラインアセンブリを使用する関数。

- 可変個引数リストを持つ関数。

- **`try`**(C++ 例外処理) ステートメントを含む関数。

次の例では、C4714 が生成されます。

```cpp
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
