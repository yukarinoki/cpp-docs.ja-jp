---
title: _com_error::HelpContext |Microsoft ドキュメント
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
ms.openlocfilehash: 7123fcf5859ce3fc373b29b4cb3e7b32109b464e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32410825"
---
# <a name="comerrorhelpcontext"></a>_com_error::HelpContext
**Microsoft 固有の仕様**  
  
 呼び出し**ierrorinfo::gethelpcontext**関数。  
  
## <a name="syntax"></a>構文  
  
```  
  
DWORD HelpContext( ) const throw( );  
  
```  
  
## <a name="return-value"></a>戻り値  
 結果を返します**ierrorinfo::gethelpcontext**の**IErrorInfo**内オブジェクトに記録された、`_com_error`オブジェクト。 ない場合は**IErrorInfo**オブジェクトが記録されますが、ゼロが返されます。  
  
## <a name="remarks"></a>コメント  
 呼び出すときの失敗、 **ierrorinfo::gethelpcontext**メソッドは無視されます。  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [_com_error クラス](../cpp/com-error-class.md)