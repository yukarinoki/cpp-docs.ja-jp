---
title: _variant_t 関係演算子
ms.date: 11/04/2016
f1_keywords:
- _variant_t::operator==
- _variant_t::operator!=
helpviewer_keywords:
- '!= operator'
- relational operators [C++], _variant_t class
- operator!= [C++], variant
- operator!= [C++], relational operators
- operator != [C++], variant
- operator == [C++], variant
- operator== [C++], variant
- operator != [C++], relational operators
- == operator [C++], with specific Visual C++ objects
ms.assetid: 141bacb8-41a2-44dd-b3c0-4ad1f884f4ea
ms.openlocfilehash: e0d7ea1a0bcaf8329cff0cdfb0c01154f3c5a73b
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80187571"
---
# <a name="_variant_t-relational-operators"></a>_variant_t 関係演算子

**Microsoft 固有の仕様**

2 つの `_variant_t` オブジェクトを比較して、等しいかどうかを確認します。

## <a name="syntax"></a>構文

```
bool operator==(
   const VARIANT& varSrc) const;
bool operator==(
   const VARIANT* pSrc) const;
bool operator!=(
   const VARIANT& varSrc) const;
bool operator!=(
   const VARIANT* pSrc) const;
```

#### <a name="parameters"></a>パラメーター

*varSrc*<br/>
`_variant_t` オブジェクトと比較する `VARIANT`。

*.Psrc*<br/>
`_variant_t` オブジェクトと比較する `VARIANT` へのポインター。

## <a name="return-value"></a>戻り値

比較が保持される場合は**true** 、それ以外の場合は**false**を返します。

## <a name="remarks"></a>解説

`_variant_t` オブジェクトと `VARIANT`を比較し、等しいかどうかをテストします。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>参照

[_variant_t クラス](../cpp/variant-t-class.md)
