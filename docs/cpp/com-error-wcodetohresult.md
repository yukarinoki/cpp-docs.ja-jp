---
title: _com_error::WCodeToHRESULT
ms.date: 11/04/2016
f1_keywords:
- _com_error::WCodeToHRESULT
helpviewer_keywords:
- WCodeToHRESULT method [C++]
ms.assetid: 0ec43a4b-ca91-42d5-b270-3fde9c8412ea
ms.openlocfilehash: f2194e0e54a93d3227b84d893f9d3f208d972d09
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80180512"
---
# <a name="_com_errorwcodetohresult"></a>_com_error::WCodeToHRESULT

**Microsoft 固有の仕様**

16ビット*Wcode*を32ビット HRESULT にマップします。

## <a name="syntax"></a>構文

```
static HRESULT WCodeToHRESULT(
   WORD wCode
) throw( );
```

#### <a name="parameters"></a>パラメーター

*wCode*<br/>
32ビットの HRESULT にマップされる16ビットの*Wcode* 。

## <a name="return-value"></a>戻り値

16ビットの*Wcode*からマップされた32ビットの HRESULT。

## <a name="remarks"></a>解説

[Wcode](../cpp/com-error-wcode.md)メンバー関数を参照してください。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>参照

[_com_error::WCode](../cpp/com-error-wcode.md)<br/>
[_com_error::HRESULTToWCode](../cpp/com-error-hresulttowcode.md)<br/>
[_com_error クラス](../cpp/com-error-class.md)
