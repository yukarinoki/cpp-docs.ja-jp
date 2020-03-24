---
title: コンパイラ エラー C3278
ms.date: 11/04/2016
f1_keywords:
- C3278
helpviewer_keywords:
- C3278
ms.assetid: 56f818f5-85a6-4792-843b-54fe16327658
ms.openlocfilehash: ec51064853afa37f75022042c8c6121b6c5248a4
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80201436"
---
# <a name="compiler-error-c3278"></a>コンパイラ エラー C3278

> インターフェイスまたは純粋メソッド '*method*' の直接呼び出しは実行時に失敗します

## <a name="remarks"></a>解説

インターフェイス メソッドまたはピュア メソッドが呼び出されましたが、このような呼び出しは許可されていません。

## <a name="example"></a>例

次の例では C3278 が生成されます。

```cpp
// C3278_2.cpp
// compile with: /clr
using namespace System;
interface class I
{
   void vmf();
};

public ref class C: public I
{
public:
   void vmf()
   {
      Console::WriteLine( "In C::vmf()" );
      I::vmf(); // C3278
   }

};

int main()
{
   C^ pC = gcnew C;
   pC->vmf();
}
```
