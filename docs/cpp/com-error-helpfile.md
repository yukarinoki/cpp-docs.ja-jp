---
title: _com_error::HelpFile |Microsoft ドキュメント
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
ms.openlocfilehash: a1f02238d228b5de4302812bacf4f9ad5cf1300c
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32409788"
---
# <a name="comerrorhelpfile"></a>_com_error::HelpFile
**Microsoft 固有の仕様**  
  
 呼び出し**ierrorinfo::gethelpfile**関数。  
  
## <a name="syntax"></a>構文  
  
```  
  
_bstr_t HelpFile() const;  
  
```  
  
## <a name="return-value"></a>戻り値  
 結果を返します**ierrorinfo::gethelpfile**の**IErrorInfo**内オブジェクトに記録された、`_com_error`オブジェクト。 結果の BSTR は `_bstr_t` オブジェクトにカプセル化されます。 ない場合は**IErrorInfo**は空白を返しますが、記録`_bstr_t`です。  
  
## <a name="remarks"></a>コメント  
 呼び出すときの失敗、 **ierrorinfo::gethelpfile**メソッドは無視されます。  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [_com_error クラス](../cpp/com-error-class.md)