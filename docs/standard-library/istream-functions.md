---
title: '&lt;istream&gt; 関数'
ms.date: 11/04/2016
f1_keywords:
- istream/std::swap
- istream/std::ws
ms.assetid: 0301ea0d-4ded-4841-83dd-4253b55b3188
ms.openlocfilehash: b590559b01bb8f5db21fca9f78d220d8bad5c27e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50537645"
---
# <a name="ltistreamgt-functions"></a>&lt;istream&gt; 関数

|||
|-|-|
|[swap](#istream_swap)|[ws](#ws)|

## <a name="istream_swap"></a>  swap

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

*left*<br/>
ストリーム。

*right*<br/>
ストリーム。

## <a name="ws"></a>  ws

ストリーム内の空白をスキップします。

```cpp
template class<Elem, Tr> basic_istream<Elem, Tr>& ws(basic_istream<Elem, Tr>& _Istr);
```

### <a name="parameters"></a>パラメーター

*_Istr*<br/>
ストリーム。

### <a name="return-value"></a>戻り値

ストリーム。

### <a name="remarks"></a>Remarks

マニピュレーターを抽出し、すべての要素を破棄`ch`を[use_facet](../standard-library/basic-filebuf-class.md#open)< **ctype** \< **Elem**>> ( [getloc](../standard-library/ios-base-class.md#getloc))。 **is**( **ctype**\< **Elem**>::**領域**、 **ch**) は true。

この関数は、要素の抽出中にファイルの終わりに達した場合 [setstate](../standard-library/basic-ios-class.md#setstate)( **eofbit**) を呼び出します。 返します *_Istr*します。

### <a name="example"></a>例

`ws` の使用例については [operator>>](../standard-library/istream-operators.md#op_gt_gt) に関する記事をご覧ください。

## <a name="see-also"></a>関連項目

[\<istream>](../standard-library/istream.md)<br/>
