---
title: コンストラクターを持たないクラスと構造体の初期化 (C++)
ms.date: 10/17/2018
ms.assetid: 3e55c3d6-1c6b-4084-b9e5-221b151402f4
ms.openlocfilehash: 4f696f4fc8862b953e40a03c96b88d1a0b7f720b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62183415"
---
# <a name="initializing-classes-and-structs-without-constructors-c"></a>コンストラクターを持たないクラスと構造体の初期化 (C++)

クラスのコンストラクターの定義は、コンストラクターが比較的単純な場合は特に、必ずしも必要ではありません。 ユーザーは、次の例に示すように、均一初期化を使用してクラスまたは構造体のオブジェクトを初期化できます。

```cpp
// no_constructor.cpp
// Compile with: cl /EHsc no_constructor.cpp
#include <time.h>

// No constructor
struct TempData
{
    int StationId;
    time_t timeSet;
    double current;
    double maxTemp;
    double minTemp;
};

// Has a constructor
struct TempData2
{
    TempData2(double minimum, double maximum, double cur, int id, time_t t) :
       stationId{id}, timeSet{t}, current{cur}, maxTemp{maximum}, minTemp{minimum} {}
    int stationId;
    time_t timeSet;
    double current;
    double maxTemp;
    double minTemp;
};

int main()
{
    time_t time_to_set;

    // Member initialization (in order of declaration):
    TempData td{ 45978, time(&time_to_set), 28.9, 37.0, 16.7 };

    // Default initialization = {0,0,0,0,0}
    TempData td_default{};

    // Uninitialized = if used, emits warning C4700 uninitialized local variable
    TempData td_noInit;

    // Member declaration (in order of ctor parameters)
    TempData2 td2{ 16.7, 37.0, 28.9, 45978, time(&time_to_set) };

    return 0;
}
```

クラスまたは構造体にコンス トラクターがあるないとき、クラスで宣言したメンバーの順序でリスト要素を指定することに注意してください。 クラスにコンス トラクターがある場合は、パラメーターの順序で要素を提供します。

## <a name="see-also"></a>関連項目

[クラスと構造体](../cpp/classes-and-structs-cpp.md)<br/>
[コンストラクター](../cpp/constructors-cpp.md)
