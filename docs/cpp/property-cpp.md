---
title: property (C++)
ms.date: 11/04/2016
f1_keywords:
- property_cpp
helpviewer_keywords:
- property __declspec keyword
- __declspec keyword [C++], property
ms.assetid: f3b850ba-bf48-4df7-a1d6-8259d97309ce
ms.openlocfilehash: 03f71739698fd20a01fd72567ce5b9babc176327
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80179303"
---
# <a name="property-c"></a>property (C++)

**Microsoft 固有の仕様**

この属性は、クラスまたは構造体の定義の非静的 "仮想データ メンバー" に適用できます。 コンパイラは、参照を関数呼び出しに変更することにより、これらの "仮想データ メンバー" をデータ メンバーとして処理します。

## <a name="syntax"></a>構文

```
   __declspec( property( get=get_func_name ) ) declarator
   __declspec( property( put=put_func_name ) ) declarator
   __declspec( property( get=get_func_name, put=put_func_name ) ) declarator
```

## <a name="remarks"></a>解説

コンパイラが、メンバー選択演算子 (" **.** " または " **->** ") の右側でこの属性を使用して宣言されたデータメンバーを認識すると、その式が左辺値または右辺値のいずれであるかに応じて、操作を `get` または `put` 関数に変換します。 "`+=`" などのより複雑なコンテキストでは、`get` と `put`の両方を実行することで書き直しが実行されます。

この属性は、クラスまたは構造体の定義の空の配列の宣言でも使用できます。 次に例を示します。

```cpp
__declspec(property(get=GetX, put=PutX)) int x[];
```

前のステートメントは、`x[]` を 1 つ以上の配列インデックスで使用できることを示します。 この例では、`i=p->x[a][b]` は `i=p->GetX(a, b)` になります。また、`p->x[a][b] = i` は `p->PutX(a, b, i);` になります。

**Microsoft 固有の仕様はここまで**

## <a name="example"></a>例

```cpp
// declspec_property.cpp
struct S {
   int i;
   void putprop(int j) {
      i = j;
   }

   int getprop() {
      return i;
   }

   __declspec(property(get = getprop, put = putprop)) int the_prop;
};

int main() {
   S s;
   s.the_prop = 5;
   return s.the_prop;
}
```

## <a name="see-also"></a>参照

[__declspec](../cpp/declspec.md)<br/>
[キーワード](../cpp/keywords-cpp.md)
