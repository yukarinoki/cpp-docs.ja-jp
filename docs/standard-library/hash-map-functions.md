---
description: '詳細情報: &lt; hash_map &gt; 関数'
title: '&lt;hash_map&gt; 関数'
ms.date: 11/04/2016
f1_keywords:
- hash_map/std::swap
- hash_map/std::swap (hash_map)
ms.assetid: 28748cd0-71f7-41b9-b068-579183645fba
ms.openlocfilehash: 50f9150bc79a3ffdc586ba420d6e3dc280784767
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97231902"
---
# <a name="lthash_mapgt-functions"></a>&lt;hash_map&gt; 関数

[フォト](#swap)\
[swap (hash_map)](#swap_hash_map)

## <a name="swap-hash_map"></a><a name="swap_hash_map"></a> swap (hash_map)

> [!NOTE]
> この API は、互換性のために残されています。 代わりに、[unordered_map クラス](../standard-library/unordered-map-class.md)を使用してください。

2 つの hash_map の要素を交換します。

```cpp
void swap(
    hash_map <Key, Type, Traits, Alloctor>& left,
    hash_map <Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>パラメーター

*そうです*\
要素が *左* のマップと交換される hash_map。

*左側*\
要素がマップ *右* の要素と交換される hash_map。

### <a name="remarks"></a>解説

テンプレート関数は、コンテナー クラス hash_map に特化したアルゴリズムであり、メンバー関数 `left.`[swap](../standard-library/basic-ios-class.md#swap)*(right*) を実行します。 これは、コンパイラによる関数テンプレートの部分的な順序付けのインスタンスです。 テンプレートと関数呼び出しの照合が一意にならないようにテンプレート関数がオーバーロードされた場合、コンパイラは、最も特化したバージョンのテンプレート関数を選択します。 アルゴリズムヘッダーファイル内のテンプレート関数の **テンプレート \<class T> void Swap (t&、t&)** の一般的なバージョンは、割り当てによって動作し、処理が遅くなります。 各コンテナー内の特化バージョンのほうが、コンテナー クラスの内部表現で使用できるため大幅に高速になります。

## <a name="swap"></a><a name="swap"></a> フォト

> [!NOTE]
> この API は、互換性のために残されています。 代替が必要な場合は、 [unordered_multimap Class](../standard-library/unordered-multimap-class.md)をご使用ください。

2 つの hash_multimap の要素を交換します。

```cpp
void swap(
    hash_multimap <Key, Type, Traits, Alloctor>& left,
    hash_multimap <Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>パラメーター

*そうです*\
要素が *左* のマップと交換される hash_multimap。

*左側*\
要素がマップ *右* の要素と交換される hash_multimap。

### <a name="remarks"></a>解説

テンプレート関数は、コンテナー クラス hash_multimap に特化したアルゴリズムであり、メンバー関数 `left.`[swap](../standard-library/hash-multimap-class.md#swap)*(right*`)` を実行します。 これは、コンパイラによる関数テンプレートの部分的な順序付けのインスタンスです。 テンプレートと関数呼び出しの照合が一意にならないようにテンプレート関数がオーバーロードされた場合、コンパイラは、最も特化したバージョンのテンプレート関数を選択します。 アルゴリズムヘッダーファイル内のテンプレート関数の **テンプレート \<class T> void Swap (t&、t&)** の一般的なバージョンは、割り当てによって動作し、処理が遅くなります。 各コンテナー内の特化バージョンのほうが、コンテナー クラスの内部表現で使用できるため大幅に高速になります。

## <a name="see-also"></a>関連項目

[<hash_map>](../standard-library/hash-map.md)
