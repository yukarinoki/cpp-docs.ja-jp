---
description: '詳細については、「_bstr_t:: operator =」を参照してください。'
title: _bstr_t::operator =
ms.date: 11/04/2016
f1_keywords:
- _bstr_t::operator=
helpviewer_keywords:
- operator = [C++], bstr
- operator= [C++], bstr
ms.assetid: fb31bb1b-ce29-4388-b5fd-8dac830cf18a
ms.openlocfilehash: 78447048a45567df603acf3af0bc51cefbdb187d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97308784"
---
# <a name="_bstr_toperator-"></a>_bstr_t::operator =

**Microsoft 固有の仕様**

既存の `_bstr_t` オブジェクトに新しい値を代入します。

## <a name="syntax"></a>構文

```
_bstr_t& operator=(const _bstr_t& s1) throw ( );
_bstr_t& operator=(const char* s2);
_bstr_t& operator=(const wchar_t* s3);
_bstr_t& operator=(const _variant_t& var);
```

#### <a name="parameters"></a>パラメーター

*s1*<br/>
既存の `_bstr_t` オブジェクトに割り当てられる `_bstr_t` オブジェクト。

*s2*<br/>
既存の `_bstr_t` オブジェクトに割り当てられるマルチバイト文字列。

*s3*<br/>
既存の `_bstr_t` オブジェクトに割り当てられる Unicode 文字列。

*var*<br/>
既存の `_variant_t` オブジェクトに割り当てられる `_bstr_t` オブジェクト。

**Microsoft 固有の仕様はここまで**

## <a name="example"></a>例

**演算子 =** の使用例については、「 [_Bstr_t:: Assign](../cpp/bstr-t-assign.md) 」を参照してください。

## <a name="see-also"></a>関連項目

[_bstr_t クラス](../cpp/bstr-t-class.md)
