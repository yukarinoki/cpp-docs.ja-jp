---
title: _com_error::Description |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_error::Description
dev_langs:
- C++
helpviewer_keywords:
- Description method [C++]
ms.assetid: 88191e24-4ee8-44a6-8c4c-3758e22e0548
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4be038bff05ce7a37b09ec3b3c61572635747864
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2018
ms.locfileid: "37939898"
---
# <a name="comerrordescription"></a>_com_error::Description
**Microsoft 固有の仕様**  
  
 `IErrorInfo::GetDescription` 関数を呼び出します。  
  
## <a name="syntax"></a>構文  
  
```  
  
_bstr_t Description( ) const;  
  
```  
  
## <a name="return-value"></a>戻り値  
 結果を返します`IErrorInfo::GetDescription`の`IErrorInfo`内オブジェクトに記録された、`_com_error`オブジェクト。 結果の `BSTR` は `_bstr_t` オブジェクトにカプセル化されます。 ない場合は`IErrorInfo`が記録されると、空を返します`_bstr_t`します。  
  
## <a name="remarks"></a>Remarks  
 呼び出し、`IErrorInfo::GetDescription`関数を取得します`IErrorInfo`内に記録された、`_com_error`オブジェクト。 呼び出すときの失敗、`IErrorInfo::GetDescription`メソッドは無視されます。  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [_com_error クラス](../cpp/com-error-class.md)