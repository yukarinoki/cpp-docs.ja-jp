---
title: _com_error::Description |Microsoft ドキュメント
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
ms.openlocfilehash: 7df1fb3a8ca600b888e5d6f2c51fc44fda17dd27
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32414260"
---
# <a name="comerrordescription"></a>_com_error::Description
**Microsoft 固有の仕様**  
  
 呼び出し**ierrorinfo::getdescription**関数。  
  
## <a name="syntax"></a>構文  
  
```  
  
_bstr_t Description( ) const;  
  
```  
  
## <a name="return-value"></a>戻り値  
 結果を返します**ierrorinfo::getdescription**の**IErrorInfo**内オブジェクトに記録された、`_com_error`オブジェクト。 結果の `BSTR` は `_bstr_t` オブジェクトにカプセル化されます。 ない場合は**IErrorInfo**は空白を返しますが、記録`_bstr_t`です。  
  
## <a name="remarks"></a>コメント  
 呼び出し、 **ierrorinfo::getdescription**関数と取得**IErrorInfo**内に記録された、`_com_error`オブジェクト。 呼び出すときの失敗、 **ierrorinfo::getdescription**メソッドは無視されます。  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [_com_error クラス](../cpp/com-error-class.md)