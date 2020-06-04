---
title: '&lt;istream&gt; 関数'
ms.date: 11/04/2016
f1_keywords:
- istream/std::swap
- istream/std::ws
ms.assetid: 0301ea0d-4ded-4841-83dd-4253b55b3188
ms.openlocfilehash: 3d647c7b05a3868ec0359410cc0e703306b874ba
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81363078"
---
# <a name="ltistreamgt-functions"></a>&lt;istream&gt; 関数

|||
|-|-|
|[スワップ](#istream_swap)|[Ws](#ws)|

## <a name="swap"></a><a name="istream_swap"></a>スワップ

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

*左*\
ストリーム。

*そうです*\
ストリーム。

## <a name="ws"></a><a name="ws"></a>Ws

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

マニピュ`ch`レータは **、ctype** **ctype** \< Elem> >( [getloc](../standard-library/ios-base-class.md#getloc)) [use_facet](../standard-library/basic-filebuf-class.md#open)< 要素を抽出して破棄します。 **は** **(ctype** \< **Elem**>::**スペース** **、ch**) が真です。

この関数は、要素の抽出中にファイルの終わりに達した場合 [setstate](../standard-library/basic-ios-class.md#setstate)( **eofbit**) を呼び出します。 _Istr返*します*。

### <a name="example"></a>例

`ws` の使用例については [operator>>](../standard-library/istream-operators.md#op_gt_gt) に関する記事をご覧ください。

## <a name="see-also"></a>関連項目

[\<i流>](../standard-library/istream.md)
