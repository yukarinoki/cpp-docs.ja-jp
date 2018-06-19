---
title: Cdynamicparameteraccessor::getparamlength |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL::CDynamicParameterAccessor::GetParamLength
- ATL.CDynamicParameterAccessor.GetParamLength
- CDynamicParameterAccessor.GetParamLength
- CDynamicParameterAccessor::GetParamLength
- GetParamLength
dev_langs:
- C++
helpviewer_keywords:
- GetParamLength method
ms.assetid: 04d76931-911a-4915-9c2c-ad585a9f3854
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: ee19c694fa267630419857c3a81bd9e61d044939
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33098317"
---
# <a name="cdynamicparameteraccessorgetparamlength"></a>CDynamicParameterAccessor::GetParamLength
バッファーに格納され、指定されたパラメーターの長さを取得します。  
  
## <a name="syntax"></a>構文  
  
```
bool GetParamLength(DBORDINAL nParam,  
  DBLENGTH* pLength);  

DBLENGTH* GetParamLength(DBORDINAL nParam) const throw();  
```  
  
#### <a name="parameters"></a>パラメーター  
 `nParam`  
 [in]パラメーターの数 (1 からのオフセット)。 に対するパラメーター 0 は、戻り値に予約されています。 パラメーター数は、SQL またはストアド プロシージャの呼び出しでその順序に基づいて、パラメーターのインデックスです。 参照してください[SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md)例についてはします。  
  
 `pLength`  
 [out]指定されたパラメーターの長さ (バイト単位) を含む変数へのポインター。  
  
## <a name="remarks"></a>コメント  
 最初の形式**true**成功した場合または**false**エラー発生時にします。 2 つ目は、パラメーターの長さを表すメモリへのポインターをオーバーライドします。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>関連項目  
 [CDynamicParameterAccessor クラス](../../data/oledb/cdynamicparameteraccessor-class.md)