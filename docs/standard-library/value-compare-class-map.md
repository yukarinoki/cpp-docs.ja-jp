---
description: '詳細情報: value_compare クラス ( &lt; map &gt; )'
title: value_compare クラス (&lt;map&gt;)
ms.date: 11/04/2016
f1_keywords:
- std::value_compare
- std.value_compare
- map/std::value_compare
helpviewer_keywords:
- std::value_compare
ms.assetid: ea97c1d0-04b2-4d42-8d96-23522c04cc41
ms.openlocfilehash: c5b7ba865606e0bc5a5c8238de72824f9061c1b5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97312814"
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

## <a name="remarks"></a>解説

`value_compare` `value_types` マップに含まれる要素全体の間で提供される比較基準は、補助型クラスの構築によって各要素のキーを比較することによって発生します。 メンバー関数の演算子は、 `comp` `key_compare` によって提供される関数オブジェクトに格納されている型のオブジェクトを使用して、 `value_compare` 2 つの要素の並べ替えキーコンポーネントを比較します。

セットとマルチセット (キーの値が要素の値と同一である単純なコンテナー) の場合、`value_compare` は `key_compare` と等価です。マップとマルチマップの場合、型 `pair` の要素の値が要素のキーの値と同一ではないため、その 2 つは等価ではありません。

## <a name="example"></a>例

`value_compare` の宣言方法や使用方法の例については、[value_comp](../standard-library/map-class.md#value_comp) の例をご覧ください。

## <a name="requirements"></a>要件

**ヘッダー:**\<map>

**名前空間:** std

## <a name="see-also"></a>関連項目

[binary_function 構造体](../standard-library/binary-function-struct.md)\
[C++ 標準ライブラリのスレッドセーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[C++ 標準ライブラリリファレンス](../standard-library/cpp-standard-library-reference.md)
