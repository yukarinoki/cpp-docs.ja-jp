---
title: '&lt;map&gt; 系関数'
ms.date: 11/04/2016
f1_keywords:
- map/std::swap (map)
- map/std::swap (multimap)
ms.assetid: 7cb3d1a5-7add-4726-a73f-61927eafd466
ms.openlocfilehash: e7876b37bfc006eaecf2f1e36273c5ae8689dad4
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2020
ms.locfileid: "79425527"
---
# <a name="ltmapgt-functions"></a>&lt;map&gt; 系関数

## <a name="swap_multimap"></a>スワップ (マップ)

2 つの map の要素を交換します。

```cpp
template <class key, class T, class _Pr, class _Alloc>
void swap(
    map<Key, Traits, Compare, Alloctor>& left,
    map<Key, Traits, Compare, Alloctor>& right);
```

### <a name="parameters"></a>パラメーター

*右*\
交換する要素を提供するマップ、またはマップの*左側*の要素と交換される要素を持つマップ。

*左*\
マップ*右側*の要素と交換される要素を持つマップ。

### <a name="remarks"></a>解説

このテンプレート関数は、コンテナークラス map に特化したアルゴリズムであり、`left`メンバー関数を実行します。[swap](../standard-library/map-class.md#swap)(`right`)。 これは、コンパイラによる関数テンプレートの部分的な順序付けのインスタンスです。 テンプレートと関数呼び出しの照合が一意にならないようにテンプレート関数がオーバーロードされた場合、コンパイラは、最も特化したバージョンのテンプレート関数を選択します。 汎用バージョンのテンプレート関数、**テンプレート**\<**クラス t**> **void swap**( **t &** 、 **t &** ) は、代入によって機能し、処理が遅くなります。 各コンテナー内の特化バージョンのほうが、コンテナー クラスの内部表現で使用できるため大幅に高速になります。

### <a name="example"></a>例

[ のテンプレート バージョンの使用例については、メンバー関数 ](../standard-library/map-class.md#swap)map::swap`swap` のコード例をご覧ください。

## <a name="swap"></a>swap (multimap)

2 つの multimap の要素を交換します。

```cpp
template <class key, class T, class _Pr, class _Alloc>
void swap(
    multimap<Key, Traits, Compare, Alloctor>& left,
    multimap<Key, Traits, Compare, Alloctor>& right);
```

### <a name="parameters"></a>パラメーター

*右*\
交換する要素を提供する multimap、また*は multimap の*要素と交換される要素を持つ multimap。

*左*\
要素が multimap *right*の要素と交換される multimap。

### <a name="remarks"></a>解説

このテンプレート関数は、コンテナークラス multimap に特化したアルゴリズムであり、メンバー関数 `left`を実行するためにコンテナークラスで実行されます。[swap](../standard-library/multimap-class.md#swap) (`right`)。 これは、コンパイラによる関数テンプレートの部分的な順序付けのインスタンスです。 テンプレートと関数呼び出しの照合が一意にならないようにテンプレート関数がオーバーロードされた場合、コンパイラは、最も特化したバージョンのテンプレート関数を選択します。 汎用バージョンのテンプレート関数、**テンプレート**\<**クラス t**> **void swap**( **t &** 、 **t &** ) は、代入によって機能し、処理が遅くなります。 各コンテナー内の特化バージョンのほうが、コンテナー クラスの内部表現で使用できるため大幅に高速になります。

### <a name="example"></a>例

[ のテンプレート バージョンの使用例については、メンバー関数 ](../standard-library/multimap-class.md#swap)multimap::swap`swap` のコード例をご覧ください。
