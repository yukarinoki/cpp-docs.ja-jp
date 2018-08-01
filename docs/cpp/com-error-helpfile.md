---
title: _com_error::HelpFile |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_error::HelpFile
dev_langs:
- C++
helpviewer_keywords:
- HelpFile method [C++]
ms.assetid: d2d3a0a1-6b62-4d52-a818-3cfae545a4af
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3afcda41d5dc4ad3cc1fd74ed5449d574946f1e5
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/01/2018
ms.locfileid: "39402043"
---
# <a name="comerrorhelpfile"></a>_com_error::HelpFile
**Microsoft 固有の仕様**  
  
 `IErrorInfo::GetHelpFile` 関数を呼び出します。  
  
## <a name="syntax"></a>構文  
  
```  
_bstr_t HelpFile() const;  
```  
  
## <a name="return-value"></a>戻り値  
 結果を返します`IErrorInfo::GetHelpFile`の`IErrorInfo`内オブジェクトに記録された、`_com_error`オブジェクト。 結果の BSTR は `_bstr_t` オブジェクトにカプセル化されます。 ない場合は`IErrorInfo`が記録されると、空を返します`_bstr_t`します。  
  
## <a name="remarks"></a>Remarks  
 呼び出すときの失敗、`IErrorInfo::GetHelpFile`メソッドは無視されます。  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [_com_error クラス](../cpp/com-error-class.md)