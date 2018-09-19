---
title: _variant_t 関係演算子 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _variant_t::operator==
- _variant_t::operator!=
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 95cb1ac663607f26c4f168c2e98910f5b41963c0
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46040162"
---
# <a name="variantt-relational-operators"></a>_variant_t 関係演算子

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
A`VARIANT`と比較される、`_variant_t`オブジェクト。

*pSrc*<br/>
ポインター、`VARIANT`と比較される、`_variant_t`オブジェクト。

## <a name="return-value"></a>戻り値

返します**true**比較が保持している場合**false**かどうか。

## <a name="remarks"></a>Remarks

比較、`_variant_t`オブジェクトを`VARIANT`等しいかどうかをテストします。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[_variant_t クラス](../cpp/variant-t-class.md)