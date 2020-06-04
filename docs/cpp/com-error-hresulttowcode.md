---
title: _com_error::HRESULTToWCode
ms.date: 11/04/2016
f1_keywords:
- _com_error::HRESULTToWCode
helpviewer_keywords:
- HRESULTToWCode method [C++]
ms.assetid: ff3789f5-1047-41a0-b7e3-86dd8f638dba
ms.openlocfilehash: 35a497c273f15c9755d3607e7907a3a48dad8dc8
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80180564"
---
# <a name="_com_errorhresulttowcode"></a>_com_error::HRESULTToWCode

**Microsoft 固有の仕様**

32ビットの HRESULT を16ビット `wCode`にマップします。

## <a name="syntax"></a>構文

```
static WORD HRESULTToWCode(
   HRESULT hr
) throw( );
```

#### <a name="parameters"></a>パラメーター

*hr*<br/>
16ビット `wCode`にマップされる32ビットの HRESULT。

## <a name="return-value"></a>戻り値

32ビット HRESULT からマップされた16ビット `wCode`。

## <a name="remarks"></a>解説

詳細については、「 [_com_error:: WCode](../cpp/com-error-wcode.md) 」を参照してください。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>参照

[_com_error::WCode](../cpp/com-error-wcode.md)<br/>
[_com_error::WCodeToHRESULT](../cpp/com-error-wcodetohresult.md)<br/>
[_com_error クラス](../cpp/com-error-class.md)
