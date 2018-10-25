---
title: IRowsetLocateImpl クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 35ebe1a4534fa1c3a738d84e3e6dd7037254fd49
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2018
ms.locfileid: "50059403"
---
# <a name="irowsetlocateimpl-class"></a>IRowsetLocateImpl クラス

OLE DB 実装[IRowsetLocate](/previous-versions/windows/desktop/ms721190)インターフェイスで、行セットから任意の行がフェッチされます。

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
派生したクラス`IRowsetLocateImpl`します。

*RowsetInterface*<br/>
派生したクラス`IRowsetImpl`します。

*RowClass*<br/>
記憶域ユニット、`HROW`します。

*MapClass*<br/>
プロバイダーによって保持されているすべての行ハンドルのストレージ ユニット。

*BookmarkKeyType*<br/>
長整数型や文字列など、ブックマークの型。 通常のブックマークには少なくとも 2 つのバイトの長さが必要です。 (1 バイトの長さは、OLE DB 用に予約された[標準ブックマーク](/previous-versions/windows/desktop/ms712954)`DBBMK_FIRST`、 `DBBMK_LAST`、および`DBBMK_INVALID`)。

*BookmarkType*<br/>
データへのブックマーク間のリレーションシップを維持するためのマッピング メカニズム。

*BookmarkMapClass*<br/>
ブックマークによって保持されているすべての行ハンドルのストレージ ユニット。

## <a name="requirements"></a>必要条件

**ヘッダー**: atldb.h

## <a name="members"></a>メンバー

### <a name="interface-methods"></a>インターフェイス メソッド

|||
|-|-|
|[Compare](#compare)|2 つのブックマークを比較します。|
|[GetRowsAt](#getrowsat)|ブックマークからのオフセットで指定した行で始まる行をフェッチします。|
|[GetRowsByBookmark](#getrowsbybookmark)|指定されたブックマークに一致する行をフェッチします。|
|[ハッシュ](#hash)|ハッシュの指定されたブックマークの値を返します。|

### <a name="data-members"></a>データ メンバー

|||
|-|-|
|[m_rgBookmarks](#rgbookmarks)|ブックマークの配列。|

## <a name="remarks"></a>Remarks

`IRowsetLocateImpl` OLE DB テンプレートの実装、 [IRowsetLocate](/previous-versions/windows/desktop/ms721190)インターフェイス。 `IRowsetLocate` 行セットからの任意の行のフェッチに使用されます。 このインターフェイスを実装していない行セットは、`sequential`行セット。 ときに`IRowsetLocate`が存在する、行セット列 0 が行のブックマーク; の同じ行に位置を変更するために使用するブックマークの値を取得はこのコラムを読みます。

`IRowsetLocateImpl` プロバイダーのブックマーク サポートを実装するために使用されます。 ブックマークは、プレース ホルダー (行セットでのインデックス)、行にすばやく戻るコンシューマーを有効にするデータを高速アクセスを許可します。 プロバイダーは、どのようなブックマークは一意を決定します。 行を識別します。 使用して`IRowsetLocateImpl`メソッド、ブックマークを比較する、行のフェッチがでオフセット、ブックマークによる行のフェッチおよびブックマークのハッシュ値を返します。

で行セットの OLE DB のブックマークをサポートするには、このクラスから継承する行セットを確認します。

ブックマークのサポートを実装する方法の詳細については、次を参照してください[プロバイダーのサポートのブックマーク](../../data/oledb/provider-support-for-bookmarks.md)で、 *Visual C++ プログラマ ガイド*と[ブックマーク](/previous-versions/windows/desktop/ms709728)、で *。OLE DB プログラマーズ リファレンス*プラットフォーム SDK にします。

## <a name="compare"></a> Irowsetlocateimpl::compare

2 つのブックマークを比較します。

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

参照してください[IRowsetLocate::Compare](/previous-versions/windows/desktop/ms709539)で、 *OLE DB プログラマーズ リファレンス*します。

### <a name="remarks"></a>Remarks

いずれかのブックマークは、標準 OLE DB 定義[標準ブックマーク](/previous-versions/windows/desktop/ms712954)(`DBBMK_FIRST`、 `DBBMK_LAST`、または`DBBMK_INVALID`)。 戻り値`pComparison`2 つのブックマークの間のリレーションシップを示します。

- DBCOMPARE_LT (`cbBookmark1`前`cbBookmark2`)。

- DBCOMPARE_EQ (`cbBookmark1`と等しい`cbBookmark2`)。

- DBCOMPARE_GT (`cbBookmark1`後`cbBookmark2`)。

- DBCOMPARE_NE (ブックマークは等しいと順序が付いていません)。

- DBCOMPARE_NOTCOMPARABLE (ブックマークは比較できません。)

## <a name="getrowsat"></a> Irowsetlocateimpl::getrowsat

ブックマークからのオフセットで指定した行で始まる行をフェッチします。

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

参照してください[irowsetlocate::getrowsat](/previous-versions/windows/desktop/ms723031)で、 *OLE DB プログラマーズ リファレンス*します。

### <a name="remarks"></a>Remarks

使用する代わりに、カーソル位置からフェッチ、[に](/previous-versions/windows/desktop/ms723031)します。

`IRowsetLocateImpl::GetRowsAt` カーソルの位置は変更されません。

## <a name="getrowsbybookmark"></a> Irowsetlocateimpl::getrowsbybookmark

指定されたブックマークに一致する 1 つまたは複数の行がフェッチされます。

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
[in]対応する*hChapter*パラメーターを[:getrowsbybookmark](/previous-versions/windows/desktop/ms725420)します。

その他のパラメーターでは、次を参照してください。 [:getrowsbybookmark](/previous-versions/windows/desktop/ms725420)で、 *OLE DB プログラマーズ リファレンス*します。

### <a name="remarks"></a>Remarks

ブックマークは、定義した値または OLE DB[標準ブックマーク](/previous-versions/windows/desktop/ms712954)(`DBBMK_FIRST`または`DBBMK_LAST`)。 カーソルの位置は変更されません。

## <a name="hash"></a> Irowsetlocateimpl::hash

ハッシュの指定されたブックマークの値を返します。

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
[in]対応する*hChapter*パラメーターを[IRowsetLocate::Hash](/previous-versions/windows/desktop/ms709697)します。

その他のパラメーターでは、次を参照してください。 [IRowsetLocate::Hash](/previous-versions/windows/desktop/ms709697)で、 *OLE DB プログラマーズ リファレンス*します。

## <a name="rgbookmarks"></a> Irowsetlocateimpl::m_rgbookmarks

ブックマークの配列。

### <a name="syntax"></a>構文

```cpp
CAtlArray<DBROWCOUNT> m_rgBookmarks;
```

## <a name="see-also"></a>関連項目

[OLE DB プロバイダー テンプレート](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB プロバイダー テンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)<br/>
[IRowsetLocate:IRowset](/previous-versions/windows/desktop/ms721190)
[プロバイダーのブックマーク サポート](../../data/oledb/provider-support-for-bookmarks.md)<br/>
[ブックマーク](/previous-versions/windows/desktop/ms709728)