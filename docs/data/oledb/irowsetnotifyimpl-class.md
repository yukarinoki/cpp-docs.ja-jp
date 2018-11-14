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
ms.openlocfilehash: 01bcc60b0c88a3953d5e75b53ac58877f7eb15df
ms.sourcegitcommit: c40469825b6101baac87d43e5f4aed6df6b078f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/12/2018
ms.locfileid: "51556388"
---
# <a name="irowsetnotifyimpl-class"></a>IRowsetNotifyImpl クラス

実装し、登録[IRowsetNotify](https://docs.microsoft.com/previous-versions/windows/desktop/ms712959(v=vs.85))コンシューマー (別名「シンク」) の通知を処理できるようにします。

## <a name="syntax"></a>構文

```cpp
class ATL_NO_VTABLE IRowsetNotifyImpl : public IRowsetNotify
```

## <a name="requirements"></a>必要条件

**ヘッダー:** atldbcli.h

## <a name="members"></a>メンバー

### <a name="methods"></a>メソッド

|||
|-|-|
|[OnFieldChange](#onfieldchange)|列の値の変更をコンシューマーに通知します。|
|[OnRowChange](#onrowchange)|最初の行を変更または行全体に影響する変更のコンシューマーに通知します。|
|[OnRowsetChange](#onrowsetchange)|行セット全体に影響を与える変更をコンシューマーに通知します。|

## <a name="remarks"></a>Remarks

参照してください[通知の受信](../../data/oledb/receiving-notifications.md)コンシューマーのコネクション ポイントのインターフェイスを実装する方法。

`IRowsetNotifyImpl` ダミー実装を提供`IRowsetNotify`、空の関数を含む、`IRowsetNotify`メソッド[OnFieldChange](https://docs.microsoft.com/previous-versions/windows/desktop/ms715961(v=vs.85))、 [OnRowChange](https://docs.microsoft.com/previous-versions/windows/desktop/ms722694(v=vs.85))、および[OnRowsetChange](https://docs.microsoft.com/previous-versions/windows/desktop/ms722669(v=vs.85)). 実装する場合、このクラスから継承する場合、`IRowsetNotify`インターフェイスに必要なメソッドのみを実装することができます。 また、自分でその他のメソッドの空の実装を提供する必要があります。

## <a name="onfieldchange"></a> Irowsetnotifyimpl::onfieldchange

列の値の変更をコンシューマーに通知します。

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

参照してください[は、](https://docs.microsoft.com/previous-versions/windows/desktop/ms715961(v=vs.85))のパラメーターの説明。

### <a name="return-value"></a>戻り値

参照してください[は、](https://docs.microsoft.com/previous-versions/windows/desktop/ms715961(v=vs.85))値の説明を返します。

### <a name="remarks"></a>Remarks

このメソッドはラップ、[は、](https://docs.microsoft.com/previous-versions/windows/desktop/ms715961(v=vs.85))メソッド。 詳細については、OLE DB プログラマーズ リファレンス、そのメソッドの説明を参照してください。

## <a name="onrowchange"></a> Irowsetnotifyimpl::onrowchange

最初の行を変更または行全体に影響する変更のコンシューマーに通知します。

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

参照してください[は、](https://docs.microsoft.com/previous-versions/windows/desktop/ms722694(v=vs.85))のパラメーターの説明。

### <a name="return-value"></a>戻り値

参照してください[は、](https://docs.microsoft.com/previous-versions/windows/desktop/ms722694(v=vs.85))値の説明を返します。

### <a name="remarks"></a>Remarks

このメソッドはラップ、[は、](https://docs.microsoft.com/previous-versions/windows/desktop/ms722694(v=vs.85))メソッド。 詳細については、OLE DB プログラマーズ リファレンス、そのメソッドの説明を参照してください。

## <a name="onrowsetchange"></a> Irowsetnotifyimpl::onrowsetchange

行セット全体に影響を与える変更をコンシューマーに通知します。

### <a name="syntax"></a>構文

```cpp
STDMETHOD(OnRowsetChange)(
/* [in] */ IRowset* /* pRowset */,
/* [in] */ DBREASON /* eReason */,
/* [in] */ DBEVENTPHASE /* ePhase */,
/* [in] */ BOOL /* fCantDeny */)
```

#### <a name="parameters"></a>パラメーター

参照してください[は、](https://docs.microsoft.com/previous-versions/windows/desktop/ms722669(v=vs.85))のパラメーターの説明。

### <a name="return-value"></a>戻り値

参照してください[は、](https://docs.microsoft.com/previous-versions/windows/desktop/ms722669(v=vs.85))値の説明を返します。

### <a name="remarks"></a>Remarks

このメソッドはラップ、[は、](https://docs.microsoft.com/previous-versions/windows/desktop/ms722669(v=vs.85))メソッド。 詳細については、OLE DB プログラマーズ リファレンス、そのメソッドの説明を参照してください。

## <a name="see-also"></a>関連項目

[OLE DB コンシューマー テンプレート](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB コンシューマー テンプレート](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[IRowsetNotify](https://docs.microsoft.com/previous-versions/windows/desktop/ms712959(v=vs.85))
[IRowsetNotifyCP クラス](../../data/oledb/irowsetnotifycp-class.md)