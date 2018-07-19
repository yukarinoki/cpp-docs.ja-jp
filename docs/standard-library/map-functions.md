---
title: '&lt;map&gt; 系関数 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- map/std::swap (map)
- map/std::swap (multimap)
ms.assetid: 7cb3d1a5-7add-4726-a73f-61927eafd466
ms.openlocfilehash: 3c6cb7d0308e4bafc531fe0baf0c5d666228c3ec
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/11/2018
ms.locfileid: "38966369"
---
# <a name="ltmapgt-functions"></a>&lt;map&gt; 系関数

|||
|-|-|
|[swap (map)](#swap)|[swap (multimap)](#swap_multimap)|

## <a name="swap_multimap"></a>  swap  (map)

2 つの map の要素を交換します。

```cpp
template <class key, class T, class _Pr, class _Alloc>
void swap(
    map<Key, Traits, Compare, Alloctor>& left,
    map<Key, Traits, Compare, Alloctor>& right);
```

### <a name="parameters"></a>パラメーター

*適切な*を交換する要素を提供するマップまたはマップのものと交換される要素がマップ*左*します。

*左*要素を持つ、map と交換されるマップ*右*します。

### <a name="remarks"></a>Remarks

テンプレート関数はメンバー関数を実行するコンテナー クラス map に特化したアルゴリズム`left`.[スワップ](../standard-library/map-class.md#swap)( `right`)。 これは、コンパイラによる関数テンプレートの部分的な順序付けのインスタンスです。 テンプレートと関数呼び出しの照合が一意にならないようにテンプレート関数がオーバーロードされた場合、コンパイラは、最も特化したバージョンのテンプレート関数を選択します。 テンプレート関数の一般的なバージョンであり、algorithm クラスにある **template** \< **class T**> **void swap**(**T&**, **T&**) は、代入によって機能し、処理が低速です。 各コンテナー内の特化バージョンのほうが、コンテナー クラスの内部表現で使用できるため大幅に高速になります。

### <a name="example"></a>例

`swap` のテンプレート バージョンの使用例については、メンバー関数 [map::swap](../standard-library/map-class.md#swap) のコード例をご覧ください。

## <a name="swap"></a>  swap  (multimap)

2 つの multimap の要素を交換します。

```cpp
template <class key, class T, class _Pr, class _Alloc>
void swap(
    multimap<Key, Traits, Compare, Alloctor>& left,
    multimap<Key, Traits, Compare, Alloctor>& right);
```

### <a name="parameters"></a>パラメーター

*適切な*を交換する要素を提供する multimap または要素が multimap のものと交換される multimap*左*します。

*左*要素が multimap のものと交換される multimap*右*します。

### <a name="remarks"></a>Remarks

テンプレート関数はメンバー関数を実行するコンテナー クラス multimap 上で実行するコンテナー クラス map に特化したアルゴリズム`left`.[スワップ](../standard-library/multimap-class.md#swap)(`right`)。 これは、コンパイラによる関数テンプレートの部分的な順序付けのインスタンスです。 テンプレートと関数呼び出しの照合が一意にならないようにテンプレート関数がオーバーロードされた場合、コンパイラは、最も特化したバージョンのテンプレート関数を選択します。 テンプレート関数の一般的なバージョンであり、algorithm クラスにある **template** \< **class T**> **void swap**(**T&**, **T&**) は、代入によって機能し、処理が低速です。 各コンテナー内の特化バージョンのほうが、コンテナー クラスの内部表現で使用できるため大幅に高速になります。

### <a name="example"></a>例

`swap` のテンプレート バージョンの使用例については、メンバー関数 [multimap::swap](../standard-library/multimap-class.md#swap) のコード例をご覧ください。

## <a name="see-also"></a>関連項目

[\<map>](../standard-library/map.md)<br/>
