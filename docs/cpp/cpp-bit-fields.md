---
title: C++ ビット フィールド
ms.date: 11/19/2018
helpviewer_keywords:
- bitfields [C++]
- fields [C++], bit
- bit fields
ms.assetid: 6f4b62e3-cc1d-4e5d-bf34-05904104f71a
ms.openlocfilehash: 747920378472cc091928a080e303a0543e287aaa
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62154718"
---
# <a name="c-bit-fields"></a>C++ ビット フィールド

クラスと構造体には、整数型よりも記憶領域の占有率が少ないメンバーを含めることができます。 これらのメンバーは、ビット フィールドとして指定されます。 ビット フィールドの構文は、*メンバー宣言子*仕様次のとおりです。

## <a name="syntax"></a>構文

*declarator* **:** *constant-expression*

## <a name="remarks"></a>Remarks

(オプション)*宣言子*プログラムのメンバーにアクセスされる名前を指定します。 整数型 (列挙型を含む) である必要があります。 *定数式*構造体のメンバーが占有するビット数を指定します。 匿名ビット フィールド (つまり、識別子のないビット フィールド メンバー) はパディング用に使用できます。

> [!NOTE]
> 幅 0 の名前のないビット フィールドでは、次のビット フィールドの配置を強制的に、[次へ]**型**境界、場所**型**メンバーの種類です。

次の例では、ビット フィールドを持つ構造体を宣言します。

```cpp
// bit_fields1.cpp
// compile with: /LD
struct Date {
   unsigned short nWeekDay  : 3;    // 0..7   (3 bits)
   unsigned short nMonthDay : 6;    // 0..31  (6 bits)
   unsigned short nMonth    : 5;    // 0..12  (5 bits)
   unsigned short nYear     : 8;    // 0..100 (8 bits)
};
```

`Date` 型のオブジェクトの概念的なメモリ レイアウトを次の図に示します。

![Date オブジェクトのメモリ レイアウト](../cpp/media/vc38uq1.png "日オブジェクトのメモリ レイアウト") <br/>
データ オブジェクトのメモリ レイアウト

なお`nYear`8 ビット長であり、宣言型のワード境界をオーバーフローする**unsigned** **short**します。 そのため、新しいの先頭で開始されます**unsigned** **short**します。 すべてのビット フィールドが基になる型の 1 つのオブジェクトに収まる必要はありません。宣言で要求されたビット数に従って、ストレージの新しい単位が割り当てられます。

**Microsoft 固有の仕様**

ビット フィールドとして宣言されたデータの順序は、上の図に示すように、下位から上位のビットへ向います。

**Microsoft 固有の仕様はここまで**

構造体の宣言に、次の例のように、名前の付いていない長さが 0 のフィールドが含まれている場合、

```cpp
// bit_fields2.cpp
// compile with: /LD
struct Date {
   unsigned nWeekDay  : 3;    // 0..7   (3 bits)
   unsigned nMonthDay : 6;    // 0..31  (6 bits)
   unsigned           : 0;    // Force alignment to next boundary.
   unsigned nMonth    : 5;    // 0..12  (5 bits)
   unsigned nYear     : 8;    // 0..100 (8 bits)
};
```

メモリ レイアウトは、次の図に示すようには。

![ゼロのデータ オブジェクトのレイアウト&#45;ビット フィールドの長さ](../cpp/media/vc38uq2.png "0 でレイアウトの Date オブジェクト&#45;ビット フィールドの長さ") <br/>
長さ 0 のビット フィールドを持つデータ オブジェクトのレイアウト

ビット フィールドの基になる型」の説明に従って、整数型である必要があります[基本的な型](../cpp/fundamental-types-cpp.md)します。

場合、初期化子の型の参照を`const T&`を左辺値参照型のビット フィールドには、`T`参照は直接ビット フィールドにバインドされません。 代わりに、参照は、ビット フィールドの値を保持する初期化一時的にバインドされます。

## <a name="restrictions-on-bit-fields"></a>ビット フィールドの制約

次の一覧は、ビット フィールドの不適切な操作を詳述します。

- ビット フィールドのアドレスの取得。

- 以外の初期化**const**ビット フィールドで参照します。

## <a name="see-also"></a>関連項目

[クラスと構造体](../cpp/classes-and-structs-cpp.md)