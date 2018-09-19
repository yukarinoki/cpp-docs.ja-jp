---
title: _com_error::WCodeToHRESULT |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_error::WCodeToHRESULT
dev_langs:
- C++
helpviewer_keywords:
- WCodeToHRESULT method [C++]
ms.assetid: 0ec43a4b-ca91-42d5-b270-3fde9c8412ea
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5b6712734cd7283558ad5776444586f8c0b3fa6e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46077569"
---
# <a name="comerrorwcodetohresult"></a>_com_error::WCodeToHRESULT

**Microsoft 固有の仕様**

16 ビット マップ*wCode* HRESULT の 32 ビットにします。

## <a name="syntax"></a>構文

```
static HRESULT WCodeToHRESULT(
   WORD wCode
) throw( );
```

#### <a name="parameters"></a>パラメーター

*WCode*<br/>
16 ビット*wCode* HRESULT の 32 ビットにマップします。

## <a name="return-value"></a>戻り値

16 ビットからマップされた 32 ビット HRESULT *wCode*します。

## <a name="remarks"></a>Remarks

参照してください、 [WCode](../cpp/com-error-wcode.md)メンバー関数。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[_com_error::WCode](../cpp/com-error-wcode.md)<br/>
[_com_error::HRESULTToWCode](../cpp/com-error-hresulttowcode.md)<br/>
[_com_error クラス](../cpp/com-error-class.md)