---
title: value_compare クラス (&lt;map&gt;)
ms.date: 11/04/2016
f1_keywords:
- std::value_compare
- std.value_compare
- map/std::value_compare
helpviewer_keywords:
- std::value_compare
ms.assetid: ea97c1d0-04b2-4d42-8d96-23522c04cc41
ms.openlocfilehash: 1f872edce6f0114be7c90a8108ba248fd793a989
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2020
ms.locfileid: "79447585"
---
# <a name="value_compare-class-ltmapgt"></a>value_compare クラス (&lt;map&gt;)

要素のキーの値を比較し要素のマップ内の相対順序を決定して、マップの要素を比較できる関数オブジェクトを提供します。

## <a name="syntax"></a>構文

```cpp
class value_compare : public binary_function<value_type, value_type, bool>
{
public:
    bool operator()(const value_type& left, const value_type& right) const;
    value_compare(key_compare pred) : comp(pred);
protected:
    key_compare comp;
};
```

## <a name="remarks"></a>コメント

マップに含まれる要素全体の `value_types` 間の `value_compare` によって提供される比較の基準は、補助型クラスの構築によって各要素のキーを比較することによって発生します。 メンバー関数の演算子は、`value_compare` によって提供される関数オブジェクトに格納されている `key_compare` 型のオブジェクト `comp` を使用して、2つの要素の並べ替えキーコンポーネントを比較します。

セットとマルチセット (キーの値が要素の値と同一である単純なコンテナー) の場合、`value_compare` は `key_compare` と等価です。マップとマルチマップの場合、型 `pair` の要素の値が要素のキーの値と同一ではないため、その 2 つは等価ではありません。

## <a name="example"></a>例

[ の宣言方法や使用方法の例については、](../standard-library/map-class.md#value_comp)value_comp`value_compare`の例を参照してください。

## <a name="requirements"></a>要件

**ヘッダー:** \<マップ >

**名前空間:** std

## <a name="see-also"></a>参照

[binary_function 構造体](../standard-library/binary-function-struct.md)\
[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[C++ 標準ライブラリ リファレンス](../standard-library/cpp-standard-library-reference.md)
