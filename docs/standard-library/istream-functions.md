---
title: '&lt;istream&gt; 関数'
ms.date: 11/04/2016
f1_keywords:
- istream/std::swap
- istream/std::ws
ms.assetid: 0301ea0d-4ded-4841-83dd-4253b55b3188
ms.openlocfilehash: 6d1fede2726d3d8f5dd678b95fd7a22a301ea95a
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88840974"
---
# <a name="ltistreamgt-functions"></a>&lt;istream&gt; 関数

[フォト](#istream_swap)\
[jax-ws](#ws)

## <a name="swap"></a><a name="istream_swap"></a> フォト

2 つのストリーム オブジェクトの要素を交換します。

```cpp
template <class Elem, class Tr>
void swap(
    basic_istream<Elem, Tr>& left,
    basic_istream<Elem, Tr>& right);

template <class Elem, class Tr>
void swap(
    basic_iostream<Elem, Tr>& left,
    basic_iostream<Elem, Tr>& right);
```

### <a name="parameters"></a>パラメーター

*左側*\
ストリーム。

*そうです*\
ストリーム。

## <a name="ws"></a><a name="ws"></a> jax-ws

ストリーム内の空白をスキップします。

```cpp
template class<Elem, Tr> basic_istream<Elem, Tr>& ws(basic_istream<Elem, Tr>& _Istr);
```

### <a name="parameters"></a>パラメーター

*_Istr*\
ストリーム。

### <a name="return-value"></a>戻り値

ストリームです。

### <a name="remarks"></a>解説

マニピュレーターは `ch` [use_facet](../standard-library/basic-filebuf-class.md#open) <  **ctype** \< **Elem**> > ( [getloc](../standard-library/ios-base-class.md#getloc)) を持つ要素を抽出して破棄します。 **is**( **ctype** \< **Elem**> :: **space**, **ch**) が true です。

この関数は、要素の抽出中にファイルの終わりに達した場合 [setstate](../standard-library/basic-ios-class.md#setstate)( **eofbit**) を呼び出します。 *_Istr*が返されます。

### <a name="example"></a>例

`ws` の使用例については [operator>>](../standard-library/istream-operators.md#op_gt_gt) に関する記事をご覧ください。

## <a name="see-also"></a>関連項目

[\<istream>](../standard-library/istream.md)
