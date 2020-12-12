---
description: '詳細情報: IRowsetNotifyCP クラス'
title: IRowsetNotifyCP クラス
ms.date: 11/04/2016
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
helpviewer_keywords:
- IRowsetNotifyCP class
- Fire_OnFieldChange method
- Fire_OnRowChange method
- Fire_OnRowsetChange method
ms.assetid: ccef402b-94a0-4c2e-9a13-7e854ef82390
ms.openlocfilehash: 70e759ed19c366f7e85511170439c24f319c5cd3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97317273"
---
# <a name="irowsetnotifycp-class"></a>IRowsetNotifyCP クラス

接続ポイントインターフェイス [IRowsetNotify](/previous-versions/windows/desktop/ms712959(v=vs.85))のプロバイダーサイトを実装します。

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

*T*<br/>
から派生したクラス `IRowsetNotifyCP` 。

*ReentrantEventSync*<br/>
再入をサポートするミューテックスクラス (既定値は `CComSharedMutex` )。 ミューテックスは、1つのスレッドがリソースに相互に排他的にアクセスできるようにする同期オブジェクトです。

*piid*<br/>
`IID*`コネクションポイントインターフェイスのインターフェイス ID ポインター () `IRowsetNotify` 。 既定値は `&__uuidof(IRowsetNotify)` です。

*DynamicUnkArray*<br/>
[CComDynamicUnkArray](../../atl/reference/ccomdynamicunkarray-class.md)型の配列 `IUnknown` 。クライアントシンクインターフェイスへのポインターの動的に割り当てられた配列です。

## <a name="requirements"></a>要件

**ヘッダー:** atldb.h

## <a name="members"></a>メンバー

### <a name="methods"></a>メソッド

| 名前 | 説明 |
|-|-|
|[Fire_OnFieldChange](#onfieldchange)|コンシューマーに、列の値の変更を通知します。|
|[Fire_OnRowChange](#onrowchange)|行に影響する変更をコンシューマーに通知します。|
|[Fire_OnRowsetChange](#onrowsetchange)|行セット全体に影響を与える変更をコンシューマーに通知します。|

## <a name="remarks"></a>解説

`IRowsetNotifyCP` は、 `IID_IRowsetNotify` 行セットの内容に対する変更のコネクションポイントをリスナーに通知する broadcast 関数を実装します。

`IRowsetNotify`コンシューマーが通知を処理できるように、 [IRowsetNotifyImpl](../../data/oledb/irowsetnotifyimpl-class.md)を使用してコンシューマー ("シンク" とも呼ばれます) にも実装し、登録する必要があることに注意してください。 「コンシューマーへのコネクションポイントインターフェイスの実装に関する [通知の受信](../../data/oledb/receiving-notifications.md) 」を参照してください。

通知の実装の詳細については、「 [更新可能なプロバイダーの作成](../../data/oledb/creating-an-updatable-provider.md)」の「サポート通知」を参照してください。

## <a name="irowsetnotifycpfire_onfieldchange"></a><a name="onfieldchange"></a> IRowsetNotifyCP:: Fire_OnFieldChange

列の値の変更をコンシューマーに通知するために、 [Onfieldchange](/previous-versions/windows/desktop/ms715961(v=vs.85)) イベントをブロードキャストします。

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

*OLE DB プログラマーリファレンス* の「 [IRowsetNotify:: onfieldchange](/previous-versions/windows/desktop/ms715961(v=vs.85)) 」を参照してください。

## <a name="irowsetnotifycpfire_onrowchange"></a><a name="onrowchange"></a> IRowsetNotifyCP:: Fire_OnRowChange

接続ポイントのすべてのリスナーに [OnRowChange](/previous-versions/windows/desktop/ms722694(v=vs.85)) イベントをブロードキャストして、 `IID_IRowsetNotify` 行に影響する変更をコンシューマーに通知します。

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

*OLE DB プログラマーリファレンス* の「 [IRowsetNotify:: OnRowChange](/previous-versions/windows/desktop/ms722694(v=vs.85)) 」を参照してください。

## <a name="irowsetnotifycpfire_onrowsetchange"></a><a name="onrowsetchange"></a> IRowsetNotifyCP:: Fire_OnRowsetChange

[](/previous-versions/windows/desktop/ms722669(v=vs.85)) `IID_IRowsetNotify` 行セット全体に影響を与える変更をコンシューマーに通知するために、接続ポイントのすべてのリスナーに OnRowsetChange イベントをブロードキャストします。

### <a name="syntax"></a>構文

```cpp
HRESULT Fire_OnRowsetChange(IRowset* pRowset,
   DBREASON eReason,
   DBEVENTPHASE ePhase,
   BOOL fCantDeny);
```

#### <a name="parameters"></a>パラメーター

*OLE DB プログラマーリファレンス* の「 [IRowsetNotify:: OnRowsetChange](/previous-versions/windows/desktop/ms722669(v=vs.85)) 」を参照してください。

## <a name="see-also"></a>関連項目

[OLE DB プロバイダー テンプレートに関するページ](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB プロバイダーテンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)<br/>
[通知 (COM)](/windows/win32/com/notifications)<br/>
[BEGIN_CONNECTION_POINT_MAP](../../atl/reference/connection-point-macros.md#begin_connection_point_map)<br/>
[END_CONNECTION_POINT_MAP](../../atl/reference/connection-point-macros.md#end_connection_point_map)<br/>
[CONNECTION_POINT_ENTRY](../../atl/reference/connection-point-macros.md#connection_point_entry)<br/>
[更新可能なプロバイダーの作成](../../data/oledb/creating-an-updatable-provider.md)
