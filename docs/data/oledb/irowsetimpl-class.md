---
title: IRowsetImpl クラス
ms.date: 11/04/2016
f1_keywords:
- IRowsetImpl
- IRowsetImpl::AddRefRows
- IRowsetImpl.AddRefRows
- ATL::IRowsetImpl::AddRefRows
- ATL.IRowsetImpl.AddRefRows
- IRowsetImpl.CreateRow
- ATL.IRowsetImpl.CreateRow
- ATL::IRowsetImpl::CreateRow
- CreateRow
- IRowsetImpl::CreateRow
- ATL.IRowsetImpl.GetData
- ATL::IRowsetImpl::GetData
- IRowsetImpl::GetData
- IRowsetImpl.GetData
- GetDBStatus
- IRowsetImpl.GetDBStatus
- IRowsetImpl::GetDBStatus
- GetNextRows
- ATL.IRowsetImpl.GetNextRows
- ATL::IRowsetImpl::GetNextRows
- IRowsetImpl::GetNextRows
- IRowsetImpl.GetNextRows
- IRowsetImpl.IRowsetImpl
- ATL::IRowsetImpl::IRowsetImpl
- ATL.IRowsetImpl.IRowsetImpl
- IRowsetImpl::IRowsetImpl
- ATL::IRowsetImpl::RefRows
- ATL.IRowsetImpl.RefRows
- IRowsetImpl.RefRows
- RefRows
- IRowsetImpl::RefRows
- ATL.IRowsetImpl.ReleaseRows
- IRowsetImpl::ReleaseRows
- ATL::IRowsetImpl::ReleaseRows
- IRowsetImpl.ReleaseRows
- ATL.IRowsetImpl.RestartPosition
- IRowsetImpl::RestartPosition
- RestartPosition
- ATL::IRowsetImpl::RestartPosition
- IRowsetImpl.RestartPosition
- IRowsetImpl.SetDBStatus
- IRowsetImpl::SetDBStatus
- SetDBStatus
- ATL.IRowsetImpl.m_bCanFetchBack
- ATL::IRowsetImpl::m_bCanFetchBack
- IRowsetImpl.m_bCanFetchBack
- IRowsetImpl::m_bCanFetchBack
- m_bCanFetchBack
- IRowsetImpl::m_bCanScrollBack
- ATL::IRowsetImpl::m_bCanScrollBack
- IRowsetImpl.m_bCanScrollBack
- ATL.IRowsetImpl.m_bCanScrollBack
- m_bCanScrollBack
- ATL.IRowsetImpl.m_bReset
- IRowsetImpl.m_bReset
- m_bReset
- IRowsetImpl::m_bReset
- ATL::IRowsetImpl::m_bReset
- IRowsetImpl::m_iRowset
- IRowsetImpl.m_iRowset
- ATL::IRowsetImpl::m_iRowset
- ATL.IRowsetImpl.m_iRowset
- m_iRowset
- IRowsetImpl::m_rgRowHandles
- IRowsetImpl.m_rgRowHandles
- m_rgRowHandles
- ATL::IRowsetImpl::m_rgRowHandles
- ATL.IRowsetImpl.m_rgRowHandles
helpviewer_keywords:
- IRowsetImpl class
- AddRefRows method
- CreateRow method
- GetData method [OLE DB]
- GetDBStatus method
- GetNextRows method
- IRowsetImpl constructor
- RefRows method
- ReleaseRows method
- RestartPosition method
- SetDBStatus method
- m_bCanFetchBack
- m_bCanScrollBack
- m_bReset
- m_iRowset
- m_rgRowHandles
ms.assetid: 6a9189af-7556-45b1-adcb-9d62bb36704c
ms.openlocfilehash: f440bb891c30033962208c3e89648bd05ba3f81b
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87232145"
---
# <a name="irowsetimpl-class"></a>IRowsetImpl クラス

`IRowset` インターフェイスの実装を提供します。

## <a name="syntax"></a>構文

```cpp
template <
   class T,
   class RowsetInterface,
   class RowClass = CSimpleRow,
   class MapClass = CAtlMap <
      RowClass::KeyType,
      RowClass*>>
class ATL_NO_VTABLE IRowsetImpl : public RowsetInterface
```

### <a name="parameters"></a>パラメーター

*T*<br/>
から派生したクラス `IRowsetImpl` 。

*RowsetInterface*<br/>
から派生したクラス `IRowsetImpl` 。

*RowClass*<br/>
のストレージユニット `HROW` 。

*MapClass*<br/>
プロバイダーによって保持されているすべての行ハンドルのストレージユニット。

## <a name="requirements"></a>必要条件

**ヘッダー:** atldb.h

## <a name="members"></a>メンバー

### <a name="methods"></a>メソッド

|||
|-|-|
|[AddRefRows](#addrefrows)|既存の行ハンドルの参照カウントをインクリメントします。|
|[CreateRow](#createrow)|新しいを割り当てるために[GetNextRows](../../data/oledb/irowsetimpl-getnextrows.md)によって呼び出され `HROW` ます。 ユーザーによって直接呼び出されることはありません。|
|[GetData](#getdata)|行セットの行のコピーからデータを取得します。|
|[GetDBStatus](#getdbstatus)|指定されたフィールドの状態を返します。|
|[GetNextRows](#getnextrows)|前の位置を記憶しながら、順番に行をフェッチします。|
|[IRowsetImpl](#irowsetimpl)|コンストラクターです。 ユーザーによって直接呼び出されることはありません。|
|[RefRows](#refrows)|[Addrefrows](../../data/oledb/irowsetimpl-addrefrows.md)および[ReleaseRows](../../data/oledb/irowsetimpl-releaserows.md)によって呼び出されます。 ユーザーによって直接呼び出されることはありません。|
|[ReleaseRows](#releaserows)|行を解放します。|
|[RestartPosition](#restartposition)|次のフェッチ位置を初期位置に再配置します。つまり、行セットが最初に作成されたときの位置。|
|[SetDBStatus](#setdbstatus)|指定されたフィールドの状態フラグを設定します。|

### <a name="data-members"></a>データ メンバー

|||
|-|-|
|[m_bCanFetchBack](#bcanfetchback)|プロバイダーが後方フェッチをサポートするかどうかを示します。|
|[m_bCanScrollBack](#bcanscrollback)|プロバイダーがカーソルを後方にスクロールできるかどうかを示します。|
|[m_bReset](#breset)|プロバイダーがカーソル位置をリセットしたかどうかを示します。 これは、 [GetNextRows](../../data/oledb/irowsetimpl-getnextrows.md)で後方にスクロールするとき、または逆方向にフェッチするときに特別な意味を持ちます。|
|[m_iRowset](#irowset)|カーソルを表す行セットへのインデックス。|
|[m_rgRowHandles](#rgrowhandles)|行ハンドルの一覧。|

## <a name="remarks"></a>解説

[IRowset](/previous-versions/windows/desktop/ms720986(v=vs.85))は、基本の行セットインターフェイスです。

## <a name="irowsetimpladdrefrows"></a><a name="addrefrows"></a>IRowsetImpl:: AddRefRows

既存の行ハンドルの参照カウントをインクリメントします。

### <a name="syntax"></a>構文

```cpp
STDMETHOD(AddRefRows )(DBCOUNTITEM cRows,
   const HROW rghRows[],
   DBREFCOUNT rgRefCounts[],
   DBROWSTATUS rgRowStatus[]);
```

#### <a name="parameters"></a>パラメーター

*OLE DB プログラマーリファレンス*の「 [IRowset:: addrefrows](/previous-versions/windows/desktop/ms719619(v=vs.85)) 」を参照してください。

## <a name="irowsetimplcreaterow"></a><a name="createrow"></a>IRowsetImpl:: CreateRow

新しいを割り当てるために[GetNextRows](../../data/oledb/irowsetimpl-getnextrows.md)によって呼び出されるヘルパーメソッド。 `HROW`

### <a name="syntax"></a>構文

```cpp
HRESULT CreateRow(DBROWOFFSET lRowsOffset,
   DBCOUNTITEM& cRowsObtained,
   HROW* rgRows);
```

#### <a name="parameters"></a>パラメーター

*lRowsOffset*<br/>
作成される行のカーソル位置。

*cRowsObtained*<br/>
作成された行の数を示す、ユーザーに返される参照。

*rgRows*<br/>
`HROW`新しく作成された行ハンドルを使用して、呼び出し元に返されるの配列。

### <a name="remarks"></a>解説

行が存在する場合、このメソッドは[Addrefrows](../../data/oledb/irowsetimpl-addrefrows.md)を呼び出し、を返します。 それ以外の場合は、RowClass テンプレート変数の新しいインスタンスを割り当て、それを[m_rgRowHandles](../../data/oledb/irowsetimpl-m-rgrowhandles.md)に追加します。

## <a name="irowsetimplgetdata"></a><a name="getdata"></a>IRowsetImpl:: GetData

行セットの行のコピーからデータを取得します。

### <a name="syntax"></a>構文

```cpp
STDMETHOD(GetData )(HROW hRow,
   HACCESSOR hAccessor,
   void* pDstData);
```

#### <a name="parameters"></a>パラメーター

*OLE DB プログラマーリファレンス*の「 [IRowset:: GetData](/previous-versions/windows/desktop/ms716988(v=vs.85)) 」を参照してください。

一部のパラメーターは、「」で説明されている、さまざまな名前の*プログラマの参照パラメーター OLE DB*に対応してい `IRowset::GetData` ます。

|テンプレートパラメーターの OLE DB|*OLE DB プログラマーの参照*パラメーター|
|--------------------------------|------------------------------------------------|
|*pDstData*|*pData*|

### <a name="remarks"></a>解説

では、OLE DB データ変換 DLL を使用したデータ変換も処理されます。

## <a name="irowsetimplgetdbstatus"></a><a name="getdbstatus"></a>IRowsetImpl:: GetDBStatus

指定されたフィールドの DBSTATUS status フラグを返します。

### <a name="syntax"></a>構文

```cpp
virtual DBSTATUS GetDBStatus(RowClass* currentRow,
   ATLCOLUMNINFO* columnNames);
```

#### <a name="parameters"></a>パラメーター

*currentRow*<br/>
から現在の行。

*columnNames*<br/>
から要求されている状態の列。

### <a name="return-value"></a>戻り値

列の[DBSTATUS](/previous-versions/windows/desktop/ms722617(v=vs.85))フラグ。

## <a name="irowsetimplgetnextrows"></a><a name="getnextrows"></a>IRowsetImpl:: GetNextRows

前の位置を記憶しながら、順番に行をフェッチします。

### <a name="syntax"></a>構文

```cpp
STDMETHOD(GetNextRows )(HCHAPTER hReserved,
   DBROWOFFSET lRowsOffset,
   DBROWCOUNT cRows,
   DBCOUNTITEM* pcRowsObtained,
   HROW** prghRows);
```

#### <a name="parameters"></a>パラメーター

*OLE DB プログラマーリファレンス*の「 [IRowset:: GetNextRows](/previous-versions/windows/desktop/ms709827(v=vs.85)) 」を参照してください。

## <a name="irowsetimplirowsetimpl"></a><a name="irowsetimpl"></a>IRowsetImpl:: IRowsetImpl

コンストラクターです。

### <a name="syntax"></a>構文

```cpp
IRowsetImpl();
```

### <a name="remarks"></a>解説

通常、このメソッドを直接呼び出す必要はありません。

## <a name="irowsetimplrefrows"></a><a name="refrows"></a>IRowsetImpl:: RefRows

[Addrefrows](../../data/oledb/irowsetimpl-addrefrows.md)および[ReleaseRows](../../data/oledb/irowsetimpl-releaserows.md)によって呼び出され、既存の行ハンドルに対して参照カウントをインクリメントまたは解放します。

### <a name="syntax"></a>構文

```cpp
HRESULT RefRows(DBCOUNTITEM cRows,
   const HROWrghRows[],
   DBREFCOUNT rgRefCounts[],
   DBROWSTATUS rgRowStatus[],
   BOOL bAdd);
```

#### <a name="parameters"></a>パラメーター

*OLE DB プログラマーリファレンス*の「 [IRowset:: addrefrows](/previous-versions/windows/desktop/ms719619(v=vs.85)) 」を参照してください。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

## <a name="irowsetimplreleaserows"></a><a name="releaserows"></a>IRowsetImpl:: ReleaseRows

行を解放します。

### <a name="syntax"></a>構文

```cpp
STDMETHOD(ReleaseRows )(DBCOUNTITEM cRows,
   const HROW rghRows[],
   DBROWOPTIONS rgRowOptions[],
   DBREFCOUNT rgRefCounts[],
   DBROWSTATUS rgRowStatus[]);
```

#### <a name="parameters"></a>パラメーター

*OLE DB プログラマーリファレンス*の「 [IRowset:: ReleaseRows](/previous-versions/windows/desktop/ms719771(v=vs.85)) 」を参照してください。

## <a name="irowsetimplrestartposition"></a><a name="restartposition"></a>IRowsetImpl:: RestartPosition

次のフェッチ位置を初期位置に再配置します。つまり、行セットが最初に作成されたときの位置。

### <a name="syntax"></a>構文

```cpp
STDMETHOD(RestartPosition )(HCHAPTER /* hReserved */);
```

#### <a name="parameters"></a>パラメーター

*OLE DB プログラマーリファレンス*の「 [IRowset:: RestartPosition](/previous-versions/windows/desktop/ms712877(v=vs.85)) 」を参照してください。

### <a name="remarks"></a>解説

行セットの位置は、が呼び出されるまで未定義です `GetNextRow` 。 を呼び出して `RestartPosition` 逆方向にフェッチまたはスクロールすることにより、rowet を後方に移動できます。

## <a name="irowsetimplsetdbstatus"></a><a name="setdbstatus"></a>IRowsetImpl:: SetDBStatus

指定されたフィールドの DBSTATUS status フラグを設定します。

### <a name="syntax"></a>構文

```cpp
virtual HRESULT SetDBStatus(DBSTATUS* statusFlags,
   RowClass* currentRow,
   ATLCOLUMNINFO* columnInfo);
```

#### <a name="parameters"></a>パラメーター

*statusFlags*<br/>
列に対して設定する[DBSTATUS](/previous-versions/windows/desktop/ms722617(v=vs.85))フラグ。

*currentRow*<br/>
現在の行のことです。

*columnInfo*<br/>
状態が設定されている列。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

プロバイダーは、この関数をオーバーライドして DBSTATUS_S_ISNULL および DBSTATUS_S_DEFAULT の特別な処理を提供します。

## <a name="irowsetimplm_bcanfetchback"></a><a name="bcanfetchback"></a>IRowsetImpl:: m_bCanFetchBack

プロバイダーが後方フェッチをサポートするかどうかを示します。

### <a name="syntax"></a>構文

```cpp
unsigned m_bCanFetchBack:1;
```

### <a name="remarks"></a>解説

`DBPROP_CANFETCHBACKWARDS`グループ内のプロパティにリンクさ `DBPROPSET_ROWSET` れています。 プロバイダーは、のをサポートする必要があり `DBPROP_CANFETCHBACKWARDS` `m_bCanFetchBackwards` **`true`** ます。

## <a name="irowsetimplm_bcanscrollback"></a><a name="bcanscrollback"></a>IRowsetImpl:: m_bCanScrollBack

プロバイダーがカーソルを後方にスクロールできるかどうかを示します。

### <a name="syntax"></a>構文

```cpp
unsigned  m_bCanScrollBack:1;
```

### <a name="remarks"></a>解説

`DBPROP_CANSCROLLBACKWARDS`グループ内のプロパティにリンクさ `DBPROPSET_ROWSET` れています。 プロバイダーは、のをサポートする必要があり `DBPROP_CANSCROLLBACKWARDS` `m_bCanFetchBackwards` **`true`** ます。

## <a name="irowsetimplm_breset"></a><a name="breset"></a>IRowsetImpl:: m_bReset

カーソル位置が行セットで定義されているかどうかを判断するために使用されるビットフラグ。

### <a name="syntax"></a>構文

```cpp
unsigned m_bReset:1;
```

### <a name="remarks"></a>解説

コンシューマーが負の値または CRows を使用して[GetNextRows](../../data/oledb/irowsetimpl-getnextrows.md)を呼び出し、 `lOffset` が true の場合*cRows* `m_bReset` 、は `GetNextRows` 行セットの末尾に移動します。 `m_bReset`が false の場合、コンシューマーは OLE DB 仕様に準拠してエラーコードを受け取ります。 この `m_bReset` フラグは、 **`true`** 行セットが最初に作成されたときと、コンシューマーが[IRowsetImpl:: RestartPosition](../../data/oledb/irowsetimpl-restartposition.md)を呼び出すときにに設定されます。 を呼び出すと、がに設定さ **`false`** `GetNextRows` れます。

## <a name="irowsetimplm_irowset"></a><a name="irowset"></a>IRowsetImpl:: m_iRowset

カーソルを表す行セットへのインデックス。

### <a name="syntax"></a>構文

```cpp
DBROWOFFSET m_iRowset;
```

## <a name="irowsetimplm_rgrowhandles"></a><a name="rgrowhandles"></a>IRowsetImpl:: m_rgRowHandles

に応答して、プロバイダーによって現在格納されている行ハンドルのマップ `GetNextRows` 。

### <a name="syntax"></a>構文

```cpp
MapClass m_rgRowHandles;
```

### <a name="remarks"></a>解説

行ハンドルは、を呼び出すことによって削除され `ReleaseRows` ます。 *Mapclass*の定義については、「 [IRowsetImpl の概要](../../data/oledb/irowsetimpl-class.md)」を参照してください。

## <a name="see-also"></a>関連項目

[OLE DB プロバイダー テンプレートに関するページ](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB プロバイダーテンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)<br/>
[CSimpleRow クラス](../../data/oledb/csimplerow-class.md)
