---
title: _com_error::WCodeToHRESULT |Microsoft ドキュメント
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
ms.openlocfilehash: 31b9df8305d0eea772979904f63847f6d6c2325a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32413376"
---
# <a name="comerrorwcodetohresult"></a>_com_error::WCodeToHRESULT
**Microsoft 固有の仕様**  
  
 16 ビットをマップ`wCode`32 ビット`HRESULT`です。  
  
## <a name="syntax"></a>構文  
  
```  
  
      static HRESULT WCodeToHRESULT(  
   WORD wCode   
) throw( );  
```  
  
#### <a name="parameters"></a>パラメーター  
 `wCode`  
 32 ビットの `wCode` にマップされる 16 ビットの `HRESULT`。  
  
## <a name="return-value"></a>戻り値  
 16 ビットの `HRESULT` からマップされた 32 ビットの `wCode`。  
  
## <a name="remarks"></a>コメント  
 参照してください、 [WCode](../cpp/com-error-wcode.md)メンバー関数。  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [_com_error::wcode](../cpp/com-error-wcode.md)   
 [_com_error::HRESULTToWCode](../cpp/com-error-hresulttowcode.md)   
 [_com_error クラス](../cpp/com-error-class.md)