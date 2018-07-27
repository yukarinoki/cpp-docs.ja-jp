---
title: IRowsetUpdateImpl クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- IRowsetUpdateImpl
- ATL.IRowsetUpdateImpl
- ATL::IRowsetUpdateImpl
- SetData
- IRowsetUpdateImpl::SetData
- IRowsetUpdateImpl.SetData
- ATL::IRowsetUpdateImpl::SetData
- ATL.IRowsetUpdateImpl.SetData
- ATL.IRowsetUpdateImpl.GetOriginalData
- IRowsetUpdateImpl.GetOriginalData
- GetOriginalData
- ATL::IRowsetUpdateImpl::GetOriginalData
- IRowsetUpdateImpl::GetOriginalData
- IRowsetUpdateImpl::GetPendingRows
- GetPendingRows
- IRowsetUpdateImpl.GetPendingRows
- ATL::IRowsetUpdateImpl::GetPendingRows
- ATL.IRowsetUpdateImpl.GetPendingRows
- ATL.IRowsetUpdateImpl.GetRowStatus
- IRowsetUpdateImpl::GetRowStatus
- IRowsetUpdateImpl.GetRowStatus
- ATL::IRowsetUpdateImpl::GetRowStatus
- GetRowStatus
- ATL.IRowsetUpdateImpl.Undo
- ATL::IRowsetUpdateImpl::Undo
- IRowsetUpdateImpl::Undo
- IRowsetUpdateImpl.Undo
- ATL::IRowsetUpdateImpl::Update
- IRowsetUpdateImpl::Update
- IRowsetUpdateImpl.Update
- ATL.IRowsetUpdateImpl.Update
- IRowsetUpdateImpl::IsUpdateAllowed
- IRowsetUpdateImpl.IsUpdateAllowed
- IsUpdateAllowed
- IRowsetUpdateImpl.m_mapCachedData
- IRowsetUpdateImpl::m_mapCachedData
- m_mapCachedData
dev_langs:
- C++
helpviewer_keywords:
- providers, updatable
- IRowsetUpdateImpl class
- updatable providers, deferred update
- SetData method
- GetOriginalData method
- GetPendingRows method
- GetRowStatus method
- Undo method
- Update method
- IsUpdateAllowed method
- m_mapCachedData
ms.assetid: f85af76b-ab6f-4f8b-8f4a-337c9679d68f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 8d58709e9a2b5bd86102e8323456c6bf9ca72fa1
ms.sourcegitcommit: e5792fcb89b9ba64c401f90f4f26a8e45d4a2359
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2018
ms.locfileid: "39322138"
---
# <a name="irowsetupdateimpl-class"></a>IRowsetUpdateImpl クラス
OLE DB テンプレートの実装、 [IRowsetUpdate](https://msdn.microsoft.com/library/ms714401.aspx)インターフェイス。  
  
## <a name="syntax"></a>構文

```cpp
template <  
   class T,   
   class Storage,   
   class UpdateArray = CAtlArray<Storage>,   
   class RowClass = CSimpleRow,   
   class MapClass = CAtlMap <RowClass::KeyType, RowClass*>   
>  

class IRowsetUpdateImpl : public IRowsetChangeImpl<  
   T,   
   Storage,   
   IRowsetUpdate,   
   RowClass,   
   MapClass>  
```  
  
### <a name="parameters"></a>パラメーター  
 *T*  
 派生したクラス`IRowsetUpdateImpl`します。  
  
 *ストレージ*  
 ユーザー レコード。  
  
 *UpdateArray*  
 行セットを更新するためのキャッシュされたデータを格納する配列。  
  
 *RowClass*  
 記憶域ユニット、`HROW`します。  
  
 *MapClass*  
 プロバイダーによって保持されているすべての行ハンドルのストレージ ユニット。  

## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldb.h  
  
## <a name="members"></a>メンバー  
  
### <a name="interface-methods-used-with-irowsetchange"></a>インターフェイスのメソッド (IRowsetChange で使用)  
  
|||  
|-|-|  
|[SetData](#setdata)|1 つまたは複数の列のデータ値を設定します。|  
  
### <a name="interface-methods-used-with-irowsetupdate"></a>インターフェイスのメソッド (IRowsetUpdate で使用)  
  
|||  
|-|-|  
|[GetOriginalData](#getoriginaldata)|最後に送信または保留中の変更を無視して、データ ソースから取得したデータを取得します。|  
|[GetPendingRows](#getpendingrows)|保留中の変更を含む行の一覧を返します。|  
|[GetRowStatus](#getrowstatus)|指定された行の状態を返します。|  
|[元に戻す](#undo)|最後のフェッチまたは更新以降、行への変更を元に戻します。|  
|[更新](#update)|最後のフェッチまたは更新以降、行に加えられた変更を送信します。|  
  
### <a name="implementation-methods-callback"></a>実装メソッド (コールバック)  
  
|||  
|-|-|  
|[IsUpdateAllowed](#isupdateallowed)|更新プログラムを許可する前に、セキュリティ、整合性、これに確認するために使用します。|  
  
### <a name="data-members"></a>データ メンバー  
  
|||  
|-|-|  
|[m_mapCachedData](#mapcacheddata)|遅延された操作の元のデータが含まれています。|  
  
## <a name="remarks"></a>Remarks  
 最初の読み取りしのドキュメントを理解する必要があります[IRowsetChange](https://msdn.microsoft.com/library/ms715790.aspx)が説明されているすべてのものも適用されるため、ここで、します。 第 6 章を参照する必要がありますも、 *OLE DB プログラマーズ リファレンス*でデータを設定します。  
  
 `IRowsetUpdateImpl` OLE DB 実装`IRowsetUpdate`インターフェイスに加えられた変更の送信を遅延するコンシューマー`IRowsetChange`をデータ ソースし、データ転送する前に変更を元に戻します。  
  
> [!IMPORTANT]
>  プロバイダーを実装する前に、次のドキュメントを確認することを強くお勧めします。  
  
-   [更新可能なプロバイダーの作成](../../data/oledb/creating-an-updatable-provider.md)  
  
-   第 6 章、 *OLE DB プログラマーズ リファレンス*  
  
-   参照してください、`RUpdateRowset`クラス UpdatePV サンプルで使用されます  

## <a name="setdata"></a> Irowsetupdateimpl::setdata
1 つまたは複数の列のデータ値を設定します。  
  
### <a name="syntax"></a>構文  
  
```cpp
      STDMETHOD (SetData )(HROW hRow,  
   HACCESSOR hAccessor,  
   void* pSrcData);  
```  
  
#### <a name="parameters"></a>パラメーター  
 参照してください[irowsetchange::setdata](https://msdn.microsoft.com/library/ms721232.aspx)で、 *OLE DB プログラマーズ リファレンス*します。  
  
### <a name="remarks"></a>Remarks  
 このメソッドは、 [irowsetchangeimpl::setdata](../../data/oledb/irowsetchangeimpl-setdata.md)がメソッドにはでは即時と遅延のいずれかの操作の処理を許可するように元のデータのキャッシュが含まれます。

## <a name="getoriginaldata"></a> Irowsetupdateimpl::getoriginaldata
最後に送信または保留中の変更を無視して、データ ソースから取得したデータを取得します。  
  
### <a name="syntax"></a>構文  
  
```cpp
      STDMETHOD (GetOriginalData )(HROW hRow,  
   HACCESSOR hAccessor,  
   void* pData);  
```  
  
#### <a name="parameters"></a>パラメーター  
 参照してください[IRowsetUpdate::GetOriginalData](https://msdn.microsoft.com/library/ms709947.aspx)で、 *OLE DB プログラマーズ リファレンス*します。   

## <a name="getpendingrows"></a> Irowsetupdateimpl::getpendingrows
保留中の変更を含む行の一覧を返します。  
  
### <a name="syntax"></a>構文  
  
```cpp
      STDMETHOD (GetPendingRows )(HCHAPTER /* hReserved */,  
   DBPENDINGSTATUS dwRowStatus,  
   DBCOUNTITEM* pcPendingRows,  
   HROW** prgPendingRows,  
   DBPENDINGSTATUS** prgPendingStatus);  
```  
  
#### <a name="parameters"></a>パラメーター  
 *hReserved*  
 [in]対応する、 *hChapter*パラメーター [IRowsetUpdate::GetPendingRows](https://msdn.microsoft.com/library/ms719626.aspx)します。  
  
 その他のパラメーターでは、次を参照してください。 [IRowsetUpdate::GetPendingRows](https://msdn.microsoft.com/library/ms719626.aspx)で、 *OLE DB プログラマーズ リファレンス*します。  
  
### <a name="remarks"></a>Remarks  
 詳細については、次を参照してください。 [IRowsetUpdate::GetPendingRows](https://msdn.microsoft.com/library/ms719626.aspx)で、 *OLE DB プログラマーズ リファレンス*します。  

## <a name="getrowstatus"></a> Irowsetupdateimpl::getrowstatus
指定された行の状態を返します。  
  
### <a name="syntax"></a>構文  
  
```cpp
      STDMETHOD (GetRowStatus )(HCHAPTER /* hReserved */,  
   DBCOUNTITEM cRows,  
   const HROW rghRows[],  
   DBPENDINGSTATUS rgPendingStatus[]);  
```  
  
#### <a name="parameters"></a>パラメーター  
 *hReserved*  
 [in]対応する、 *hChapter*パラメーター [IRowsetUpdate::GetRowStatus](https://msdn.microsoft.com/library/ms724377.aspx)します。  
  
 その他のパラメーターでは、次を参照してください。 [IRowsetUpdate::GetRowStatus](https://msdn.microsoft.com/library/ms724377.aspx)で、 *OLE DB プログラマーズ リファレンス*します。  

## <a name="undo"></a> Irowsetupdateimpl::undo
最後のフェッチまたは更新以降、行への変更を元に戻します。  
  
### <a name="syntax"></a>構文  
  
```cpp
      STDMETHOD (Undo )(HCHAPTER /* hReserved */,  
   DBCOUNTITEM cRows,  
   const HROW rghRows[ ],  
   DBCOUNTITEM* pcRowsUndone,  
   HROW** prgRowsUndone,  
   DBROWSTATUS** prgRowStatus);  
```  
  
#### <a name="parameters"></a>パラメーター  
 *hReserved*  
 [in]対応する、 *hChapter*パラメーター [IRowsetUpdate::Undo](https://msdn.microsoft.com/library/ms719655.aspx)します。  
  
 *pcRowsUndone*  
 [out]対応する、 *pcRows*パラメーター [IRowsetUpdate::Undo](https://msdn.microsoft.com/library/ms719655.aspx)します。  
  
 *prgRowsUndone*  
 [in]対応する、 *prgRows*パラメーター [IRowsetUpdate::Undo](https://msdn.microsoft.com/library/ms719655.aspx)します。  
  
 その他のパラメーターでは、次を参照してください。 [IRowsetUpdate::Undo](https://msdn.microsoft.com/library/ms719655.aspx)で、 *OLE DB プログラマーズ リファレンス*します。 

## <a name="update"></a> Irowsetupdateimpl::update
最後のフェッチまたは更新以降、行に加えられた変更を送信します。  
  
### <a name="syntax"></a>構文  
  
```cpp
      STDMETHOD (Update )(HCHAPTER /* hReserved */,  
   DBCOUNTITEM cRows,  
   const HROW rghRows[],  
   DBCOUNTITEM* pcRows,  
   HROW** prgRows,  
   DBROWSTATUS** prgRowStatus);  
```  
  
#### <a name="parameters"></a>パラメーター  
 *hReserved*  
 [in]対応する、 *hChapter*パラメーター [irowsetupdate::update](https://msdn.microsoft.com/library/ms719709.aspx)します。  
  
 その他のパラメーターでは、次を参照してください。 [irowsetupdate::update](https://msdn.microsoft.com/library/ms719709.aspx)で、 *OLE DB プログラマーズ リファレンス*します。  
  
### <a name="remarks"></a>Remarks  
 呼び出して変更を転送する[irowsetchangeimpl::flushdata](../../data/oledb/irowsetchangeimpl-flushdata.md)します。 コンシューマーを呼び出す必要があります[crowset::update](../../data/oledb/crowset-update.md)の変更を有効にします。 設定*prgRowstatus*で説明するよう適切な値に[行の状態](https://msdn.microsoft.com/library/ms722752.aspx)で、 *OLE DB プログラマーズ リファレンス*します。 
  
## <a name="isupdateallowed"></a> Irowsetupdateimpl::isupdateallowed
セキュリティ、更新後に、整合性を確認するには、このメソッドをオーバーライドします。  
  
### <a name="syntax"></a>構文  
  
```cpp
HRESULT IsUpdateAllowed(DBPENDINGSTATUS /* [in] */ /* status */,  
   HROW /* [in] */ /* hRowUpdate */,  
   DBROWSTATUS* /* [out] */ /* pRowStatus */);  
```  
  
#### <a name="parameters"></a>パラメーター  
 *status*  
 [in]保留中の行の操作の状態。  
  
 *hRowUpdate*  
 [in]ユーザーが更新する行のハンドル。  
  
 *pRowStatus*  
 [out]ユーザーに、状態が返されます。  
  
### <a name="remarks"></a>Remarks  
 更新プログラムを許可する場合は、S_OK を返します。E_FAIL を返しますそれ以外の場合。 設定する必要がある更新を許可する場合、`DBROWSTATUS`で[irowsetupdateimpl::update](../../data/oledb/irowsetupdateimpl-update.md)に適切な[状態の行](https://msdn.microsoft.com/library/ms722752.aspx)します。  

## <a name="mapcacheddata"></a> Irowsetupdateimpl::m_mapcacheddata
遅延された操作の元のデータを格納しているマップ。  
  
### <a name="syntax"></a>構文  
  
```cpp
      CAtlMap<   
   HROW hRow,    
   Storage* pData   
>   
m_mapCachedData;  
```  
  
#### <a name="parameters"></a>パラメーター  
 *hRow*  
 データの行へのハンドルします。  
  
 *pData*  
 キャッシュされたデータへのポインター。 型のデータは*ストレージ*(ユーザー レコード クラス)。 参照してください、*ストレージ*のテンプレート引数[IRowsetUpdateImpl クラス](../../data/oledb/irowsetupdateimpl-class.md)します。  

## <a name="see-also"></a>関連項目  
 [OLE DB プロバイダー テンプレート](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB プロバイダー テンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)   
 [更新可能なプロバイダーの作成](../../data/oledb/creating-an-updatable-provider.md)
