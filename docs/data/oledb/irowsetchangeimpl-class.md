---
title: IRowsetChangeImpl クラス
ms.date: 11/04/2016
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
- IRowsetChangeImpl::SetData
- ATL.IRowsetChangeImpl.SetData
- IRowsetChangeImpl.SetData
- ATL::IRowsetChangeImpl::SetData
- IRowsetChangeImpl::FlushData
- IRowsetChangeImpl.FlushData
- FlushData
helpviewer_keywords:
- providers, updatable
- updatable providers, immediate update
- IRowsetChangeImpl class
- DeleteRows method
- InsertRow method
- SetData method
- FlushData method
ms.assetid: 1e9fee15-ed9e-4387-af8f-215569beca6c
ms.openlocfilehash: ae4ceea53ec91cc3f9593dd3789fcf61e0702274
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376945"
---
# <a name="irowsetchangeimpl-class"></a>IRowsetChangeImpl クラス

OLE DB 仕様の[IRowset インターフェイス](/previous-versions/windows/desktop/ms715790(v=vs.85))の実装。

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

*T*<br/>
から`IRowsetChangeImpl`派生したクラス。

*Storage*<br/>
ユーザー レコード。

*ベースインターフェイス*<br/>
インターフェイスの基本クラス ( など`IRowsetChange`) 。

*行クラス*<br/>
行ハンドルの記憶装置。

*マップクラス*<br/>
プロバイダが保持するすべての行ハンドルの記憶装置。

## <a name="requirements"></a>必要条件

**ヘッダー:** atldb.h

## <a name="members"></a>メンバー

### <a name="interface-methods-used-with-irowsetchange"></a>インターフェイス メソッド (IRowsetChange で使用)

|||
|-|-|
|[行の削除](#deleterows)|行セットから行を削除します。|
|[InsertRow](#insertrow)|行セットに行を挿入します。|
|[Setdata](#setdata)|1 つ以上の列にデータ値を設定します。|

### <a name="implementation-method-callback"></a>実装メソッド (コールバック)

|||
|-|-|
|[フラッシュデータ](#flushdata)|データをストアにコミットするプロバイダーによってオーバーライドされます。|

## <a name="remarks"></a>解説

このインターフェイスは、データ ストアへの即時書き込み操作を行います。 "即時" とは、エンド ユーザー (コンシューマを使用するユーザー) が変更を行うと、その変更がデータ ストアに直ちに転送され、元に戻すことができないことを意味します。

`IRowsetChangeImpl`OLE DB`IRowsetChange`インターフェイスを実装し、既存の行の列の値の更新、行の削除、および新しい行の挿入を可能にします。

OLE DB テンプレートの実装では、すべての基本`SetData`メソッド`InsertRow`( `DeleteRows`、 、、および ) がサポートされます。

> [!IMPORTANT]
> プロバイダーの実装を試みる前に、次のドキュメントを読むことを強くお勧めします。

- [更新可能なプロバイダーの作成](../../data/oledb/creating-an-updatable-provider.md)

- OLE DB*プログラマーズ リファレンス*の第 6 章

- また、クラスが`RUpdateRowset` [UpdatePV](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/ATL/OLEDB/Provider/UPDATEPV)サンプルでどのように使用されているかも確認してください。

## <a name="irowsetchangeimpldeleterows"></a><a name="deleterows"></a>イローセットチェンジルプル::Dエレテロウ

行セットから行を削除します。

### <a name="syntax"></a>構文

```cpp
STDMETHOD (DeleteRows )(HCHAPTER /* hReserved */,
   DBCOUNTITEM cRows,
   const HROW rghRows[],
   DBROWSTATUS rgRowStatus[]);
```

#### <a name="parameters"></a>パラメーター

OLE DB プログラマ リファレンスの[「IRowsetChange::DeleteRows](/previous-versions/windows/desktop/ms724362(v=vs.85))を*参照してください*。

## <a name="irowsetchangeimplinsertrow"></a><a name="insertrow"></a>イロウセットチェンジインプラ

行セット内の新しい行を作成して初期化します。

### <a name="syntax"></a>構文

```cpp
STDMETHOD (InsertRow )(HCHAPTER /* hReserved */,
   HACCESSOR hAccessor,
   void* pData,
   HROW* phRow);
```

#### <a name="parameters"></a>パラメーター

*OLE DB プログラマーズ リファレンス*の[「IRowsetChange::InsertRow」](/previous-versions/windows/desktop/ms716921(v=vs.85))を参照してください。

## <a name="irowsetchangeimplsetdata"></a><a name="setdata"></a>IRowset変更Impl::データセット

1 つ以上の列にデータ値を設定します。

### <a name="syntax"></a>構文

```cpp
STDMETHOD (SetData )(HROW hRow,
   HACCESSOR hAccessor,
   void* pSrcData);
```

#### <a name="parameters"></a>パラメーター

*OLE DB プログラマーズ リファレンス*の[「IRowsetChange::SetData」](/previous-versions/windows/desktop/ms721232(v=vs.85))を参照してください。

## <a name="irowsetchangeimplflushdata"></a><a name="flushdata"></a>IRowset変更Impl::フラッシュデータ

データをストアにコミットするプロバイダーによってオーバーライドされます。

### <a name="syntax"></a>構文

```cpp
HRESULT FlushData(HROW hRowToFlush,
   HACCESSOR hAccessorToFlush);
```

#### <a name="parameters"></a>パラメーター

*フロウトフラッシュ*<br/>
[in]データの行へのハンドル。 この行の型は、`IRowsetImpl`クラスの*RowClass*テンプレート引数 (`CSimpleRow`既定) から決定されます。

*フラッシュ*<br/>
[in]バインディング情報と型情報を含むアクセサーへの`PROVIDER_MAP`ハンドル ( [IAccessorImpl](../../data/oledb/iaccessorimpl-class.md)を参照してください ) 。

### <a name="return-value"></a>戻り値

標準の HRESULT。

## <a name="see-also"></a>関連項目

[OLE DB プロバイダー テンプレートに関するページ](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB プロバイダー テンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)
