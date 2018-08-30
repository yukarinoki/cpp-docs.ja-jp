---
title: IRowsetNotifyCP クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- IRowsetNotifyCP
- Fire_OnFieldChange
- ATL::IRowsetNotifyCP::Fire_OnFieldChange
- ATL.IRowsetNotifyCP.Fire_OnFieldChange
- IRowsetNotifyCP.Fire_OnFieldChange
- IRowsetNotifyCP::Fire_OnFieldChange
- IRowsetNotifyCP.Fire_OnRowChange
- ATL.IRowsetNotifyCP.Fire_OnRowChange
- Fire_OnRowChange
- ATL::IRowsetNotifyCP::Fire_OnRowChange
- IRowsetNotifyCP::Fire_OnRowChange
- Fire_OnRowsetChange
- IRowsetNotifyCP::Fire_OnRowsetChange
- IRowsetNotifyCP.Fire_OnRowsetChange
- ATL::IRowsetNotifyCP::Fire_OnRowsetChange
- ATL.IRowsetNotifyCP.Fire_OnRowsetChange
dev_langs:
- C++
helpviewer_keywords:
- IRowsetNotifyCP class
- Fire_OnFieldChange method
- Fire_OnRowChange method
- Fire_OnRowsetChange method
ms.assetid: ccef402b-94a0-4c2e-9a13-7e854ef82390
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: e9826dd9249d01b78466a18df866afd818df78c8
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43212345"
---
# <a name="irowsetnotifycp-class"></a>IRowsetNotifyCP クラス
プロバイダーは、サイト接続ポイントのインターフェイスを実装する[IRowsetNotify](/previous-versions/windows/desktop/ms712959\(v=vs.85\))します。  
  
## <a name="syntax"></a>構文

```cpp
template <class T, class ReentrantEventSync = CComSharedMutex>  
class IRowsetNotifyCP :   
   public IConnectionPointImpl<  
      T,   
      piid = &__uuidof(IRowsetNotify),   
      CComDynamicUnkArray DynamicUnkArray>,  
   public ReentrantEventSync  
```  
  
### <a name="parameters"></a>パラメーター  
 *T*  
 派生したクラス`IRowsetNotifyCP`します。  
  
 *ReentrantEventSync*  
 再入をサポートする mutex クラス (既定値は`CComSharedMutex`)。 ミュー テックスは、リソースへの 1 つのスレッド相互に排他的アクセスを許可する同期オブジェクトです。  
  
 *piid*  
 インターフェイス ID のポインター (`IID*`) の`IRowsetNotify`接続ポイントのインターフェイス。 既定値は `&__uuidof(IRowsetNotify)` です。  
  
 *DynamicUnkArray*  
 型の配列[CComDynamicUnkArray](../../atl/reference/ccomdynamicunkarray-class.md)、これは、動的に割り当てられた配列の`IUnknown`シンク インターフェイスのクライアントへのポインター。 

## <a name="requirements"></a>要件  
 **ヘッダー:** atldb.h   
  
## <a name="members"></a>メンバー  
  
### <a name="methods"></a>メソッド  
  
|||  
|-|-|  
|[Fire_OnFieldChange](#onfieldchange)|列の値に変更をコンシューマーに通知します。|  
|[Fire_OnRowChange](#onrowchange)|行に影響する変更をコンシューマーに通知します。|  
|[Fire_OnRowsetChange](#onrowsetchange)|行セット全体に影響する変更をコンシューマーに通知します。|  
  
## <a name="remarks"></a>Remarks  
 `IRowsetNotifyCP` 実装は、接続ポイント上のリスナーに通知する関数をブロードキャスト`IID_IRowsetNotify`の行セットの内容の変更。  
  
 実装し、登録する必要がありますので注意`IRowsetNotify`(別名「シンク」) を使用して、コンシューマーで[IRowsetNotifyImpl](../../data/oledb/irowsetnotifyimpl-class.md)コンシューマーが通知を処理できるようにします。 参照してください[通知の受信](../../data/oledb/receiving-notifications.md)コンシューマーのコネクション ポイントのインターフェイスを実装する方法。  
  
 通知の実装の詳細については、「通知のサポート」を参照してください[更新可能なプロバイダーを作成する](../../data/oledb/creating-an-updatable-provider.md)します。  

## <a name="onfieldchange"></a> Irowsetnotifycp::fire_onfieldchange
ブロードキャスト、 [OnFieldChange](/previous-versions/windows/desktop/ms715961\(v=vs.85\))列の値に対する変更をコンシューマーに通知するイベントです。  
  
### <a name="syntax"></a>構文  
  
```cpp
HRESULT Fire_OnFieldChange(IRowset* pRowset,  
   HROW hRow,  
   DBORDINAL cColumns,  
   DBORDINAL* rgColumns,  
   DBREASON eReason,  
   DBEVENTPHASE ePhase,  
   BOOL fCantDeny);  
```  
  
#### <a name="parameters"></a>パラメーター  
 参照してください[は、](/previous-versions/windows/desktop/ms715961\(v=vs.85\))で、 *OLE DB プログラマーズ リファレンス*します。 

## <a name="onrowchange"></a> Irowsetnotifycp::fire_onrowchange
ブロードキャスト、 [OnRowChange](/previous-versions/windows/desktop/ms722694\(v=vs.85\))イベント接続ポイント上のすべてのリスナーを`IID_IRowsetNotify`行に影響する変更のコンシューマーに通知します。  
  
### <a name="syntax"></a>構文  
  
```cpp
HRESULT Fire_OnRowChange(IRowset* pRowset,  
   DBCOUNTITEM cRows,  
   const HROW rghRows[],  
   DBREASON eReason,  
   DBEVENTPHASE ePhase,  
   BOOL fCantDeny);  
```  
  
#### <a name="parameters"></a>パラメーター  
 参照してください[は、](/previous-versions/windows/desktop/ms722694\(v=vs.85\))で、 *OLE DB プログラマーズ リファレンス*します。  

## <a name="onrowsetchange"></a> Irowsetnotifycp::fire_onrowsetchange
ブロードキャスト、 [OnRowsetChange](/previous-versions/windows/desktop/ms722669\(v=vs.85\))イベント接続ポイント上のすべてのリスナーを`IID_IRowsetNotify`行セット全体に影響する変更のコンシューマーに通知します。  
  
### <a name="syntax"></a>構文  
  
```cpp
HRESULT Fire_OnRowsetChange(IRowset* pRowset,  
   DBREASON eReason,  
   DBEVENTPHASE ePhase,  
   BOOL fCantDeny);  
```  
  
#### <a name="parameters"></a>パラメーター  
 参照してください[は、](/previous-versions/windows/desktop/ms722669\(v=vs.85\))で、 *OLE DB プログラマーズ リファレンス*します。
  
## <a name="see-also"></a>関連項目  
 [OLE DB プロバイダー テンプレート](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB プロバイダー テンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)   
 [通知 (COM)](https://msdn.microsoft.com/library/windows/desktop/ms678433)   
 [BEGIN_CONNECTION_POINT_MAP](../../atl/reference/connection-point-macros.md#begin_connection_point_map)   
 [END_CONNECTION_POINT_MAP](../../atl/reference/connection-point-macros.md#end_connection_point_map)   
 [CONNECTION_POINT_ENTRY](../../atl/reference/connection-point-macros.md#connection_point_entry)   
 [更新可能なプロバイダーの作成](../../data/oledb/creating-an-updatable-provider.md)