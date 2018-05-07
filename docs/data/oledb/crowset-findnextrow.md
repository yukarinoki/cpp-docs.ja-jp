---
title: Crowset::findnextrow |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL.CRowset.FindNextRow
- CRowset<TAccessor>.FindNextRow
- ATL::CRowset::FindNextRow
- CRowset::FindNextRow
- CRowset<TAccessor>::FindNextRow
- CRowset.FindNextRow
- ATL.CRowset<TAccessor>.FindNextRow
- ATL::CRowset<TAccessor>::FindNextRow
- FindNextRow
dev_langs:
- C++
helpviewer_keywords:
- FindNextRow method
ms.assetid: 36484df9-3625-4f15-bf69-db73a8d91c55
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 4afc1db20970102ecddb9031f4f1b7a8f6906cf4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="crowsetfindnextrow"></a>CRowset::FindNextRow
指定されたブックマーク後、次の一致する行を検索します。  
  
## <a name="syntax"></a>構文  
  
```
HRESULT FindNextRow(DBCOMPAREOP op,   
  BYTE* pData,   
   DBTYPE wType,   
   DBLENGTH nLength,   
   BYTE bPrecision,   
   BYTE bScale,   
   BOOL bSkipCurrent = TRUE,   
   CBookmarkBase* pBookmark = NULL) throw();  
```  
  
#### <a name="parameters"></a>パラメーター  
 `op`  
 [in]行の値の比較で使用する操作です。 値については、次を参照してください。 [irowsetfind::findnextrow](https://msdn.microsoft.com/en-us/library/ms723091.aspx)です。  
  
 `pData`  
 [in]照合する値へのポインター。  
  
 `wType`  
 [in]バッファーの値部分のデータ型を示します。 型インジケーターについては、次を参照してください。[データ型](https://msdn.microsoft.com/en-us/library/ms723969.aspx)で、 *OLE DB プログラマーズ リファレンス*Windows SDK にします。  
  
 `nLength`  
 [in]データ値に割り当てるコンシューマー データ構造体の長さ、(バイト単位)。 詳細については、説明を参照してください。 **cbMaxLen**で[DBBINDING 構造体](https://msdn.microsoft.com/en-us/library/ms716845.aspx)で、 *OLE DB プログラマーズ リファレンスです。*  
  
 `bPrecision`  
 [in]データを取得するときに使用される最大有効桁数です。 使用されている場合にのみ`wType`は`DBTYPE_NUMERIC`します。 詳細については、次を参照してください。 [DBTYPE_NUMERIC または DBTYPE_DECIMAL を使用する変換](https://msdn.microsoft.com/en-us/library/ms719714.aspx)で、 *OLE DB プログラマーズ リファレンス*です。  
  
 `bScale`  
 [in]小数点以下桁数がデータを取得するときに使用します。 使用されている場合にのみ`wType`は`DBTYPE_NUMERIC`または**DBTYPE_DECIMAL**です。 詳細については、次を参照してください。 [DBTYPE_NUMERIC または DBTYPE_DECIMAL を使用する変換](https://msdn.microsoft.com/en-us/library/ms719714.aspx)で、 *OLE DB プログラマーズ リファレンス*です。  
  
 *bSkipCurrent*  
 [in]検索を開始する位置を示すブックマークからの行の数。  
  
 `pBookmark`  
 [in]検索を開始する位置をブックマークします。  
  
## <a name="return-value"></a>戻り値  
 標準の `HRESULT`。  
  
## <a name="remarks"></a>コメント  
 このメソッドには、省略可能なインターフェイスが必要とする**IRowsetFind**、する可能性がありますすべてのプロバイダーでサポートされていない以外の場合は、そうでは、返されます**E_NOINTERFACE**です。 設定する必要もあります**DBPROP_IRowsetFind**に`VARIANT_TRUE`呼び出す前に**開く**テーブルまたは行セットを含むコマンドをします。  
  
 コンシューマーでのブックマークの使用方法の詳細については、次を参照してください。[を使用してブックマーク](../../data/oledb/using-bookmarks.md)です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>関連項目  
 [CRowset クラス](../../data/oledb/crowset-class.md)   
 [DBBINDING 構造体](https://msdn.microsoft.com/en-us/library/ms716845.aspx)