---
title: 配列の初期化
ms.date: 11/04/2016
helpviewer_keywords:
- initializing arrays [C++]
- arrays [C++], initializing
ms.assetid: 41efe5f0-15b5-4f49-9196-c4902f8fc705
ms.openlocfilehash: e055e7759865fc151176097c6f0afd9ee237f4c1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62183428"
---
# <a name="initializing-arrays"></a>配列の初期化

クラスにコンストラクターがある場合、そのクラスの配列はコンストラクターによって初期化されます。 配列の要素よりも初期化子リスト内の項目が少ない場合、残りの要素には既定のコンストラクターが使用されます。 クラスに対して既定のコンストラクターが定義されていない場合は、完全な初期化子リストが必要です。つまり、配列の各要素に 1 つずつ初期化子が必要です。

2 つのコンストラクターを定義する `Point` クラスを考えます。

```cpp
// initializing_arrays1.cpp
class Point
{
public:
   Point()   // Default constructor.
   {
   }
   Point( int, int )   // Construct from two ints
   {
   }
};

// An array of Point objects can be declared as follows:
Point aPoint[3] = {
   Point( 3, 3 )     // Use int, int constructor.
};

int main()
{
}
```

`aPoint` の最初の要素はコンストラクター `Point( int, int )` を使用して構築されます。残りの 2 つの要素は既定のコンストラクターを使用して構築されます。

静的メンバー配列 (かどうか**const**か) の定義 (宣言の外側のクラス) で初期化することができます。 例:

```cpp
// initializing_arrays2.cpp
class WindowColors
{
public:
    static const char *rgszWindowPartList[7];
};

const char *WindowColors::rgszWindowPartList[7] = {
    "Active Title Bar", "Inactive Title Bar", "Title Bar Text",
    "Menu Bar", "Menu Bar Text", "Window Background", "Frame"   };
int main()
{
}
```