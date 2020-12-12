---
description: 詳しくは、「プロパティ (C++)」をご覧ください。
title: property (C++)
ms.date: 11/04/2016
f1_keywords:
- property_cpp
helpviewer_keywords:
- property __declspec keyword
- __declspec keyword [C++], property
ms.assetid: f3b850ba-bf48-4df7-a1d6-8259d97309ce
ms.openlocfilehash: ed996ecadd16837af1e28b71bbedd9b4e3c1abaa
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97299164"
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

コンパイラは、メンバー選択演算子 ("**.**" または "") の右側でこの属性を使用して宣言されたデータメンバーを認識すると **->** 、 `get` その `put` ような式が左辺値または右辺値のいずれであるかに応じて、演算をまたは関数に変換します。 "" などのより複雑なコンテキストで `+=` は、との両方を実行して書き直しが実行され `get` `put` ます。

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

## <a name="see-also"></a>関連項目

[__declspec](../cpp/declspec.md)<br/>
[キーワード](../cpp/keywords-cpp.md)
