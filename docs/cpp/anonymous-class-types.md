---
title: 匿名クラス型
ms.date: 11/04/2016
helpviewer_keywords:
- class types [C++], anonymous
- anonymous class types
ms.assetid: 9ba667b2-8c2a-4c29-82a6-fa120b9233c8
ms.openlocfilehash: e227f48588c3c4f59c0d0bd28ab16178de159b58
ms.sourcegitcommit: 89d9e1cb08fa872483d1cde98bc2a7c870e505e9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "82032084"
---
# <a name="anonymous-class-types"></a>匿名クラス型

クラスは匿名で指定できます。 *identifier* これは、次のように、クラス名を**typedef**名に置き換える場合に役立ちます。

```cpp
typedef struct
{
    unsigned x;
    unsigned y;
} POINT;
```

> [!NOTE]
> 前の例で示した匿名クラスの使用は、既存の C コードとの互換性を維持するために役立ちます。 C コードによっては、匿名構造体と組み合わせて**typedef**を使用することが一般的です。

匿名クラスは、次のように、クラス メンバーへの参照が別のクラスに含まれていないかのように見せる場合にも役立ちます。

```cpp
struct PTValue
{
    POINT ptLoc;
    union
    {
        int  iValue;
        long lValue;
    };
};

PTValue ptv;
```

上記のコードでは、`iValue`次のようにオブジェクト メンバ選択演算子 (**.**) を使用してアクセスできます。

```cpp
int i = ptv.iValue;
```

匿名クラスには、特定の制限が適用されます  (匿名共用体の詳細については、「[ユニオン](../cpp/unions.md)」を参照してください。匿名クラス:

- コンストラクターやデストラクターを持つことはできません。

- 関数に引数として渡すことはできません (省略記号を使用して型チェックが負けない場合)。

- 関数の戻り値として返すことはできません。

## <a name="anonymous-structs"></a>匿名構造体

**マイクロソフト固有**

Microsoft の C 拡張機能を使用すれば、名前を指定せずに、別の構造体内に構造体変数を宣言できます。 このような入れ子の構造体を "匿名構造体" といいます。 C++ では匿名構造体を使用できません。

匿名構造体のメンバーには、包含構造体のメンバーと同じようにアクセスできます。

```cpp
// anonymous_structures.c
#include <stdio.h>

struct phone
{
    int  areacode;
    long number;
};

struct person
{
    char   name[30];
    char   gender;
    int    age;
    int    weight;
    struct phone;    // Anonymous structure; no name needed
} Jim;

int main()
{
    Jim.number = 1234567;
    printf_s("%d\n", Jim.number);
}
//Output: 1234567
```

**エンド マイクロソフト 固有**
