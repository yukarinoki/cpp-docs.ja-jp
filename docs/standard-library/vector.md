---
description: '詳細情報: &lt; vector&gt;'
title: '&lt;vector&gt;'
ms.date: 11/04/2016
f1_keywords:
- <vector>
helpviewer_keywords:
- vector header
ms.assetid: c1431ad8-c0b6-4dbb-89c4-5f651e432d7f
ms.openlocfilehash: 1f787afb00a3f94ba6b5148fe064badbc5d373ec
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97187859"
---
# <a name="ltvectorgt"></a>&lt;vector&gt;

コンテナークラステンプレートベクターといくつかのサポートテンプレートを定義します。

`vector` 指定された型の要素を直線上のシーケンスに編成するコンテナーです。 このシーケンスでは、任意の要素を高速にランダム アクセスしたり、動的に追加および削除したりできます。 `vector` は、ランダム アクセスのパフォーマンスを重視するシーケンスに適したコンテナーです。

> [!NOTE]
> ライブラリは、 \<vector> ステートメントも使用し `#include <initializer_list>` ます。

クラス `vector` の詳細については、「[vector クラス](../standard-library/vector-class.md)」をご覧ください。 特殊化の詳細については `vector<bool>` 、「 [vector \<bool> クラス](../standard-library/vector-bool-class.md)」を参照してください。

## <a name="syntax"></a>構文

```cpp
namespace std {
template <class Type, class Allocator>
class vector;
template <class Allocator>
class vector<bool>;

template <class Allocator>
struct hash<vector<bool, Allocator>>;

// TEMPLATE FUNCTIONS
template <class Type, class Allocator>
bool operator== (
    const vector<Type, Allocator>& left,
    const vector<Type, Allocator>& right);

template <class Type, class Allocator>
bool operator!= (
    const vector<Type, Allocator>& left,
    const vector<Type, Allocator>& right);

template <class Type, class Allocator>
bool operator<(
    const vector<Type, Allocator>& left,
    const vector<Type, Allocator>& right);

template <class Type, class Allocator>
bool operator> (
    const vector<Type, Allocator>& left,
    const vector<Type, Allocator>& right);

template <class Type, class Allocator>
bool operator<= (
    const vector<Type, Allocator>& left,
    const vector<Type, Allocator>& right);

template <class Type, class Allocator>
bool operator>= (
    const vector<Type, Allocator>& left,
    const vector<Type, Allocator>& right);

template <class Type, class Allocator>
void swap (
    vector<Type, Allocator>& left,
    vector<Type, Allocator>& right);

}  // namespace std
```

### <a name="parameters"></a>パラメーター

*各種*\
ベクター内に格納されるデータ型に対するテンプレート パラメーター。

*アロケーター*\
メモリの割り当てと解放を担当する格納されたアロケーター オブジェクトのテンプレート パラメーター。

*左側*\
比較演算の最初の (左辺の) ベクター

*そうです*\
比較演算の 2 つ目の (右辺の) ベクター。

## <a name="members"></a>メンバー

### <a name="operators"></a>オペレーター

|名前|説明|
|-|-|
|[operator!=](../standard-library/vector-operators.md#op_neq)|演算子の左辺のベクター オブジェクトが右辺のベクター オブジェクトと等しくないかどうかを調べます。|
|[<演算子 ](../standard-library/vector-operators.md#op_lt)|演算子の左辺のベクター オブジェクトが右辺のベクター オブジェクトより小さいかどうかを調べます。|
|[operator\<=](../standard-library/vector-operators.md#op_gt_eq)|演算子の左辺のベクター オブジェクトが右辺のベクター オブジェクト以下かどうかを調べます。|
|[operator = =](../standard-library/vector-operators.md#op_eq_eq)|演算子の左辺のベクター オブジェクトが右辺のベクター オブジェクトと等しいかどうかを調べます。|
|[>演算子 ](../standard-library/vector-operators.md#op_gt)|演算子の左辺のベクター オブジェクトが右辺のベクター オブジェクトより大きいかどうかを調べます。|
|[operator>=](../standard-library/vector-operators.md#op_gt_eq)|演算子の左辺のベクター オブジェクトが右辺のベクター オブジェクト以上かどうかを調べます。|

### <a name="classes"></a>クラス

|名前|説明|
|-|-|
|[vector クラス](../standard-library/vector-class.md)|指定された型の要素を直線上に配置し、任意の要素に対する高速なランダム アクセスを可能にするシーケンス コンテナーのクラス テンプレートです。|

### <a name="specializations"></a>特殊化

|名前|説明|
|-|-|
|hash|ベクターのハッシュを返します。|
|[vector \<bool> クラス](../standard-library/vector-bool-class.md)|**`bool`** 特殊化で使用される基になる型のアロケーターを持つ型の要素に対するクラステンプレートベクターの完全な特殊化。|

## <a name="requirements"></a>要件

**ヘッダー:**\<vector>

**名前空間:** std

## <a name="see-also"></a>関連項目

[ヘッダーファイルのリファレンス](../standard-library/cpp-standard-library-header-files.md)\
[C++ 標準ライブラリのスレッドセーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[C++ 標準ライブラリリファレンス](../standard-library/cpp-standard-library-reference.md)
