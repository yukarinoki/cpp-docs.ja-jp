---
title: Cdynamicparameteraccessor::setparamstring |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL.CDynamicParameterAccessor.SetParamString
- ATL::CDynamicParameterAccessor::SetParamString
- SetParamString
- CDynamicParameterAccessor::SetParamString
- CDynamicParameterAccessor.SetParamString
dev_langs:
- C++
helpviewer_keywords:
- SetParamString method
ms.assetid: 77a38d23-7e33-4e5a-bda6-c12c4c3fe2e4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 0b8c435fea707317c1f8de798796f49cb8b048ae
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33095730"
---
# <a name="cdynamicparameteraccessorsetparamstring"></a>CDynamicParameterAccessor::SetParamString
バッファーに格納され、指定されたパラメーターの文字列データを設定します。  
  
## <a name="syntax"></a>構文  
  
```
bool SetParamString(DBORDINAL nParam,   
   constCHAR* pString,   
   DBSTATUS status = DBSTATUS_S_OK) throw();bool SetParamString(DBORDINAL nParam,   
   constWCHAR* pString,   
   DBSTATUS status = DBSTATUS_S_OK) throw();  
```  
  
#### <a name="parameters"></a>パラメーター  
 `nParam`  
 [in]パラメーターの数 (1 からのオフセット)。 に対するパラメーター 0 は、戻り値に予約されています。 パラメーター数は、SQL またはストアド プロシージャの呼び出しでその順序に基づいて、パラメーターのインデックスです。 参照してください[SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md)例についてはします。  
  
 `pString`  
 [in]ANSI へのポインター (**CHAR**) または Unicode (**WCHAR**) 文字列型の指定されたパラメーターのデータ。 参照してください`DBSTATUS`oledb.h でします。  
  
 *status*  
 [in]`DBSTATUS`指定されたパラメーターの状態。 詳細について`DBSTATUS`値を参照してください[ステータス](https://msdn.microsoft.com/en-us/library/ms722617.aspx)で、 *OLE DB プログラマーズ リファレンス*、または検索`DBSTATUS`oledb.h でします。  
  
## <a name="remarks"></a>コメント  
 返します**true**成功した場合または**false**エラー発生時にします。  
  
 `SetParamString` 指定された最大サイズを超える文字列を設定しようとする場合は失敗`pString`です。  
  
 使用して`SetParamString`をバッファーに文字列パラメーターのデータを設定します。 使用して[SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md)をバッファーに文字列以外のパラメーターのデータを設定します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>関連項目  
 [CDynamicParameterAccessor クラス](../../data/oledb/cdynamicparameteraccessor-class.md)