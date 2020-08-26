---
title: IRowsetNotifyImpl クラス
ms.date: 11/04/2016
f1_keywords:
- ATL.IRowsetNotifyImpl
- ATL::IRowsetNotifyImpl
- IRowsetNotifyImpl
- IRowsetNotifyImpl.OnFieldChange
- IRowsetNotifyImpl::OnFieldChange
- OnFieldChange
- IRowsetNotifyImpl::OnRowChange
- IRowsetNotifyImpl.OnRowChange
- OnRowChange
- OnRowsetChange
- IRowsetNotifyImpl::OnRowsetChange
- IRowsetNotifyImpl.OnRowsetChange
helpviewer_keywords:
- IRowsetNotifyImpl class
- OnFieldChange method
- OnRowChange method
- OnRowsetChange method
ms.assetid: fbfd0cb2-38ff-4b42-899a-8de902f834b8
ms.openlocfilehash: f938d9e92bc2f447ecfa82f2bfb27c8fda7652ab
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88845108"
---
# <a name="irowsetnotifyimpl-class"></a>IRowsetNotifyImpl クラス

コンシューマー ("シンク" とも呼ばれます) に [IRowsetNotify](/previous-versions/windows/desktop/ms712959(v=vs.85)) を実装して登録し、通知を処理できるようにします。

## <a name="syntax"></a>構文

```cpp
class ATL_NO_VTABLE IRowsetNotifyImpl : public IRowsetNotify
```

## <a name="requirements"></a>必要条件

**ヘッダー:** atldbcli.h

## <a name="members"></a>メンバー

### <a name="methods"></a>メソッド

| 名前 | 説明 |
|-|-|
|[OnFieldChange](#onfieldchange)|列の値に対する変更をコンシューマーに通知します。|
|[OnRowChange](#onrowchange)|行に対する最初の変更、または行全体に影響のある変更をコンシューマーに通知します。|
|[OnRowsetChange](#onrowsetchange)|行セット全体に影響のある変更をコンシューマーに通知します。|

## <a name="remarks"></a>解説

「コンシューマーへのコネクションポイントインターフェイスの実装に関する [通知の受信](../../data/oledb/receiving-notifications.md) 」を参照してください。

`IRowsetNotifyImpl` のダミーの実装を提供し `IRowsetNotify` 、 `IRowsetNotify` メソッド [onfieldchange](/previous-versions/windows/desktop/ms715961(v=vs.85))、 [OnRowChange](/previous-versions/windows/desktop/ms722694(v=vs.85))、および [OnRowsetChange](/previous-versions/windows/desktop/ms722669(v=vs.85))の空の関数を使用します。 インターフェイスを実装するときにこのクラスを継承する場合は、 `IRowsetNotify` 必要なメソッドのみを実装できます。 また、他のメソッドの空の実装を自分で提供する必要もあります。

## <a name="irowsetnotifyimplonfieldchange"></a><a name="onfieldchange"></a> IRowsetNotifyImpl:: OnFieldChange

列の値に対する変更をコンシューマーに通知します。

### <a name="syntax"></a>構文

```cpp
STDMETHOD(OnFieldChange)(
/* [in] */ IRowset* /* pRowset */,
/* [in] */ HROW /* hRow */,
/* [in] */ DBORDINAL /* cColumns */,
/* [size_is][in] */ DBORDINAL /* rgColumns */ [] ,
/* [in] */ DBREASON /* eReason */,
/* [in] */ DBEVENTPHASE /* ePhase */,
/* [in] */ BOOL /* fCantDeny */)
```

#### <a name="parameters"></a>パラメーター

パラメーターの説明については、「 [IRowsetNotify:: OnFieldChange](/previous-versions/windows/desktop/ms715961(v=vs.85)) 」を参照してください。

### <a name="return-value"></a>戻り値

戻り値の説明については、「 [IRowsetNotify:: OnFieldChange](/previous-versions/windows/desktop/ms715961(v=vs.85)) 」を参照してください。

### <a name="remarks"></a>解説

このメソッドは、 [IRowsetNotify:: OnFieldChange](/previous-versions/windows/desktop/ms715961(v=vs.85)) メソッドをラップします。 詳細については、OLE DB プログラマーリファレンスのメソッドの説明を参照してください。

## <a name="irowsetnotifyimplonrowchange"></a><a name="onrowchange"></a> IRowsetNotifyImpl:: OnRowChange

行に対する最初の変更、または行全体に影響のある変更をコンシューマーに通知します。

### <a name="syntax"></a>構文

```cpp
STDMETHOD(OnRowChange)(
/* [in] */ IRowset* /* pRowset */,
/* [in] */ DBCOUNTITEM /* cRows */,
/* [size_is][in] */ const HROW /* rghRows*/ [] ,
/* [in] */ DBREASON /* eReason */,
/* [in] */ DBEVENTPHASE /* ePhase */,
/* [in] */ BOOL /* fCantDeny */)
```

#### <a name="parameters"></a>パラメーター

パラメーターの説明については、「 [IRowsetNotify:: OnRowChange](/previous-versions/windows/desktop/ms722694(v=vs.85)) 」を参照してください。

### <a name="return-value"></a>戻り値

戻り値の説明については、「 [IRowsetNotify:: OnRowChange](/previous-versions/windows/desktop/ms722694(v=vs.85)) 」を参照してください。

### <a name="remarks"></a>解説

このメソッドは、 [IRowsetNotify:: OnRowChange](/previous-versions/windows/desktop/ms722694(v=vs.85)) メソッドをラップします。 詳細については、OLE DB プログラマーリファレンスのメソッドの説明を参照してください。

## <a name="irowsetnotifyimplonrowsetchange"></a><a name="onrowsetchange"></a> IRowsetNotifyImpl:: OnRowsetChange

行セット全体に影響のある変更をコンシューマーに通知します。

### <a name="syntax"></a>構文

```cpp
STDMETHOD(OnRowsetChange)(
/* [in] */ IRowset* /* pRowset */,
/* [in] */ DBREASON /* eReason */,
/* [in] */ DBEVENTPHASE /* ePhase */,
/* [in] */ BOOL /* fCantDeny */)
```

#### <a name="parameters"></a>パラメーター

パラメーターの説明については、「 [IRowsetNotify:: OnRowsetChange](/previous-versions/windows/desktop/ms722669(v=vs.85)) 」を参照してください。

### <a name="return-value"></a>戻り値

戻り値の説明については、「 [IRowsetNotify:: OnRowsetChange](/previous-versions/windows/desktop/ms722669(v=vs.85)) 」を参照してください。

### <a name="remarks"></a>解説

このメソッドは、 [IRowsetNotify:: OnRowsetChange](/previous-versions/windows/desktop/ms722669(v=vs.85)) メソッドをラップします。 詳細については、OLE DB プログラマーリファレンスのメソッドの説明を参照してください。

## <a name="see-also"></a>関連項目

[OLE DB コンシューマー テンプレート](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[IRowsetNotify](/previous-versions/windows/desktop/ms712959(v=vs.85)) 
[IRowsetNotifyCP クラス](../../data/oledb/irowsetnotifycp-class.md)
