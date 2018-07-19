---
title: _com_error::HelpContext |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_error::HelpContext
dev_langs:
- C++
helpviewer_keywords:
- HelpContext method [C++]
ms.assetid: 160d6443-9b68-4cf5-a540-50da951a5b2b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e800bd3100fa0199534f3e9bdf6646aa0ffc6860
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2018
ms.locfileid: "37940899"
---
# <a name="comerrorhelpcontext"></a>_com_error::HelpContext
**Microsoft 固有の仕様**  
  
 `IErrorInfo::GetHelpContext` 関数を呼び出します。  
  
## <a name="syntax"></a>構文  
  
```  
  
DWORD HelpContext( ) const throw( );  
  
```  
  
## <a name="return-value"></a>戻り値  
 結果を返します`IErrorInfo::GetHelpContext`の`IErrorInfo`内オブジェクトに記録された、`_com_error`オブジェクト。 ない場合は`IErrorInfo`オブジェクトが記録されますが、0 を返します。  
  
## <a name="remarks"></a>Remarks  
 呼び出すときの失敗、`IErrorInfo::GetHelpContext`メソッドは無視されます。  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [_com_error クラス](../cpp/com-error-class.md)