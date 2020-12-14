---
description: 詳細については、「コンパイラエラー C3278」を参照してください。
title: コンパイラ エラー C3278
ms.date: 11/04/2016
f1_keywords:
- C3278
helpviewer_keywords:
- C3278
ms.assetid: 56f818f5-85a6-4792-843b-54fe16327658
ms.openlocfilehash: cdbb53b4f11357ae9058d9a5ebc3882c8701fc88
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97228964"
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
