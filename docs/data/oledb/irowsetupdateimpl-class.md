---
description: '詳細情報: IRowsetUpdateImpl クラス'
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
ms.openlocfilehash: f040ed902b867059636a16bf635dc5c526b8ba1b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97317247"
---
# <a name="irowsetupdateimpl-class"></a>IRowsetUpdateImpl クラス

[IRowsetUpdate](/previous-versions/windows/desktop/ms714401(v=vs.85))インターフェイスの OLE DB テンプレートの実装。

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
から派生したクラス `IRowsetUpdateImpl` 。

*Storage*<br/>
ユーザーレコード。

*UpdateArray*<br/>
行セットを更新するためのキャッシュされたデータを格納している配列。

*RowClass*<br/>
のストレージユニット `HROW` 。

*MapClass*<br/>
プロバイダーによって保持されているすべての行ハンドルのストレージユニット。

## <a name="requirements"></a>要件

**ヘッダー:** atldb.h

## <a name="members"></a>メンバー

### <a name="interface-methods-used-with-irowsetchange"></a>インターフェイスメソッド (IRowsetChange と共に使用)

| 名前 | 説明 |
|-|-|
|[SetData](#setdata)|1つ以上の列にデータ値を設定します。|

### <a name="interface-methods-used-with-irowsetupdate"></a>インターフェイスメソッド (IRowsetUpdate と共に使用)

| 名前 | 説明 |
|-|-|
|[GetOriginalData](#getoriginaldata)|保留中の変更を無視して、データソースとの間で最後に転送または取得されたデータを取得します。|
|[GetPendingRows](#getpendingrows)|保留中の変更がある行の一覧を返します。|
|[GetRowStatus](#getrowstatus)|指定された行の状態を返します。|
|[元に戻す](#undo)|前回のフェッチまたは更新以降に行に加えられたすべての変更を元に戻します。|
|[アップデート](#update)|前回のフェッチまたは更新以降に行に加えられた変更を転送します。|

### <a name="implementation-methods-callback"></a>実装方法 (コールバック)

| 名前 | 説明 |
|-|-|
|[IsUpdateAllowed](#isupdateallowed)|更新を許可する前に、セキュリティ、整合性などを確認するために使用します。|

### <a name="data-members"></a>データ メンバー

| 名前 | 説明 |
|-|-|
|[m_mapCachedData](#mapcacheddata)|遅延操作の元のデータを格納します。|

## <a name="remarks"></a>解説

ここに記載されているすべてのものはここにも適用されるため、まず [IRowsetChange](/previous-versions/windows/desktop/ms715790(v=vs.85))のドキュメントを読んで理解しておく必要があります。 また、データの設定に関する *OLE DB プログラマーリファレンス* の第6章も参照してください。

`IRowsetUpdateImpl` OLE DB `IRowsetUpdate` インターフェイスを実装します。これにより、コンシューマーは、によるデータソースへの変更の送信を遅らせ、転送前に変更を元に戻すことができ `IRowsetChange` ます。

> [!IMPORTANT]
> プロバイダーを実装する前に、次のドキュメントを読むことを強くお勧めします。

- [更新可能なプロバイダーの作成](../../data/oledb/creating-an-updatable-provider.md)

- *OLE DB プログラマーリファレンス* の第6章

- また、 `RUpdateRowset` [UpdatePV](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/ATL/OLEDB/Provider/UPDATEPV) サンプルでのクラスの使用方法についても説明します。

## <a name="irowsetupdateimplsetdata"></a><a name="setdata"></a> IRowsetUpdateImpl:: SetData

1つ以上の列にデータ値を設定します。

### <a name="syntax"></a>構文

```cpp
STDMETHOD (SetData )(HROW hRow,
   HACCESSOR hAccessor,
   void* pSrcData);
```

#### <a name="parameters"></a>パラメーター

*OLE DB プログラマーリファレンス* の「 [IRowsetChange:: SetData](/previous-versions/windows/desktop/ms721232(v=vs.85)) 」を参照してください。

### <a name="remarks"></a>解説

このメソッドは [IRowsetChangeImpl:: SetData](./irowsetchangeimpl-class.md#setdata) メソッドをオーバーライドしますが、操作の即時処理または遅延処理を許可する元のデータのキャッシュを含みます。

## <a name="irowsetupdateimplgetoriginaldata"></a><a name="getoriginaldata"></a> IRowsetUpdateImpl:: GetOriginalData

保留中の変更を無視して、データソースとの間で最後に転送または取得されたデータを取得します。

### <a name="syntax"></a>構文

```cpp
STDMETHOD (GetOriginalData )(HROW hRow,
   HACCESSOR hAccessor,
   void* pData);
```

#### <a name="parameters"></a>パラメーター

*OLE DB プログラマーリファレンス* の「 [IRowsetUpdate:: getoriginaldata](/previous-versions/windows/desktop/ms709947(v=vs.85)) 」を参照してください。

## <a name="irowsetupdateimplgetpendingrows"></a><a name="getpendingrows"></a> IRowsetUpdateImpl:: GetPendingRows

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

*hReserved*<br/>
から [IRowsetUpdate:: GetPendingRows](/previous-versions/windows/desktop/ms719626(v=vs.85))の *hchapter* パラメーターに対応します。

その他のパラメーターについては、 *OLE DB プログラマーリファレンス* の「 [IRowsetUpdate:: getpendingrows](/previous-versions/windows/desktop/ms719626(v=vs.85)) 」を参照してください。

### <a name="remarks"></a>解説

詳細については、 *OLE DB プログラマーリファレンス* の「 [IRowsetUpdate:: getpendingrows](/previous-versions/windows/desktop/ms719626(v=vs.85)) 」を参照してください。

## <a name="irowsetupdateimplgetrowstatus"></a><a name="getrowstatus"></a> IRowsetUpdateImpl:: GetRowStatus

指定された行の状態を返します。

### <a name="syntax"></a>構文

```cpp
STDMETHOD (GetRowStatus )(HCHAPTER /* hReserved */,
   DBCOUNTITEM cRows,
   const HROW rghRows[],
   DBPENDINGSTATUS rgPendingStatus[]);
```

#### <a name="parameters"></a>パラメーター

*hReserved*<br/>
から [IRowsetUpdate:: GetRowStatus](/previous-versions/windows/desktop/ms724377(v=vs.85))の *hchapter* パラメーターに対応します。

その他のパラメーターについては、 *OLE DB プログラマーリファレンス* の「 [IRowsetUpdate:: getrowstatus](/previous-versions/windows/desktop/ms724377(v=vs.85)) 」を参照してください。

## <a name="irowsetupdateimplundo"></a><a name="undo"></a> IRowsetUpdateImpl:: Undo

前回のフェッチまたは更新以降に行に加えられたすべての変更を元に戻します。

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

*hReserved*<br/>
から [IRowsetUpdate:: Undo](/previous-versions/windows/desktop/ms719655(v=vs.85))の *hchapter* パラメーターに対応します。

*pcRowsUndone*<br/>
入出力 [IRowsetUpdate:: Undo](/previous-versions/windows/desktop/ms719655(v=vs.85))の *pcrows* パラメーターに対応します。

*Prgrowdone*<br/>
から [IRowsetUpdate:: Undo](/previous-versions/windows/desktop/ms719655(v=vs.85))の *prgrows* パラメーターに対応します。

その他のパラメーターについては、 *OLE DB プログラマーリファレンス* の「 [IRowsetUpdate:: Undo](/previous-versions/windows/desktop/ms719655(v=vs.85)) 」を参照してください。

## <a name="irowsetupdateimplupdate"></a><a name="update"></a> IRowsetUpdateImpl:: Update

前回のフェッチまたは更新以降に行に加えられた変更を転送します。

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

*hReserved*<br/>
から [IRowsetUpdate:: Update](/previous-versions/windows/desktop/ms719709(v=vs.85))の *hchapter* パラメーターに対応します。

その他のパラメーターについては、 *OLE DB プログラマーリファレンス* の「 [IRowsetUpdate:: Update](/previous-versions/windows/desktop/ms719709(v=vs.85)) 」を参照してください。

### <a name="remarks"></a>解説

変更は、 [IRowsetChangeImpl:: FlushData](./irowsetchangeimpl-class.md#flushdata)を呼び出すことによって送信されます。 変更を有効にするには、コンシューマーが [CRowset:: Update](./crowset-class.md#update) を呼び出す必要があります。 「 *OLE DB プログラマーのリファレンス*」の「[行の状態](/previous-versions/windows/desktop/ms722752(v=vs.85))」で説明されているように、 *prgrowstatus* を適切な値に設定します。

## <a name="irowsetupdateimplisupdateallowed"></a><a name="isupdateallowed"></a> IRowsetUpdateImpl:: IsUpdateAllowed

更新前にセキュリティ、整合性などを確認するには、このメソッドをオーバーライドします。

### <a name="syntax"></a>構文

```cpp
HRESULT IsUpdateAllowed(DBPENDINGSTATUS /* [in] */ /* status */,
   HROW /* [in] */ /* hRowUpdate */,
   DBROWSTATUS* /* [out] */ /* pRowStatus */);
```

#### <a name="parameters"></a>パラメーター

*status*<br/>
から行に対する保留中の操作の状態。

*hRowUpdate*<br/>
からユーザーが更新しようとしている行のハンドル。

*pRowStatus*<br/>
入出力ユーザーに返されるステータス。

### <a name="remarks"></a>解説

更新を許可する必要があると判断した場合、は S_OK を返します。それ以外の場合は E_FAIL を返します。 更新を許可する場合は、 `DBROWSTATUS` [IRowsetUpdateImpl:: update](#update) のを適切な [行の状態](/previous-versions/windows/desktop/ms722752(v=vs.85))に設定する必要もあります。

## <a name="irowsetupdateimplm_mapcacheddata"></a><a name="mapcacheddata"></a> IRowsetUpdateImpl:: m_mapCachedData

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
データの行を処理します。

*pData*<br/>
キャッシュされるデータへのポインター。 データは、型 *ストレージ* (ユーザーレコードクラス) です。 [IRowsetUpdateImpl クラス](../../data/oledb/irowsetupdateimpl-class.md)の *ストレージ* テンプレート引数を参照してください。

## <a name="see-also"></a>関連項目

[OLE DB プロバイダー テンプレートに関するページ](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB プロバイダーテンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)<br/>
[更新可能なプロバイダーの作成](../../data/oledb/creating-an-updatable-provider.md)
