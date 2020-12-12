---
description: 詳細については、「コンパイラエラー C3799」を参照してください。
title: コンパイラ エラー C3799
ms.date: 11/04/2016
f1_keywords:
- C3799
helpviewer_keywords:
- C3799
ms.assetid: 336a2811-9370-4e6e-b03b-325bda470805
ms.openlocfilehash: 31ada62b9bc347ce4d4889eca72d8d8e9c2987e4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97291624"
---
# <a name="compiler-error-c3799"></a>コンパイラ エラー C3799

インデックス付きプロパティに空のパラメーターリストを指定することはできません

インデックス付きプロパティが正しく宣言されていません。 詳細については、「 [方法: C++/cli でプロパティを使用](../../dotnet/how-to-use-properties-in-cpp-cli.md)する」を参照してください。

## <a name="example"></a>例

次の例では、C3799 を生成し、その修正方法を示しています。

```cpp
// C3799.cpp
// compile with: /clr /c
ref struct C {
   property int default[] {   // C3799
   // try the following line instead
   // property int default[int] {
      int get(int index) { return 0; }
      void set(int index, int value) {}
   }
};
```
