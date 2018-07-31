---
title: IRowsetChangeImpl クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL::IRowsetChangeImpl
- IRowsetChangeImpl
- ATL.IRowsetChangeImpl
- ATL.IRowsetChangeImpl.DeleteRows
- ATL::IRowsetChangeImpl::DeleteRows
- IRowsetChangeImpl.DeleteRows
- DeleteRows
- IRowsetChangeImpl::DeleteRows
- ATL.IRowsetChangeImpl.InsertRow
- InsertRow
- IRowsetChangeImpl.InsertRow
- ATL::IRowsetChangeImpl::InsertRow
- IRowsetChangeImpl::InsertRow
- SetData
- IRowsetChangeImpl::SetData
- ATL.IRowsetChangeImpl.SetData
- IRowsetChangeImpl.SetData
- ATL::IRowsetChangeImpl::SetData
- IRowsetChangeImpl::FlushData
- IRowsetChangeImpl.FlushData
- FlushData
dev_langs:
- C++
helpviewer_keywords:
- providers, updatable
- updatable providers, immediate update
- IRowsetChangeImpl class
- DeleteRows method
- InsertRow method
- SetData method
- FlushData method
ms.assetid: 1e9fee15-ed9e-4387-af8f-215569beca6c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 0f77f9a33b0cf51ea54d16f89e86ea914640f627
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2018
ms.locfileid: "39339599"
---
# <a name="irowsetchangeimpl-class"></a>IRowsetChangeImpl クラス
OLE DB テンプレートの実装、 [IRowsetChange](https://msdn.microsoft.com/library/ms715790.aspx) OLE DB 仕様のインターフェイス。  
  
## <a name="syntax"></a>構文

```cpp
template <  
   class T,   
   class Storage,   
   class BaseInterface = IRowsetChange,   
   class RowClass = CSimpleRow,   
   class MapClass = CAtlMap <RowClass::KeyType, RowClass*>>  
class ATL_NO_VTABLE IRowsetChangeImpl : public BaseInterface  
```  
  
### <a name="parameters"></a>パラメーター  
 *T*  
 派生したクラス`IRowsetChangeImpl`します。  
  
 *ストレージ*  
 ユーザー レコード。  
  
 *BaseInterface*  
 基底クラス、インターフェイスでなど`IRowsetChange`します。  
  
 *RowClass*  
 行ハンドルの記憶域ユニット。  
  
 *MapClass*  
 プロバイダーによって保持されているすべての行ハンドルのストレージ ユニット。  

## <a name="requirements"></a>要件  
 **ヘッダー:** atldb.h  
  
## <a name="members"></a>メンバー  
  
### <a name="interface-methods-used-with-irowsetchange"></a>インターフェイスのメソッド (IRowsetChange で使用)  
  
|||  
|-|-|  
|[DeleteRows](#deleterows)|行セットから行を削除します。|  
|[InsertRow](#insertrow)|行セットには、行を挿入します。|  
|[SetData](#setdata)|1 つまたは複数の列のデータ値を設定します。|  
  
### <a name="implementation-method-callback"></a>実装メソッド (コールバック)  
  
|||  
|-|-|  
|[FlushData](#flushdata)|プロバイダーによって、そのストアにデータをコミットする上書きします。|  
  
## <a name="remarks"></a>Remarks  
 このインターフェイスは、データ ストアへの即時の書き込み操作を担当します。 「直近」の意味がエンドユーザー (コンシューマーを使用するユーザー) がすべての変更を行うと、それらの変更はすぐに送信されること、データは格納 (および、元に戻すことはできません)。  
  
 `IRowsetChangeImpl` OLE DB 実装`IRowsetChange`インターフェイスで、行を削除して、新しい行を挿入する既存の行の列の値の更新が可能です。  
  
 OLE DB テンプレートの実装には、すべての基本メソッドがサポートしています (`SetData`、 `InsertRow`、および`DeleteRows`)。  
  
> [!IMPORTANT]
>  プロバイダーを実装する前に、次のドキュメントを確認することを強くお勧めします。  
  
-   [更新可能なプロバイダーの作成](../../data/oledb/creating-an-updatable-provider.md)  
  
-   第 6 章、 *OLE DB プログラマーズ リファレンス*  
  
-   参照してください、`RUpdateRowset`クラス UpdatePV サンプルで使用されます  
  
## <a name="deleterows"></a> Irowsetchangeimpl::deleterows
行セットから行を削除します。  
  
### <a name="syntax"></a>構文  
  
```cpp
STDMETHOD (DeleteRows )(HCHAPTER /* hReserved */,  
   DBCOUNTITEM cRows,  
   const HROW rghRows[],  
   DBROWSTATUS rgRowStatus[]);  
```  
  
#### <a name="parameters"></a>パラメーター  
 参照してください[irowsetchange::deleterows](https://msdn.microsoft.com/library/ms724362.aspx)で、 *OLE DB プログラマーズ リファレンス*します。 

## <a name="insertrow"></a> Irowsetchangeimpl::insertrow
作成し、行セット内の新しい行を初期化します。  
  
### <a name="syntax"></a>構文  
  
```cpp
STDMETHOD (InsertRow )(HCHAPTER /* hReserved */,  
   HACCESSOR hAccessor,  
   void* pData,  
   HROW* phRow);  
```  
  
#### <a name="parameters"></a>パラメーター  
 参照してください[irowsetchange::insertrow](https://msdn.microsoft.com/library/ms716921.aspx)で、 *OLE DB プログラマーズ リファレンス*します。 

## <a name="setdata"></a> Irowsetchangeimpl::setdata
1 つまたは複数の列のデータ値を設定します。  
  
### <a name="syntax"></a>構文  
  
```cpp
STDMETHOD (SetData )(HROW hRow,  
   HACCESSOR hAccessor,  
   void* pSrcData);  
```  
  
#### <a name="parameters"></a>パラメーター  
 参照してください[irowsetchange::setdata](https://msdn.microsoft.com/library/ms721232.aspx)で、 *OLE DB プログラマーズ リファレンス*します。 

## <a name="flushdata"></a> Irowsetchangeimpl::flushdata
プロバイダーによって、そのストアにデータをコミットする上書きします。  
  
### <a name="syntax"></a>構文  
  
```cpp
HRESULT FlushData(HROW hRowToFlush,  
   HACCESSOR hAccessorToFlush);  
```  
  
#### <a name="parameters"></a>パラメーター  
 *hRowToFlush*  
 [in]データの行へのハンドルします。 この行の型から判断されます、 *RowClass*のテンプレート引数、`IRowsetImpl`クラス (`CSimpleRow`既定)。  
  
 *hAccessorToFlush*  
 [in]バインド情報とで型情報が含まれた、アクセサーへのハンドル、 `PROVIDER_MAP` (を参照してください[IAccessorImpl](../../data/oledb/iaccessorimpl-class.md))。  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT です。  
  
## <a name="see-also"></a>関連項目  
 [OLE DB プロバイダー テンプレート](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB プロバイダー テンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)