---
title: _com_error::HRESULTToWCode |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_error::HRESULTToWCode
dev_langs:
- C++
helpviewer_keywords:
- HRESULTToWCode method [C++]
ms.assetid: ff3789f5-1047-41a0-b7e3-86dd8f638dba
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c39b638451aa8ea89191e323eae5f2c140563990
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46082067"
---
# <a name="comerrorhresulttowcode"></a>_com_error::HRESULTToWCode

**Microsoft 固有の仕様**

16 ビットに 32 ビットの HRESULT をマップ`wCode`します。

## <a name="syntax"></a>構文

```
static WORD HRESULTToWCode(
   HRESULT hr
) throw( );
```

#### <a name="parameters"></a>パラメーター

*hr*<br/>
16 ビットにマップする 32 ビット HRESULT`wCode`します。

## <a name="return-value"></a>戻り値

16 ビット`wCode`32 ビット HRESULT からマップされます。

## <a name="remarks"></a>Remarks

参照してください[_com_error::wcode](../cpp/com-error-wcode.md)詳細についてはします。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[_com_error::WCode](../cpp/com-error-wcode.md)<br/>
[_com_error::WCodeToHRESULT](../cpp/com-error-wcodetohresult.md)<br/>
[_com_error クラス](../cpp/com-error-class.md)