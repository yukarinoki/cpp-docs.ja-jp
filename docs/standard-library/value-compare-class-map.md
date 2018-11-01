---
title: value_compare クラス (&lt;map&gt;)
ms.date: 11/04/2016
f1_keywords:
- std::value_compare
- std.value_compare
- map/std::value_compare
- value_compare
helpviewer_keywords:
- std::value_compare
ms.assetid: ea97c1d0-04b2-4d42-8d96-23522c04cc41
ms.openlocfilehash: 69b484944c9ce30dc28fceacfb082051da31c053
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50472138"
---
# <a name="valuecompare-class-ltmapgt"></a>value_compare クラス (&lt;map&gt;)

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

## <a name="remarks"></a>Remarks

によって提供される比較の基準`value_compare`間`value_types`マップに含まれる要素全体の補助型クラスの構築によって各要素のキーの間の比較から出されます。 メンバー関数の演算子は、オブジェクトを使用して`comp`型の`key_compare`によって提供される関数オブジェクトに格納されている`value_compare`を 2 つの要素の並べ替えキー構成要素を比較します。

セットとマルチセット (キーの値が要素の値と同一である単純なコンテナー) の場合、`value_compare` は `key_compare` と等価です。マップとマルチマップの場合、型 `pair` の要素の値が要素のキーの値と同一ではないため、その 2 つは等価ではありません。

## <a name="example"></a>例

`value_compare` の宣言方法や使用方法の例については、[value_comp](../standard-library/map-class.md#value_comp)の例を参照してください。

## <a name="requirements"></a>必要条件

**ヘッダー:** \<map>

**名前空間:** std

## <a name="see-also"></a>関連項目

[binary_function 構造体](../standard-library/binary-function-struct.md)<br/>
[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++ 標準ライブラリ リファレンス](../standard-library/cpp-standard-library-reference.md)<br/>
