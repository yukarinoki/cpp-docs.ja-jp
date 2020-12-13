---
description: '詳細情報: &lt; map &gt; 関数'
title: '&lt;map&gt; 系関数'
ms.date: 11/04/2016
f1_keywords:
- map/std::swap (map)
- map/std::swap (multimap)
ms.assetid: 7cb3d1a5-7add-4726-a73f-61927eafd466
ms.openlocfilehash: dded58c4af44bca08a5cb9e2cd0436974f48f6c8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97149514"
---
# <a name="ltmapgt-functions"></a>&lt;map&gt; 系関数

## <a name="swap-map"></a><a name="swap_multimap"></a> スワップ (マップ)

2 つの map の要素を交換します。

```cpp
template <class key, class T, class _Pr, class _Alloc>
void swap(
    map<Key, Traits, Compare, Alloctor>& left,
    map<Key, Traits, Compare, Alloctor>& right);
```

### <a name="parameters"></a>パラメーター

*そうです*\
交換する要素を提供するマップ、またはマップの *左側* の要素と交換される要素を持つマップ。

*左側*\
マップ *右側* の要素と交換される要素を持つマップ。

### <a name="remarks"></a>解説

このテンプレート関数は、コンテナークラス map に特化したアルゴリズムで、メンバー関数を実行し `left` ます。[swap](../standard-library/map-class.md#swap)( `right` )。 これは、コンパイラによる関数テンプレートの部分的な順序付けのインスタンスです。 テンプレートと関数呼び出しの照合が一意にならないようにテンプレート関数がオーバーロードされた場合、コンパイラは、最も特化したバージョンのテンプレート関数を選択します。 アルゴリズムクラスの一般的なバージョンのテンプレート関数である **`template`** \< **class T**> **void swap**( **t&**、 **t&**) は、割り当てによって動作し、処理が遅くなります。 各コンテナー内の特化バージョンのほうが、コンテナー クラスの内部表現で使用できるため大幅に高速になります。

### <a name="example"></a>例

`swap` のテンプレート バージョンの使用例については、メンバー関数 [map::swap](../standard-library/map-class.md#swap) のコード例をご覧ください。

## <a name="swap-multimap"></a><a name="swap"></a> swap (multimap)

2 つの multimap の要素を交換します。

```cpp
template <class key, class T, class _Pr, class _Alloc>
void swap(
    multimap<Key, Traits, Compare, Alloctor>& left,
    multimap<Key, Traits, Compare, Alloctor>& right);
```

### <a name="parameters"></a>パラメーター

*そうです*\
交換する要素を提供する multimap、また *は multimap の* 要素と交換される要素を持つ multimap。

*左側*\
要素が multimap *right* の要素と交換される multimap。

### <a name="remarks"></a>解説

このテンプレート関数は、コンテナークラスの map に特化したアルゴリズムで、メンバー関数を実行するためにコンテナークラス multimap で実行され `left` ます。[swap](../standard-library/multimap-class.md#swap) ( `right` )。 これは、コンパイラによる関数テンプレートの部分的な順序付けのインスタンスです。 テンプレートと関数呼び出しの照合が一意にならないようにテンプレート関数がオーバーロードされた場合、コンパイラは、最も特化したバージョンのテンプレート関数を選択します。 アルゴリズムクラスの一般的なバージョンのテンプレート関数である **`template`** \< **class T**> **void swap**( **t&**、 **t&**) は、割り当てによって動作し、処理が遅くなります。 各コンテナー内の特化バージョンのほうが、コンテナー クラスの内部表現で使用できるため大幅に高速になります。

### <a name="example"></a>例

`swap` のテンプレート バージョンの使用例については、メンバー関数 [multimap::swap](../standard-library/multimap-class.md#swap) のコード例をご覧ください。
