---
title: Cmanualaccessor::addbindentry |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL::CManualAccessor::AddBindEntry
- ATL.CManualAccessor.AddBindEntry
- CManualAccessor::AddBindEntry
- AddBindEntry
- CManualAccessor.AddBindEntry
dev_langs:
- C++
helpviewer_keywords:
- AddBindEntry method
ms.assetid: 8556dda9-dda1-4f67-96bc-6031e6c6a271
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 59793bd61b17fe2ead4948932efa1b583da8e1a8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="cmanualaccessoraddbindentry"></a>CManualAccessor::AddBindEntry
出力列にバインド エントリを追加します。  
  
## <a name="syntax"></a>構文  
  
```
void AddBindEntry(DBORDINAL nOrdinal,  
   DBTYPE wType,  DBLENGTH nColumnSize,  
   void* pData,  
   void* pLength = NULL,  
   void* pStatus = NULL) throw ();  
```  
  
#### <a name="parameters"></a>パラメーター  
 参照してください[DBBINDING](https://msdn.microsoft.com/en-us/library/ms716845.aspx)で、 *OLE DB プログラマーズ リファレンス*です。  
  
 `nOrdinal`  
 [in]列の数です。  
  
 `wType`  
 [in]データ型です。  
  
 `nColumnSize`  
 [in]列のサイズ (バイト単位)。  
  
 `pData`  
 [in]バッファーに格納されている列のデータへのポインター。  
  
 `pLength`  
 [in]必要な場合は、フィールド長へのポインター。  
  
 `pStatus`  
 [in]必要な場合に、列の状態にバインドする変数へのポインター。  
  
## <a name="remarks"></a>コメント  
 この関数を使用するには、まず[CreateAccessor](../../data/oledb/cmanualaccessor-createaccessor.md)です。 指定された列の数より多くのエントリを追加することはできません`CreateAccessor`です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>関連項目  
 [CManualAccessor クラス](../../data/oledb/cmanualaccessor-class.md)   
 [DBViewer サンプル](../../visual-cpp-samples.md)