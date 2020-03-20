---
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
ms.openlocfilehash: 481c2c0ec28972e9cef8d1103e49afa2037c2393
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/15/2019
ms.locfileid: "79544568"
---
# <a name="irowsetnotifycp-class"></a>IRowsetNotifyCP クラス

接続ポイントインターフェイス[IRowsetNotify](/previous-versions/windows/desktop/ms712959(v=vs.85))のプロバイダーサイトを実装します。

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
`IRowsetNotifyCP`から派生したクラス。

*ReentrantEventSync*<br/>
再入をサポートする mutex クラス (既定値は `CComSharedMutex`)。 ミューテックスは、1つのスレッドがリソースに相互に排他的にアクセスできるようにする同期オブジェクトです。

*piid*<br/>
`IRowsetNotify` 接続ポイントインターフェイスのインターフェイス ID ポインター (`IID*`)。 既定値は `&__uuidof(IRowsetNotify)` です。

*DynamicUnkArray*<br/>
[CComDynamicUnkArray](../../atl/reference/ccomdynamicunkarray-class.md)型の配列。クライアントシンクインターフェイスへの `IUnknown` ポインターの動的に割り当てられた配列です。

## <a name="requirements"></a>要件

**ヘッダー:** atldb.h

## <a name="members"></a>メンバー

### <a name="methods"></a>メソッド

|||
|-|-|
|[Fire_OnFieldChange](#onfieldchange)|コンシューマーに、列の値の変更を通知します。|
|[Fire_OnRowChange](#onrowchange)|行に影響する変更をコンシューマーに通知します。|
|[Fire_OnRowsetChange](#onrowsetchange)|行セット全体に影響を与える変更をコンシューマーに通知します。|

## <a name="remarks"></a>コメント

`IRowsetNotifyCP` は、行セットの内容に対する変更 `IID_IRowsetNotify` 接続ポイントでリスナーをアドバイズするように、ブロードキャスト関数を実装します。

コンシューマーが通知を処理できるように、 [IRowsetNotifyImpl](../../data/oledb/irowsetnotifyimpl-class.md)を使用してコンシューマー ("シンク" とも呼ばれます) に `IRowsetNotify` を実装して登録する必要があることにも注意してください。 「コンシューマーへのコネクションポイントインターフェイスの実装に関する[通知の受信](../../data/oledb/receiving-notifications.md)」を参照してください。

通知の実装の詳細については、「[更新可能なプロバイダーの作成](../../data/oledb/creating-an-updatable-provider.md)」の「サポート通知」を参照してください。

## <a name="irowsetnotifycpfire_onfieldchange"></a><a name="onfieldchange"></a>IRowsetNotifyCP:: Fire_OnFieldChange

列の値の変更をコンシューマーに通知するために、 [Onfieldchange](/previous-versions/windows/desktop/ms715961(v=vs.85))イベントをブロードキャストします。

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

*OLE DB プログラマーリファレンス*の「 [IRowsetNotify:: onfieldchange](/previous-versions/windows/desktop/ms715961(v=vs.85)) 」を参照してください。

## <a name="irowsetnotifycpfire_onrowchange"></a><a name="onrowchange"></a>IRowsetNotifyCP:: Fire_OnRowChange

`IID_IRowsetNotify` 接続ポイントのすべてのリスナーに[OnRowChange](/previous-versions/windows/desktop/ms722694(v=vs.85))イベントをブロードキャストし、行に影響する変更をコンシューマーに通知します。

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

*OLE DB プログラマーリファレンス*の「 [IRowsetNotify:: OnRowChange](/previous-versions/windows/desktop/ms722694(v=vs.85)) 」を参照してください。

## <a name="irowsetnotifycpfire_onrowsetchange"></a><a name="onrowsetchange"></a>IRowsetNotifyCP:: Fire_OnRowsetChange

`IID_IRowsetNotify` 接続ポイントのすべてのリスナーに[OnRowsetChange](/previous-versions/windows/desktop/ms722669(v=vs.85))イベントをブロードキャストし、行セット全体に影響を与える変更をコンシューマーに通知します。

### <a name="syntax"></a>構文

```cpp
HRESULT Fire_OnRowsetChange(IRowset* pRowset,
   DBREASON eReason,
   DBEVENTPHASE ePhase,
   BOOL fCantDeny);
```

#### <a name="parameters"></a>パラメーター

*OLE DB プログラマーリファレンス*の「 [IRowsetNotify:: OnRowsetChange](/previous-versions/windows/desktop/ms722669(v=vs.85)) 」を参照してください。

## <a name="see-also"></a>参照

[OLE DB プロバイダー テンプレートに関するページ](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB プロバイダー テンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)<br/>
[通知 (COM)](/windows/win32/com/notifications)<br/>
[BEGIN_CONNECTION_POINT_MAP](../../atl/reference/connection-point-macros.md#begin_connection_point_map)<br/>
[END_CONNECTION_POINT_MAP](../../atl/reference/connection-point-macros.md#end_connection_point_map)<br/>
[CONNECTION_POINT_ENTRY](../../atl/reference/connection-point-macros.md#connection_point_entry)<br/>
[更新可能なプロバイダーの作成](../../data/oledb/creating-an-updatable-provider.md)