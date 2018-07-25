---
title: CTable クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL::CTable
- ATL.CTable
- CTable
- ATL.CTable.Open
- ATL::CTable::Open
- CTable::Open
- CTable.Open
dev_langs:
- C++
helpviewer_keywords:
- CTable class
- Open method
ms.assetid: f13fdaa3-e198-4557-977d-54b0bbc3454d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 7dc1383199b5e8167936d99d487bdfc3eb15bddb
ms.sourcegitcommit: b217daee32d3413cf33753d9b4dc35a0022b1bfa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "39233491"
---
# <a name="ctable-class"></a>CTable クラス
(パラメーターなしのいずれかの) 単純な行セットに直接アクセスするための手段を提供します。  
  
## <a name="syntax"></a>構文

```cpp
template <class TAccessor = CNoAccessor, 
            template <typename T> class TRowset = CRowset>  
class CTable :  
   public CAccessorRowset <TAccessor, TRowset>  
```  
  
### <a name="parameters"></a>パラメーター  
 *TAccessor*  
 アクセサー クラス。  
  
 *TRowset*  
 行セット クラスです。  

## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldbcli.h  
  
## <a name="members"></a>メンバー  
  
### <a name="methods"></a>メソッド  
  
|||  
|-|-|  
|[開く](#open)|テーブルを開きます。|  
  
## <a name="remarks"></a>Remarks  
 参照してください[CCommand](../../data/oledb/ccommand-class.md)については、行セットにアクセスするためのコマンドを実行する方法。  

## <a name="open"></a> Ctable::open
テーブルを開きます。  
  
### <a name="syntax"></a>構文  
  
```cpp
HRESULT Open(const CSession& session,  
   LPCWSTR wszTableName,  
   DBPROPSET* pPropSet = NULL,  
   ULONG ulPropSets = 0) throw ();  


HRESULT Open(const CSession& session,  
   LPCSTR szTableName,  
   DBPROPSET* pPropSet = NULL,  
   ULONG ulPropSets = 0) throw ();  


HRESULT Open(const CSession& session,  
   DBID& dbid,  
   DBPROPSET* pPropSet = NULL,  
   ULONG ulPropSets = 0) throw ();  
```  
  
#### <a name="parameters"></a>パラメーター  
 *セッション*  
 [in]テーブルが開いているセッションです。  
  
 *wszTableName*  
 [in]開くには、テーブルの名前は、Unicode 文字列として渡されます。  
  
 *szTableName*  
 [in]開くには、テーブルの名前は、ANSI 文字列として渡されます。  
  
 *dbid*  
 [in]`DBID`のテーブルを開きます。  
  
 *pPropSet*  
 [in]配列へのポインター [DBPROPSET](https://msdn.microsoft.com/library/ms714367.aspx)プロパティおよび設定する値を含む構造体。 参照してください[プロパティ セットとプロパティ グループ](https://msdn.microsoft.com/library/ms713696.aspx)で、 *OLE DB プログラマーズ リファレンス*Windows SDK にします。 既定値は NULL には、プロパティは指定しません。  
  
 *ulPropSets*  
 [in]数[DBPROPSET](https://msdn.microsoft.com/library/ms714367.aspx)構造体が渡された、 *pPropSet*引数。  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT です。  
  
### <a name="remarks"></a>Remarks  
 詳細については、次を参照してください。 [iopenrowset::openrowset](https://msdn.microsoft.com/library/ms716724.aspx)で、 *OLE DB プログラマーズ リファレンス*します。  
  
## <a name="see-also"></a>関連項目  
 [OLE DB コンシューマー テンプレート](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB コンシューマー テンプレート リファレンス](../../data/oledb/ole-db-consumer-templates-reference.md)   
