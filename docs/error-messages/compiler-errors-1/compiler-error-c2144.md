---
title: コンパイラ エラー C2144
ms.date: 11/04/2016
f1_keywords:
- C2144
helpviewer_keywords:
- C2144
ms.assetid: 49f3959b-324f-4c06-9588-c0ecef5dc5b3
ms.openlocfilehash: b917c0a2c15aeb70222c948bce9a6fb275c91068
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80207247"
---
# <a name="compiler-error-c2144"></a>コンパイラ エラー C2144

> 構文エラー: '*type*' の前には '*token*' を指定しなければなりません

コンパイラでは*トークン*が必要ですが、*型*が見つかりました。

このエラーは、右中かっこ、右かっこ、またはセミコロンがないことが原因で発生する場合があります。

C2144 は、空白文字を含む CLR キーワードからマクロを作成しようとしたときにも発生する可能性があります。

型の転送を実行しようとしている場合は、C2144 も表示されることがあります。 詳細については、「[型の転送C++(/cli)](../../extensions/type-forwarding-cpp-cli.md) 」を参照してください。

## <a name="examples"></a>例

次の例では、C2144 を生成し、その修正方法を示しています。

```cpp
// C2144.cpp
// compile with: /clr /c
#define REF ref
REF struct MyStruct0;   // C2144

// OK
#define REF1 ref struct
REF1 MyStruct1;
```

次の例では、C2144 を生成し、その修正方法を示しています。

```cpp
// C2144_2.cpp
// compile with: /clr /c
ref struct X {

   property double MultiDimProp[,,] {   // C2144
   // try the following line instead
   // property double MultiDimProp[int , int, int] {
      double get(int, int, int) { return 1; }
      void set(int i, int j, int k, double l) {}
   }

   property double MultiDimProp2[] {   // C2144
   // try the following line instead
   // property double MultiDimProp2[int] {
      double get(int) { return 1; }
      void set(int i, double l) {}
   }
};
```
