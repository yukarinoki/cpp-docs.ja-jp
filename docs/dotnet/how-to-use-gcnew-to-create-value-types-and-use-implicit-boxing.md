---
description: '詳細については、「方法: gcnew を使用して値型を作成し、暗黙的なボックス化を使用する」を参照してください。'
title: '方法: gcnew を使用して値型を作成し、暗黙的なボックス化を使用する'
ms.date: 11/04/2016
helpviewer_keywords:
- gcnew keyword [C++], creating value types
- boxing, implicit
- value types, creating
ms.assetid: ceb48841-d6bd-47be-a167-57f44c961603
ms.openlocfilehash: e58b50be4399cef6a842ce0b02e951617f143e5c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97210895"
---
# <a name="how-to-use-gcnew-to-create-value-types-and-use-implicit-boxing"></a>方法: gcnew を使用して値型を作成し、暗黙的なボックス化を使用する

値型で [gcnew](../extensions/ref-new-gcnew-cpp-component-extensions.md) を使用すると、ボックス化された値型が作成されます。これは、ガベージコレクトされたマネージヒープに配置できます。

## <a name="example"></a>例

```cpp
// vcmcppv2_explicit_boxing4.cpp
// compile with: /clr
public value class V {
public:
   int m_i;
   V(int i) : m_i(i) {}
};

public ref struct TC {
   void do_test(V^ v) {
      if (v != nullptr)
         ;
      else
         ;
   }
};

int main() {
   V^ v = gcnew V(42);
   TC^ tc = gcnew TC;
   tc->do_test(v);
}
```

## <a name="see-also"></a>関連項目

[ボックス化](../extensions/boxing-cpp-component-extensions.md)
