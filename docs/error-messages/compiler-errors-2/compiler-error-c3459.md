---
description: 詳細については、「コンパイラエラー C3459」を参照してください。
title: コンパイラ エラー C3459
ms.date: 11/04/2016
f1_keywords:
- C3459
helpviewer_keywords:
- C3459
ms.assetid: 3d290a20-d313-4c07-9bd8-c5c159cb169f
ms.openlocfilehash: 862dd9b2f84a44db2e2cd08b918938b14692e18d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97113572"
---
# <a name="compiler-error-c3459"></a>コンパイラ エラー C3459

'attribute': 属性は、クラス インデクサー (既定のインデックス付きのプロパティ) のみに使用できます

クラス インデクサー プロパティに適用されるように設計された属性が正しく使用されていません。

詳細については、「 [方法: C++/cli でプロパティを使用](../../dotnet/how-to-use-properties-in-cpp-cli.md)する」を参照してください。

## <a name="example"></a>例

次の例では C3459 が生成されます。

```cpp
// C3459.cpp
// compile with: /clr /c
public ref class MyString {
public:
   [System::Runtime::CompilerServices::IndexerName("Chars")]   // C3459
   property int Prop;
};

// OK
public ref class MyString2 {
   array<int>^ MyArr;
public:
   MyString2() {
      MyArr = gcnew array<int>(5);
   }

   [System::Runtime::CompilerServices::IndexerName("Chars")]   // OK
   property int default[int] {
      int get(int index) {
         return MyArr[index];
      }
      void set(int index, int value) {
         MyArr[index] = value;
      }
   }
};
```
