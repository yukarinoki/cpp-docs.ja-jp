---
title: _com_error::GUID |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_error::GUID
dev_langs:
- C++
helpviewer_keywords:
- GUID method [C++]
ms.assetid: e84c2c23-d02e-48f8-b776-9bd6937296d2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ee1952e50251cfac7563357c7626ab8603589e4d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32409689"
---
# <a name="comerrorguid"></a>_com_error::GUID
**Microsoft 固有の仕様**  
  
 呼び出し**ierrorinfo::getguid**関数。  
  
## <a name="syntax"></a>構文  
  
```  
  
GUID GUID( ) const throw( );  
  
```  
  
## <a name="return-value"></a>戻り値  
 結果を返します**ierrorinfo::getguid**の**IErrorInfo**内オブジェクトに記録された、`_com_error`オブジェクト。 ない場合は**IErrorInfo**返しますオブジェクトが記録されて、`GUID_NULL`です。  
  
## <a name="remarks"></a>コメント  
 呼び出すときの失敗、 **ierrorinfo::getguid**メソッドは無視されます。  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [_com_error クラス](../cpp/com-error-class.md)