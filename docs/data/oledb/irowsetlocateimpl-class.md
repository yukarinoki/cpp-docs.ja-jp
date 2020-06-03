---
title: IRowsetLocateImpl クラス
ms.date: 11/04/2016
f1_keywords:
- IRowsetLocateImpl
- ATL.IRowsetLocateImpl.Compare
- IRowsetLocateImpl::Compare
- IRowsetLocateImpl.Compare
- ATL::IRowsetLocateImpl::Compare
- GetRowsAt
- IRowsetLocateImpl.GetRowsAt
- ATL::IRowsetLocateImpl::GetRowsAt
- IRowsetLocateImpl::GetRowsAt
- ATL.IRowsetLocateImpl.GetRowsAt
- IRowsetLocateImpl::GetRowsByBookmark
- IRowsetLocateImpl.GetRowsByBookmark
- GetRowsByBookmark
- IRowsetLocateImpl::Hash
- IRowsetLocateImpl.Hash
- m_rgBookmarks
- IRowsetLocateImpl::m_rgBookmarks
- ATL.IRowsetLocateImpl.m_rgBookmarks
- ATL::IRowsetLocateImpl::m_rgBookmarks
- IRowsetLocateImpl.m_rgBookmarks
helpviewer_keywords:
- providers, bookmarks
- IRowsetLocateImpl class
- bookmarks, OLE DB
- Compare method
- GetRowsAt method
- GetRowsByBookmark method
- Hash method
- m_rgbookmarks
ms.assetid: a8aa3149-7ce8-4976-a680-2da193fd3234
ms.openlocfilehash: 06e860425215d9fde268b780c001301b14a1caa1
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80210432"
---
# <a name="irowsetlocateimpl-class"></a>IRowsetLocateImpl クラス

行セットから任意の行をフェッチする OLE DB [IRowsetLocate](/previous-versions/windows/desktop/ms721190(v=vs.85))インターフェイスを実装します。

## <a name="syntax"></a>構文

```cpp
template <
   class T,
   class RowsetInterface,
   class RowClass = CSimpleRow,
   class MapClass = CAtlMap < RowClass::KeyType, RowClass* >,
   class BookmarkKeyType = LONG,
   class BookmarkType = LONG,
   class BookmarkMapClass = CAtlMap < RowClass::KeyType, RowClass* >>
class ATL_NO_VTABLE IRowsetLocateImpl : public IRowsetImpl<
       T,
       RowsetInterface,
       RowClass,
       MapClass>
```

### <a name="parameters"></a>パラメーター

*T*<br/>
`IRowsetLocateImpl`から派生したクラス。

*RowsetInterface*<br/>
`IRowsetImpl`から派生したクラス。

*RowClass*<br/>
`HROW`のストレージユニット。

*MapClass*<br/>
プロバイダーによって保持されているすべての行ハンドルのストレージユニット。

*BookmarkKeyType*<br/>
ブックマークの型 (LONG や string など)。 通常のブックマークは、少なくとも2バイトの長さである必要があります。 (1 バイトの長さは、OLE DB 標準の[ブックマーク](/previous-versions/windows/desktop/ms712954(v=vs.85))`DBBMK_FIRST`、`DBBMK_LAST`、および `DBBMK_INVALID`用に予約されています)。

*BookmarkType*<br/>
ブックマークからデータへのリレーションシップを維持するためのマッピング機構。

*BookmarkMapClass*<br/>
ブックマークによって保持されているすべての行ハンドルのストレージ単位。

## <a name="requirements"></a>必要条件

**ヘッダー**: atldb.h

## <a name="members"></a>メンバー

### <a name="interface-methods"></a>インターフェイス メソッド

|||
|-|-|
|[比較](#compare)|2つのブックマークを比較します。|
|[GetRowsAt](#getrowsat)|ブックマークからのオフセットによって指定された行で始まる行をフェッチします。|
|[GetRowsByBookmark](#getrowsbybookmark)|指定したブックマークに一致する行をフェッチします。|
|[ハッシュ](#hash)|指定されたブックマークのハッシュ値を返します。|

### <a name="data-members"></a>データ メンバー

|||
|-|-|
|[m_rgBookmarks](#rgbookmarks)|ブックマークの配列。|

## <a name="remarks"></a>解説

`IRowsetLocateImpl` は、 [IRowsetLocate](/previous-versions/windows/desktop/ms721190(v=vs.85))インターフェイスの OLE DB テンプレートの実装です。 `IRowsetLocate` は、行セットから任意の行をフェッチするために使用されます。 このインターフェイスを実装していない行セットは `sequential` 行セットです。 行セットに `IRowsetLocate` が存在する場合、列0は行のブックマークです。この列を読み取ると、同じ行に再配置するために使用できるブックマーク値が取得されます。

`IRowsetLocateImpl` は、プロバイダーでブックマークサポートを実装するために使用されます。 ブックマークは、コンシューマーが行にすばやく戻ることができるようにするプレースホルダー (行セットのインデックス) です。これにより、データへの高速アクセスが可能になります。 プロバイダーは、行を一意に識別できるブックマークを決定します。 `IRowsetLocateImpl` メソッドを使用すると、ブックマークの比較、オフセットによる行のフェッチ、ブックマークによる行のフェッチ、およびブックマークのハッシュ値の取得を行うことができます。

行セット内の OLE DB ブックマークをサポートするには、行セットがこのクラスから継承されるようにします。

ブックマークサポートの実装の詳細については、『 *Visual C++プログラマーガイド』* の「[プロバイダーのサポート](../../data/oledb/provider-support-for-bookmarks.md)」および「プラットフォーム SDK の*OLE DB プログラマーリファレンス*」の[ブックマーク](/previous-versions/windows/desktop/ms709728(v=vs.85))を参照してください。

## <a name="irowsetlocateimplcompare"></a><a name="compare"></a>IRowsetLocateImpl:: Compare

2つのブックマークを比較します。

### <a name="syntax"></a>構文

```cpp
STDMETHOD (Compare )(HCHAPTER /* hReserved */,
   DBBKMARK cbBookmark1,
   const BYTE* pBookmark1,
   DBBKMARK cbBookmark2,
   const BYTE* pBookmark2,
   DBCOMPARE* pComparison);
```

#### <a name="parameters"></a>パラメーター

*OLE DB プログラマーリファレンス*の「 [IRowsetLocate:: Compare](/previous-versions/windows/desktop/ms709539(v=vs.85)) 」を参照してください。

### <a name="remarks"></a>解説

どちらのブックマークも、標準の OLE DB 定義された[標準のブックマーク](/previous-versions/windows/desktop/ms712954(v=vs.85))(`DBBMK_FIRST`、`DBBMK_LAST`、または `DBBMK_INVALID`) にすることができます。 `pComparison` に返される値は、次の2つのブックマーク間の関係を示します。

- DBCOMPARE_LT (`cbBookmark1` は `cbBookmark2`の前にあります)。

- DBCOMPARE_EQ (`cbBookmark1` は `cbBookmark2`に相当します)。

- DBCOMPARE_GT (`cbBookmark1` は `cbBookmark2`の後にあります)。

- DBCOMPARE_NE (ブックマークは同じであり、順序付けされていません)。

- DBCOMPARE_NOTCOMPARABLE (ブックマークを比較することはできません)。

## <a name="irowsetlocateimplgetrowsat"></a><a name="getrowsat"></a>IRowsetLocateImpl:: GetRowsAt

ブックマークからのオフセットによって指定された行で始まる行をフェッチします。

### <a name="syntax"></a>構文

```cpp
STDMETHOD (GetRowsAt )(HWATCHREGION /* hReserved1 */,
   HCHAPTER hReserved2,
   DBBKMARK cbBookmark,
   const BYTE* pBookmark,
   DBROWOFFSET lRowsOffset,
   DBROWCOUNT cRows,
   DBCOUNTITEM* pcRowsObtained,
   HROW** prghRows);
```

#### <a name="parameters"></a>パラメーター

*OLE DB プログラマーリファレンス*の「 [IRowsetLocate:: getrowsat](/previous-versions/windows/desktop/ms723031(v=vs.85)) 」を参照してください。

### <a name="remarks"></a>解説

代わりにカーソル位置からフェッチするには、 [IRowset:: GetRowsAt](/previous-versions/windows/desktop/ms723031(v=vs.85))を使用します。

`IRowsetLocateImpl::GetRowsAt` によってカーソル位置が変更されることはありません。

## <a name="irowsetlocateimplgetrowsbybookmark"></a><a name="getrowsbybookmark"></a>IRowsetLocateImpl:: GetRowsByBookmark

指定されたブックマークに一致する1つ以上の行をフェッチします。

### <a name="syntax"></a>構文

```cpp
STDMETHOD (GetRowsByBookmark )(HCHAPTER /* hReserved */,
   DBCOUNTITEM cRows,
   const DBBKMARK rgcbBookmarks[],
   const BYTE* rgpBookmarks,
   HROW rghRows[],
   DBROWSTATUS* rgRowStatus[]);
```

#### <a name="parameters"></a>パラメーター

*hReserved*<br/>
から[IRowsetLocate:: GetRowsByBookmark](/previous-versions/windows/desktop/ms725420(v=vs.85))の*hchapter*パラメーターに対応します。

その他のパラメーターについては、 *OLE DB プログラマーリファレンス*の「 [IRowsetLocate:: GetRowsByBookmark](/previous-versions/windows/desktop/ms725420(v=vs.85)) 」を参照してください。

### <a name="remarks"></a>解説

ブックマークには、定義する値、または OLE DB[標準のブックマーク](/previous-versions/windows/desktop/ms712954(v=vs.85))(`DBBMK_FIRST` または `DBBMK_LAST`) を指定できます。 カーソル位置を変更しません。

## <a name="irowsetlocateimplhash"></a><a name="hash"></a>IRowsetLocateImpl:: Hash

指定されたブックマークのハッシュ値を返します。

### <a name="syntax"></a>構文

```cpp
STDMETHOD (Hash )(HCHAPTER /* hReserved */,
   DBBKMARK cbBookmarks,
   const DBBKMARK* rgcbBookmarks[],
   const BYTE* rgpBookmarks[],
   DBHASHVALUE rgHashValues[],
   DBROWSTATUS rgBookmarkStatus[]);
```

#### <a name="parameters"></a>パラメーター

*hReserved*<br/>
から[IRowsetLocate:: Hash](/previous-versions/windows/desktop/ms709697(v=vs.85))の*hchapter*パラメーターに対応します。

その他のパラメーターについては、 *OLE DB プログラマーリファレンス*の「 [IRowsetLocate:: Hash](/previous-versions/windows/desktop/ms709697(v=vs.85)) 」を参照してください。

## <a name="irowsetlocateimplm_rgbookmarks"></a><a name="rgbookmarks"></a>IRowsetLocateImpl:: m_rgBookmarks

ブックマークの配列。

### <a name="syntax"></a>構文

```cpp
CAtlArray<DBROWCOUNT> m_rgBookmarks;
```

## <a name="see-also"></a>参照

[OLE DB プロバイダー テンプレートに関するページ](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB プロバイダー テンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)<br/>
[IRowsetLocate: IRowset](/previous-versions/windows/desktop/ms721190(v=vs.85))
[プロバイダーによるブックマークのサポート](../../data/oledb/provider-support-for-bookmarks.md)<br/>
[ブックマーク](/previous-versions/windows/desktop/ms709728(v=vs.85))
