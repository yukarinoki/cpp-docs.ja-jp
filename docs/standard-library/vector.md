---
title: '&lt;vector&gt; | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- <vector>
dev_langs:
- C++
helpviewer_keywords:
- vector header
ms.assetid: c1431ad8-c0b6-4dbb-89c4-5f651e432d7f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f9a94fbf8ae46c2abf65fc0229bbb2faa54d695f
ms.sourcegitcommit: 1d9bd38cacbc783fccd3884b7b92062161c91c84
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/03/2018
ms.locfileid: "48235024"
---
# <a name="ltvectorgt"></a>&lt;vector&gt;

コンテナー テンプレート クラス vector と、いくつかのサポート テンプレートを定義します。

`vector` 指定された型の要素を直線上のシーケンスに編成するコンテナーです。 このシーケンスでは、任意の要素を高速にランダム アクセスしたり、動的に追加および削除したりできます。 `vector` は、ランダム アクセスのパフォーマンスを重視するシーケンスに適したコンテナーです。

クラス `vector` の詳細については、「[vector クラス](../standard-library/vector-class.md)」をご覧ください。 特殊化 `vector<bool>` の詳細については、「[vector\<bool> クラス](../standard-library/vector-bool-class.md)」をご覧ください。

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

*Type*<br/>
ベクター内に格納されるデータ型に対するテンプレート パラメーター。

*アロケーター*<br/>
メモリの割り当てと解放を担当する格納されたアロケーター オブジェクトのテンプレート パラメーター。

*left*<br/>
比較演算の最初の (左辺の) ベクター

*right*<br/>
比較演算の 2 つ目の (右辺の) ベクター。

### <a name="operators"></a>演算子

|演算子|説明|
|-|-|
|[operator! =](../standard-library/vector-operators.md#op_neq)|演算子の左辺のベクター オブジェクトが右辺のベクター オブジェクトと等しくないかどうかを調べます。|
|[operator<](../standard-library/vector-operators.md#op_lt)|演算子の左辺のベクター オブジェクトが右辺のベクター オブジェクトより小さいかどうかを調べます。|
|[operator\<=](../standard-library/vector-operators.md#op_gt_eq)|演算子の左辺のベクター オブジェクトが右辺のベクター オブジェクト以下かどうかを調べます。|
|[operator==](../standard-library/vector-operators.md#op_eq_eq)|演算子の左辺のベクター オブジェクトが右辺のベクター オブジェクトと等しいかどうかを調べます。|
|[operator>](../standard-library/vector-operators.md#op_gt)|演算子の左辺のベクター オブジェクトが右辺のベクター オブジェクトより大きいかどうかを調べます。|
|[operator>=](../standard-library/vector-operators.md#op_gt_eq)|演算子の左辺のベクター オブジェクトが右辺のベクター オブジェクト以上かどうかを調べます。|

### <a name="classes"></a>クラス

|クラス|説明|
|-|-|
|[vector クラス](../standard-library/vector-class.md)|指定された型の要素を直線上に配置し、任意の要素に対する高速なランダム アクセスを可能にするシーケンス コンテナーのテンプレート クラスです。|

### <a name="specializations"></a>特殊化

|||
|-|-|
|[vector\<bool> クラス](../standard-library/vector-bool-class.md)|テンプレート クラス vector を型 `bool` の要素に対して完全に特殊化したもので、基になる型のアロケーターを特殊化で使用します。|

## <a name="requirements"></a>要件

**ヘッダー:** \<vector>

**名前空間:** std

## <a name="see-also"></a>関連項目

[ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)<br/>
[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++ 標準ライブラリ リファレンス](../standard-library/cpp-standard-library-reference.md)<br/>
