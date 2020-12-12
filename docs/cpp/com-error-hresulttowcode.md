---
description: '詳細については、「_com_error:: HRESULTToWCode」を参照してください。'
title: _com_error::HRESULTToWCode
ms.date: 11/04/2016
f1_keywords:
- _com_error::HRESULTToWCode
helpviewer_keywords:
- HRESULTToWCode method [C++]
ms.assetid: ff3789f5-1047-41a0-b7e3-86dd8f638dba
ms.openlocfilehash: 1bbf62be42d4e34a2ef73493f0449c2ffbaf0646
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97295835"
---
# <a name="_com_errorhresulttowcode"></a>_com_error::HRESULTToWCode

**Microsoft 固有の仕様**

32ビットの HRESULT を16ビットにマップ `wCode` します。

## <a name="syntax"></a>構文

```
static WORD HRESULTToWCode(
   HRESULT hr
) throw( );
```

#### <a name="parameters"></a>パラメーター

*時間*<br/>
16ビットにマップされる32ビットの HRESULT `wCode` 。

## <a name="return-value"></a>戻り値

`wCode`32 ビット HRESULT からマップされた16ビット。

## <a name="remarks"></a>解説

詳細については、「 [_com_error:: WCode](../cpp/com-error-wcode.md) 」を参照してください。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[_com_error::WCode](../cpp/com-error-wcode.md)<br/>
[_com_error::WCodeToHRESULT](../cpp/com-error-wcodetohresult.md)<br/>
[_com_error クラス](../cpp/com-error-class.md)
