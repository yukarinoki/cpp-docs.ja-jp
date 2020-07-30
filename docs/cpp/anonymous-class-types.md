---
title: 匿名クラス型
ms.date: 11/04/2016
helpviewer_keywords:
- class types [C++], anonymous
- anonymous class types
ms.assetid: 9ba667b2-8c2a-4c29-82a6-fa120b9233c8
ms.openlocfilehash: 77f0a5517cee5e4baeacbbdcae47bdeea2853a97
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87216636"
---
# <a name="anonymous-class-types"></a>匿名クラス型

クラスは匿名にすることができます。つまり、*識別子*なしで宣言できます。 これは、 **`typedef`** 次に示すように、クラス名を名前に置き換える場合に便利です。

```cpp
typedef struct
{
    unsigned x;
    unsigned y;
} POINT;
```

> [!NOTE]
> 前の例で示した匿名クラスの使用は、既存の C コードとの互換性を維持するために役立ちます。 一部の C コードで **`typedef`** は、匿名構造と共にを使用することは一般的です。

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

上のコードでは、 `iValue` オブジェクトメンバー選択演算子 (**.**) を使用して、次のようにを使用してにアクセスできます。

```cpp
int i = ptv.iValue;
```

匿名クラスには、特定の制限が適用されます  (匿名共用体の詳細については、「[共用体](../cpp/unions.md)」を参照してください)。匿名クラス:

- コンストラクターやデストラクターを持つことはできません。

- を引数として関数に渡すことはできません (省略記号を使用して型チェックを省略する場合を除きます)。

- 関数の戻り値として返すことはできません。

## <a name="anonymous-structs"></a>匿名構造体

**Microsoft 固有の仕様**

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

**Microsoft 固有の仕様はここまで**
