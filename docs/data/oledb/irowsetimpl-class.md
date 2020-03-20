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
ms.openlocfilehash: 2fbe461bfc812c5ac9b9a09aa3ed31c0a2a638e1
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2020
ms.locfileid: "79546045"
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
`IRowsetImpl`から派生したクラス。

*RowsetInterface*<br/>
`IRowsetImpl`から派生したクラス。

*RowClass*<br/>
`HROW`のストレージユニット。

*MapClass*<br/>
プロバイダーによって保持されているすべての行ハンドルのストレージユニット。

## <a name="requirements"></a>要件

**ヘッダー:** atldb.h

## <a name="members"></a>メンバー

### <a name="methods"></a>メソッド

|||
|-|-|
|[AddRefRows](#addrefrows)|既存の行ハンドルの参照カウントをインクリメントします。|
|[CreateRow](#createrow)|新しい `HROW`を割り当てるために[GetNextRows](../../data/oledb/irowsetimpl-getnextrows.md)によって呼び出されます。 ユーザーによって直接呼び出されることはありません。|
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

## <a name="remarks"></a>コメント

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

新しい `HROW`を割り当てるために[GetNextRows](../../data/oledb/irowsetimpl-getnextrows.md)によって呼び出されるヘルパーメソッド。

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
新しく作成された行ハンドルを使用して、`HROW`の配列が呼び出し元に返されます。

### <a name="remarks"></a>コメント

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

一部のパラメーターは、`IRowset::GetData`で説明されているさまざまな名前の*プログラマの参照パラメーター OLE DB*に対応しています。

|テンプレートパラメーターの OLE DB|*OLE DB プログラマーの参照*パラメーター|
|--------------------------------|------------------------------------------------|
|*pDstData*|*pData*|

### <a name="remarks"></a>コメント

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

### <a name="remarks"></a>コメント

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

### <a name="remarks"></a>コメント

行セットの位置は、`GetNextRow` が呼び出されるまで未定義です。 `RestartPosition` を呼び出し、後方にフェッチまたはスクロールすることによって、rowet の後方に移動できます。

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

### <a name="remarks"></a>コメント

プロバイダーは、この関数をオーバーライドして DBSTATUS_S_ISNULL および DBSTATUS_S_DEFAULT の特別な処理を提供します。

## <a name="irowsetimplm_bcanfetchback"></a><a name="bcanfetchback"></a>IRowsetImpl:: m_bCanFetchBack

プロバイダーが後方フェッチをサポートするかどうかを示します。

### <a name="syntax"></a>構文

```cpp
unsigned m_bCanFetchBack:1;
```

### <a name="remarks"></a>コメント

`DBPROPSET_ROWSET` グループの `DBPROP_CANFETCHBACKWARDS` プロパティにリンクされています。 `m_bCanFetchBackwards` を**true**にするには、プロバイダーが `DBPROP_CANFETCHBACKWARDS` をサポートしている必要があります。

## <a name="irowsetimplm_bcanscrollback"></a><a name="bcanscrollback"></a>IRowsetImpl:: m_bCanScrollBack

プロバイダーがカーソルを後方にスクロールできるかどうかを示します。

### <a name="syntax"></a>構文

```cpp
unsigned  m_bCanScrollBack:1;
```

### <a name="remarks"></a>コメント

`DBPROPSET_ROWSET` グループの `DBPROP_CANSCROLLBACKWARDS` プロパティにリンクされています。 `m_bCanFetchBackwards` を**true**にするには、プロバイダーが `DBPROP_CANSCROLLBACKWARDS` をサポートしている必要があります。

## <a name="irowsetimplm_breset"></a><a name="breset"></a>IRowsetImpl:: m_bReset

カーソル位置が行セットで定義されているかどうかを判断するために使用されるビットフラグ。

### <a name="syntax"></a>構文

```cpp
unsigned m_bReset:1;
```

### <a name="remarks"></a>コメント

コンシューマーが負の `lOffset` または*cRows*を使用して[GetNextRows](../../data/oledb/irowsetimpl-getnextrows.md)を呼び出し、`m_bReset` が true の場合、`GetNextRows` は行セットの末尾に移動します。 `m_bReset` が false の場合、コンシューマーは OLE DB 仕様に準拠したエラーコードを受け取ります。 `m_bReset` フラグは、行セットが最初に作成されたときと、コンシューマーが[IRowsetImpl:: RestartPosition](../../data/oledb/irowsetimpl-restartposition.md)を呼び出すときに**true**に設定されます。 `GetNextRows`を呼び出すと、 **false**に設定されます。

## <a name="irowsetimplm_irowset"></a><a name="irowset"></a>IRowsetImpl:: m_iRowset

カーソルを表す行セットへのインデックス。

### <a name="syntax"></a>構文

```cpp
DBROWOFFSET m_iRowset;
```

## <a name="irowsetimplm_rgrowhandles"></a><a name="rgrowhandles"></a>IRowsetImpl:: m_rgRowHandles

`GetNextRows`に応答して、プロバイダーによって現在格納されている行ハンドルのマップ。

### <a name="syntax"></a>構文

```cpp
MapClass m_rgRowHandles;
```

### <a name="remarks"></a>コメント

行ハンドルは `ReleaseRows`を呼び出すことによって削除されます。 *Mapclass*の定義については、「 [IRowsetImpl の概要](../../data/oledb/irowsetimpl-class.md)」を参照してください。

## <a name="see-also"></a>参照

[OLE DB プロバイダー テンプレートに関するページ](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB プロバイダー テンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)<br/>
[CSimpleRow クラス](../../data/oledb/csimplerow-class.md)