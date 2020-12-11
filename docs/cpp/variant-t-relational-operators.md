---
description: 詳細については、「_variant_t 関係演算子」を参照してください。
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
ms.openlocfilehash: 0a9c339bc67527e258c0d1f69060cde251c8adb9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97161430"
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
`VARIANT`オブジェクトと比較する `_variant_t` 。

*.Psrc*<br/>
`VARIANT`オブジェクトと比較するへのポインター `_variant_t` 。

## <a name="return-value"></a>戻り値

比較が保持される場合はを返します。それ以外の場合はを返し **`true`** **`false`** ます。

## <a name="remarks"></a>解説

オブジェクトと `_variant_t` を比較し `VARIANT` 、等しいかどうかをテストします。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[_variant_t クラス](../cpp/variant-t-class.md)
