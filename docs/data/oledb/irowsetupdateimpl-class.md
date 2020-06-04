---
title: IRowsetUpdateImpl クラス
ms.date: 11/04/2016
f1_keywords:
- IRowsetUpdateImpl
- ATL.IRowsetUpdateImpl
- ATL::IRowsetUpdateImpl
- IRowsetUpdateImpl::SetData
- IRowsetUpdateImpl.SetData
- ATL::IRowsetUpdateImpl::SetData
- ATL.IRowsetUpdateImpl.SetData
- ATL.IRowsetUpdateImpl.GetOriginalData
- IRowsetUpdateImpl.GetOriginalData
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
ms.openlocfilehash: 6347a42b9065239f768c6b50c430946393358df1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370748"
---
# <a name="irowsetupdateimpl-class"></a>IRowsetUpdateImpl クラス

[インターフェイス](/previous-versions/windows/desktop/ms714401(v=vs.85))の OLE DB テンプレートの実装。

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

*T*<br/>
から`IRowsetUpdateImpl`派生したクラス。

*Storage*<br/>
ユーザー レコード。

*アレイを更新します。*<br/>
行セットを更新するためのキャッシュされたデータを格納している配列。

*行クラス*<br/>
のストレージ ユニット`HROW`。

*マップクラス*<br/>
プロバイダが保持するすべての行ハンドルの記憶装置。

## <a name="requirements"></a>必要条件

**ヘッダー:** atldb.h

## <a name="members"></a>メンバー

### <a name="interface-methods-used-with-irowsetchange"></a>インターフェイス メソッド (IRowsetChange で使用)

|||
|-|-|
|[Setdata](#setdata)|1 つ以上の列にデータ値を設定します。|

### <a name="interface-methods-used-with-irowsetupdate"></a>インターフェイス メソッド (IRowsetUpdate で使用)

|||
|-|-|
|[元のデータを取得します。](#getoriginaldata)|保留中の変更を無視して、データ ソースに最後に転送されたデータまたはデータ ソースから取得されたデータを取得します。|
|[保留中の行を取得します。](#getpendingrows)|保留中の変更がある行の一覧を返します。|
|[ゲットローステータス](#getrowstatus)|指定された行の状態を返します。|
|[取り消し](#undo)|最後のフェッチまたは更新以降の行に対する変更を元に変更を取り消します。|
|[更新](#update)|最後のフェッチまたは更新以降に行に加えられた変更を送信します。|

### <a name="implementation-methods-callback"></a>実装メソッド (コールバック)

|||
|-|-|
|[更新が許可されています](#isupdateallowed)|更新を許可する前に、セキュリティ、整合性などをチェックするために使用します。|

### <a name="data-members"></a>データ メンバー

|||
|-|-|
|[m_mapCachedData](#mapcacheddata)|遅延操作の元のデータが格納されます。|

## <a name="remarks"></a>解説

ここで説明する内容もすべて当てはまるので、まず[IRowsetChange](/previous-versions/windows/desktop/ms715790(v=vs.85))のドキュメントを読んで理解する必要があります。 また、データの設定に関する*OLE DB プログラマ リファレンスの*第 6 章も参照してください。

`IRowsetUpdateImpl`は、コンシューマーがデータ`IRowsetUpdate`ソースに加えられた変更の送信を遅延させ、転送前`IRowsetChange`に変更を元に戻すことを可能にする OLE DB インターフェイスを実装します。

> [!IMPORTANT]
> プロバイダーの実装を試みる前に、次のドキュメントを読むことを強くお勧めします。

- [更新可能なプロバイダーの作成](../../data/oledb/creating-an-updatable-provider.md)

- OLE DB*プログラマーズ リファレンス*の第 6 章

- また、クラスが`RUpdateRowset` [UpdatePV](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/ATL/OLEDB/Provider/UPDATEPV)サンプルでどのように使用されているかも確認できます。

## <a name="irowsetupdateimplsetdata"></a><a name="setdata"></a>IRowset更新インプラ

1 つ以上の列にデータ値を設定します。

### <a name="syntax"></a>構文

```cpp
STDMETHOD (SetData )(HROW hRow,
   HACCESSOR hAccessor,
   void* pSrcData);
```

#### <a name="parameters"></a>パラメーター

*OLE DB プログラマーズ リファレンス*の[「IRowsetChange::SetData」](/previous-versions/windows/desktop/ms721232(v=vs.85))を参照してください。

### <a name="remarks"></a>解説

このメソッドは[、IRowsetChangeImpl::SetData](../../data/oledb/irowsetchangeimpl-setdata.md)メソッドをオーバーライドしますが、操作の即時または遅延処理を許可する元のデータのキャッシュが含まれています。

## <a name="irowsetupdateimplgetoriginaldata"></a><a name="getoriginaldata"></a>イロウセット更新インプル::取得元データ

保留中の変更を無視して、データ ソースに最後に転送されたデータまたはデータ ソースから取得されたデータを取得します。

### <a name="syntax"></a>構文

```cpp
STDMETHOD (GetOriginalData )(HROW hRow,
   HACCESSOR hAccessor,
   void* pData);
```

#### <a name="parameters"></a>パラメーター

*OLE DB プログラマーズ リファレンス*の[「IRowsetUpdate::GetOriginalData」](/previous-versions/windows/desktop/ms709947(v=vs.85))を参照してください。

## <a name="irowsetupdateimplgetpendingrows"></a><a name="getpendingrows"></a>IRowset更新Impl::GetPending行

保留中の変更がある行の一覧を返します。

### <a name="syntax"></a>構文

```cpp
STDMETHOD (GetPendingRows )(HCHAPTER /* hReserved */,
   DBPENDINGSTATUS dwRowStatus,
   DBCOUNTITEM* pcPendingRows,
   HROW** prgPendingRows,
   DBPENDINGSTATUS** prgPendingStatus);
```

#### <a name="parameters"></a>パラメーター

*h予約済み*<br/>
[in]の h*章パラメーター*に対応します[。](/previous-versions/windows/desktop/ms719626(v=vs.85))

その他のパラメーターについては *、OLE DB プログラマ リファレンス*の[IRowsetUpdate::GetPendingRows](/previous-versions/windows/desktop/ms719626(v=vs.85))を参照してください。

### <a name="remarks"></a>解説

詳細については *、OLE DB プログラマ リファレンス*の[「IRowsetUpdate::GetPendingRows」](/previous-versions/windows/desktop/ms719626(v=vs.85))を参照してください。

## <a name="irowsetupdateimplgetrowstatus"></a><a name="getrowstatus"></a>イロウセット更新インプル::GetRowステータス

指定された行の状態を返します。

### <a name="syntax"></a>構文

```cpp
STDMETHOD (GetRowStatus )(HCHAPTER /* hReserved */,
   DBCOUNTITEM cRows,
   const HROW rghRows[],
   DBPENDINGSTATUS rgPendingStatus[]);
```

#### <a name="parameters"></a>パラメーター

*h予約済み*<br/>
[in]の h*章パラメーター*に対応[します。](/previous-versions/windows/desktop/ms724377(v=vs.85))

その他のパラメーターについては *、OLE DB プログラマ リファレンス*の[IRowsetUpdate::GetRowStatus](/previous-versions/windows/desktop/ms724377(v=vs.85))を参照してください。

## <a name="irowsetupdateimplundo"></a><a name="undo"></a>IRowset更新インプル::元に戻す

最後のフェッチまたは更新以降の行に対する変更を元に変更を取り消します。

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

*h予約済み*<br/>
[in][IRowsetUpdate::元に戻す](/previous-versions/windows/desktop/ms719655(v=vs.85))の*hChapter*パラメーターに対応します。

*を行なう*<br/>
[アウト][IRowsetUpdate::元に戻す](/previous-versions/windows/desktop/ms719655(v=vs.85))の*pcRows*パラメーターに対応します。

*プルグロウズ未行*<br/>
[in][IRowsetUpdate::元に戻す](/previous-versions/windows/desktop/ms719655(v=vs.85))の*prgRows*パラメーターに対応します。

その他のパラメーターについては *、OLE DB プログラマ リファレンス*の[IRowsetUpdate::Undo](/previous-versions/windows/desktop/ms719655(v=vs.85))を参照してください。

## <a name="irowsetupdateimplupdate"></a><a name="update"></a>IRowset更新Impl::更新

最後のフェッチまたは更新以降に行に加えられた変更を送信します。

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

*h予約済み*<br/>
[in]の h*章パラメーター*に対応[します。](/previous-versions/windows/desktop/ms719709(v=vs.85))

その他のパラメーターについては、 OLE DB プログラマ リファレンス の[IRowsetUpdate::Update](/previous-versions/windows/desktop/ms719709(v=vs.85))を*参照してください*。

### <a name="remarks"></a>解説

変更は[、IRowsetChangeImpl::フラッシュデータ](../../data/oledb/irowsetchangeimpl-flushdata.md)を呼び出すことによって送信されます。 コンシューマは、変更を有効にするために[CRowset::Update](../../data/oledb/crowset-update.md)を呼び出す必要があります。 *prgRowstatus*を *「OLE DB プログラマ リファレンス*」の[「行の状態](/previous-versions/windows/desktop/ms722752(v=vs.85))」で説明されているように適切な値に設定します。

## <a name="irowsetupdateimplisupdateallowed"></a><a name="isupdateallowed"></a>IRowset 更新インプラシスト::IsUpdate 許可

更新前にセキュリティ、整合性などを確認するには、このメソッドをオーバーライドします。

### <a name="syntax"></a>構文

```cpp
HRESULT IsUpdateAllowed(DBPENDINGSTATUS /* [in] */ /* status */,
   HROW /* [in] */ /* hRowUpdate */,
   DBROWSTATUS* /* [out] */ /* pRowStatus */);
```

#### <a name="parameters"></a>パラメーター

*status*<br/>
[in]行に対する保留中の操作の状態。

*フロウアップデート*<br/>
[in]ユーザーが更新する行のハンドル。

*ステータス*<br/>
[アウト]ユーザーに返される状態。

### <a name="remarks"></a>解説

更新を許可する必要があると判断した場合は、S_OK返します。それ以外の場合は、E_FAILを返します。 更新を許可する場合は`DBROWSTATUS`[、IRowsetUpdateImpl::Update](../../data/oledb/irowsetupdateimpl-update.md)を適切な[行状態](/previous-versions/windows/desktop/ms722752(v=vs.85))に設定する必要もあります。

## <a name="irowsetupdateimplm_mapcacheddata"></a><a name="mapcacheddata"></a>IRowset 更新Impl::m_mapCachedData

遅延操作の元のデータを含むマップ。

### <a name="syntax"></a>構文

```cpp
CAtlMap<
   HROW hRow,
   Storage* pData
>
m_mapCachedData;
```

#### <a name="parameters"></a>パラメーター

*hRow*<br/>
データの行へのハンドル。

*Pdata*<br/>
キャッシュされるデータへのポインター。 データのタイプは*ストレージ*(ユーザー・レコード・クラス) です。 [IRowsetUpdateImpl クラス](../../data/oledb/irowsetupdateimpl-class.md)の*ストレージ*テンプレート引数を参照してください。

## <a name="see-also"></a>関連項目

[OLE DB プロバイダー テンプレートに関するページ](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB プロバイダー テンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)<br/>
[更新可能なプロバイダーの作成](../../data/oledb/creating-an-updatable-provider.md)
