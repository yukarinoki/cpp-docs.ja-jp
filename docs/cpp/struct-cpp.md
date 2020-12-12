---
description: '詳細情報: 構造体 (C++)'
title: struct (C++ )
ms.date: 11/04/2016
f1_keywords:
- struct_cpp
helpviewer_keywords:
- struct constructors
ms.assetid: 3c6ba273-e248-4ff1-8c69-d2abcf1263c6
ms.openlocfilehash: 4c7f8ab04bec2f161e303c3fed93414332fddeb6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97246254"
---
# <a name="struct-c"></a>struct (C++ )

キーワードは、構造体 **`struct`** 型または構造体型の変数を定義します。

## <a name="syntax"></a>構文

```
[template-spec] struct [ms-decl-spec] [tag [: base-list ]]
{
   member-list
} [declarators];
[struct] tag declarators;
```

#### <a name="parameters"></a>パラメーター

*テンプレート-仕様*<br/>
テンプレートの指定 (省略可能)。 詳細については、「 [テンプレートの仕様](templates-cpp.md)」を参照してください。

*struct*<br/>
**`struct`** キーワード。

*ms の宣言*<br/>
ストレージ クラスの指定 (省略可能)。 詳細については、 [__declspec](../cpp/declspec.md) キーワードを参照してください。

*タグ*<br/>
構造体に渡す型名。 タグは構造体のスコープ内で予約語になります。 タグは省略できます。 省略した場合、匿名構造体が定義されます。 詳細については、「 [匿名クラス型](../cpp/anonymous-class-types.md)」を参照してください。

*base-list*<br/>
この構造体がメンバーを継承するクラスまたは構造体のリスト (省略可能)。 詳細については、「 [基底クラス](../cpp/base-classes.md) 」を参照してください。 各基底クラスまたは構造体の名前の前には、アクセス指定子 ([public](../cpp/public-cpp.md)、 [private](../cpp/private-cpp.md)、 [protected](../cpp/protected-cpp.md)) と [virtual](../cpp/virtual-cpp.md) キーワードを付けることができます。 詳細については、「 [クラスメンバーへのアクセスの制御](member-access-control-cpp.md) 」のメンバーアクセステーブルを参照してください。

*メンバーリスト*<br/>
構造体のメンバーのリスト。 詳細については、 [クラスメンバーの概要](../cpp/class-member-overview.md) に関するトピックを参照してください。 ここでの唯一の違いは、 **`struct`** の代わりにを使用することです **`class`** 。

*declarators*<br/>
構造体の名前を指定する宣言子リスト。 宣言子リストは構造体型の 1 つ以上のインスタンスを宣言します。 構造体のすべてのデータメンバーがである場合は、宣言子に初期化子リストを含めることができ **`public`** ます。 初期化子リストは、データメンバーが既定であるため、構造で共通 **`public`** です。  詳細については、「 [宣言子の概要](./declarations-and-definitions-cpp.md) 」を参照してください。

## <a name="remarks"></a>解説

構造体型はユーザー定義の複合データ型です。 この型は異なる型のフィールドやメンバーで構成されます。

C++ では、構造体はクラスと同じですが、そのメンバーが既定でである点が異なり **`public`** ます。

C++/CLI のマネージクラスと構造体の詳細については、「 [クラスと構造体](../extensions/classes-and-structs-cpp-component-extensions.md)」を参照してください。

## <a name="using-a-structure"></a>構造体の使用

C では、 **`struct`** 構造体を宣言するためにキーワードを明示的に使用する必要があります。 C++ では、 **`struct`** 型が定義された後にキーワードを使用する必要はありません。

右中かっことセミコロンの間に 1 つ以上のコンマ区切りの変数名を挿入することで構造体型を定義している場合は、変数を宣言してもかまいません。

構造体の変数は初期化できます。 各変数の初期化は中かっこで囲む必要があります。

関連情報については、「 [クラス](../cpp/class-cpp.md)、 [共用体](../cpp/unions.md)、および [列挙型](../cpp/enumerations-cpp.md)」を参照してください。

## <a name="example"></a>例

```cpp
#include <iostream>
using namespace std;

struct PERSON {   // Declare PERSON struct type
    int age;   // Declare member types
    long ss;
    float weight;
    char name[25];
} family_member;   // Define object of type PERSON

struct CELL {   // Declare CELL bit field
    unsigned short character  : 8;  // 00000000 ????????
    unsigned short foreground : 3;  // 00000??? 00000000
    unsigned short intensity  : 1;  // 0000?000 00000000
    unsigned short background : 3;  // 0???0000 00000000
    unsigned short blink      : 1;  // ?0000000 00000000
} screen[25][80];       // Array of bit fields

int main() {
    struct PERSON sister;   // C style structure declaration
    PERSON brother;   // C++ style structure declaration
    sister.age = 13;   // assign values to members
    brother.age = 7;
    cout << "sister.age = " << sister.age << '\n';
    cout << "brother.age = " << brother.age << '\n';

    CELL my_cell;
    my_cell.character = 1;
    cout << "my_cell.character = " << my_cell.character;
}
// Output:
// sister.age = 13
// brother.age = 7
// my_cell.character = 1
```
