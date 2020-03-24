---
title: CBulkRowset クラス
ms.date: 11/04/2016
f1_keywords:
- ATL::CBulkRowset
- ATL.CBulkRowset
- ATL::CBulkRowset<TAccessor>
- CBulkRowset
- ATL.CBulkRowset<TAccessor>
- CBulkRowset::AddRefRows
- CBulkRowset.AddRefRows
- ATL.CBulkRowset<TAccessor>.AddRefRows
- ATL::CBulkRowset::AddRefRows
- CBulkRowset<TAccessor>::AddRefRows
- ATL.CBulkRowset.AddRefRows
- ATL::CBulkRowset<TAccessor>::AddRefRows
- ATL.CBulkRowset<TAccessor>.CBulkRowset
- ATL::CBulkRowset::CBulkRowset
- CBulkRowset.CBulkRowset
- CBulkRowset::CBulkRowset
- ATL.CBulkRowset.CBulkRowset
- ATL::CBulkRowset<TAccessor>::CBulkRowset
- CBulkRowset<TAccessor>::CBulkRowset
- ATL.CBulkRowset.MoveFirst
- CBulkRowset<TAccessor>.MoveFirst
- ATL.CBulkRowset<TAccessor>.MoveFirst
- ATL::CBulkRowset::MoveFirst
- ATL::CBulkRowset<TAccessor>::MoveFirst
- CBulkRowset::MoveFirst
- CBulkRowset<TAccessor>::MoveFirst
- CBulkRowset.MoveFirst
- CBulkRowset.MoveLast
- ATL.CBulkRowset.MoveLast
- ATL::CBulkRowset<TAccessor>::MoveLast
- CBulkRowset::MoveLast
- CBulkRowset<TAccessor>.MoveLast
- ATL::CBulkRowset::MoveLast
- ATL.CBulkRowset<TAccessor>.MoveLast
- CBulkRowset<TAccessor>::MoveLast
- ATL.CBulkRowset<TAccessor>.MoveNext
- ATL::CBulkRowset::MoveNext
- CBulkRowset::MoveNext
- ATL.CBulkRowset.MoveNext
- CBulkRowset.MoveNext
- ATL::CBulkRowset<TAccessor>::MoveNext
- CBulkRowset<TAccessor>.MoveNext
- CBulkRowset<TAccessor>::MoveNext
- CBulkRowset::MovePrev
- CBulkRowset<TAccessor>::MovePrev
- ATL::CBulkRowset<TAccessor>::MovePrev
- CBulkRowset<TAccessor>.MovePrev
- ATL::CBulkRowset::MovePrev
- CBulkRowset.MovePrev
- ATL.CBulkRowset.MovePrev
- ATL.CBulkRowset<TAccessor>.MovePrev
- CBulkRowset<TAccessor>::MoveToBookmark
- CBulkRowset.MoveToBookmark
- ATL.CBulkRowset.MoveToBookmark
- CBulkRowset::MoveToBookmark
- ATL::CBulkRowset<TAccessor>::MoveToBookmark
- ATL::CBulkRowset::MoveToBookmark
- CBulkRowset.MoveToRatio
- ATL::CBulkRowset::MoveToRatio
- CBulkRowset::MoveToRatio
- ATL.CBulkRowset<TAccessor>.MoveToRatio
- ATL::CBulkRowset<TAccessor>::MoveToRatio
- ATL.CBulkRowset.MoveToRatio
- CBulkRowset<TAccessor>::MoveToRatio
- ATL.CBulkRowset<TAccessor>.ReleaseRows
- ATL::CBulkRowset<TAccessor>::ReleaseRows
- ATL.CBulkRowset.ReleaseRows
- CBulkRowset<TAccessor>::ReleaseRows
- ATL::CBulkRowset::ReleaseRows
- CBulkRowset::ReleaseRows
- CBulkRowset.ReleaseRows
- ATL.CBulkRowset.SetRows
- CBulkRowset::SetRows
- CBulkRowset<TAccessor>.SetRows
- ATL.CBulkRowset<TAccessor>.SetRows
- CBulkRowset<TAccessor>::SetRows
- ATL::CBulkRowset<TAccessor>::SetRows
- ATL::CBulkRowset::SetRows
- CBulkRowset.SetRows
- SetRows
helpviewer_keywords:
- CBulkRowset class
- AddRefRows method
- CBulkRowset class, constructor
- MoveFirst method
- MoveLast method
- MoveNext method
- MovePrev method
- MoveToBookmark method
- MoveToRatio method
- ReleaseRows method
- SetRows method
ms.assetid: c6bde426-c543-4022-a98a-9519d9e2ae59
ms.openlocfilehash: e66a183c7bbafa16b3aefea8da1472255b507468
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80212124"
---
# <a name="cbulkrowset-class"></a>CBulkRowset クラス

1回の呼び出しで複数の行ハンドルを取得することにより、データを一括処理する行をフェッチして操作します。

## <a name="syntax"></a>構文

```cpp
template <class TAccessor>
class CBulkRowset : public CRowset<TAccessor>
```

### <a name="parameters"></a>パラメーター

*TAccessor*<br/>
アクセサークラス。

## <a name="requirements"></a>必要条件

**ヘッダー:** atldbcli.h

## <a name="members"></a>メンバー

### <a name="methods"></a>メソッド

|||
|-|-|
|[AddRefRows](#addrefrows)|参照カウントをインクリメントします。|
|[CBulkRowset](#cbulkrowset)|コンストラクターです。|
|[MoveFirst](#movefirst)|データの最初の行を取得し、必要に応じて新しい一括フェッチを実行します。|
|[MoveLast](#movelast)|最後の行に移動します。|
|[MoveNext](#movenext)|次のデータ行を取得します。|
|[MovePrev](#moveprev)|前の行に移動します。|
|[MoveToBookmark](#movetobookmark)|ブックマークによってマークされた行、またはそのブックマークの指定したオフセット位置にある行をフェッチします。|
|[MoveToRatio](#movetoratio)|行セット内の小数位置から始まる行をフェッチします。|
|[ReleaseRows](#releaserows)|現在の行 (`m_nCurrentRow`) をゼロに設定し、すべての行を解放します。|
|[SetRows](#setrows)|1回の呼び出しで取得される行ハンドルの数を設定します。|

## <a name="example"></a>例

`CBulkRowset` クラスの使用例を次に示します。

[!code-cpp[NVC_OLEDB_Consumer#1](../../data/oledb/codesnippet/cpp/cbulkrowset-class_1.cpp)]

## <a name="cbulkrowsetaddrefrows"></a><a name="addrefrows"></a>CBulkRowset:: AddRefRows

[IRowset:: AddRefRows](/previous-versions/windows/desktop/ms719619(v=vs.85))を呼び出して、一括行セットから現在取得されているすべての行の参照カウントをインクリメントします。

### <a name="syntax"></a>構文

```cpp
HRESULT AddRefRows() throw();
```

### <a name="return-value"></a>戻り値

標準の HRESULT です。

## <a name="cbulkrowsetcbulkrowset"></a><a name="cbulkrowset"></a>CBulkRowset:: CBulkRowset

新しい `CBulkRowset` オブジェクトを作成し、既定の行数を10に設定します。

### <a name="syntax"></a>構文

```cpp
CBulkRowset();
```

## <a name="cbulkrowsetmovefirst"></a><a name="movefirst"></a>CBulkRowset:: MoveFirst

データの最初の行を取得します。

### <a name="syntax"></a>構文

```cpp
HRESULT MoveFirst() throw();
```

### <a name="return-value"></a>戻り値

標準の HRESULT です。

## <a name="cbulkrowsetmovelast"></a><a name="movelast"></a>CBulkRowset:: MoveLast

最後の行に移動します。

### <a name="syntax"></a>構文

```cpp
HRESULT MoveLast() throw();
```

### <a name="return-value"></a>戻り値

標準の HRESULT です。

## <a name="cbulkrowsetmovenext"></a><a name="movenext"></a>CBulkRowset:: MoveNext

次のデータ行を取得します。

### <a name="syntax"></a>構文

```cpp
HRESULT MoveNext() throw();
```

### <a name="return-value"></a>戻り値

標準の HRESULT です。 行セットの末尾に到達すると、DB_S_ENDOFROWSET を返します。

## <a name="cbulkrowsetmoveprev"></a><a name="moveprev"></a>CBulkRowset:: MovePrev

前の行に移動します。

### <a name="syntax"></a>構文

```cpp
HRESULT MovePrev() throw();
```

### <a name="return-value"></a>戻り値

標準の HRESULT です。

## <a name="cbulkrowsetmovetobookmark"></a><a name="movetobookmark"></a>CBulkRowset:: MoveToBookmark

ブックマークまたは指定されたオフセット (*lSkip*) にある行を、そのブックマークからフェッチします。

### <a name="syntax"></a>構文

```cpp
HRESULT MoveToBookmark(const CBookmarkBase& bookmark,
   DBCOUNTITEM lSkip = 0) throw();
```

#### <a name="parameters"></a>パラメーター

*ブックマーク*<br/>
からデータをフェッチする場所を示すブックマーク。

*lSkip*<br/>
からブックマークから対象の行までの行数。 *LSkip*が0の場合、最初にフェッチされた行がブックマークが付けられた行になります。 *LSkip*が1の場合、最初にフェッチされる行は、ブックマークが付けられた行の後の行になります。 *LSkip*が-1 の場合、最初にフェッチされる行は、ブックマークが付けられた行の前の行になります。

### <a name="return-value"></a>戻り値

*OLE DB プログラマーリファレンス*の「 [IRowset:: GetData](/previous-versions/windows/desktop/ms716988(v=vs.85)) 」を参照してください。

## <a name="cbulkrowsetmovetoratio"></a><a name="movetoratio"></a>CBulkRowset:: MoveToRatio

行セット内の小数位置から始まる行をフェッチします。

### <a name="syntax"></a>構文

```cpp
HRESULT MoveToRatio(DBCOUNTITEM nNumerator,
   DBCOUNTITEM nDenominator)throw();
```

#### <a name="parameters"></a>パラメーター

*nNumerator*<br/>
からデータのフェッチ元となる小数点位置を決定するために使用される分子。

*nDenominator*<br/>
からデータのフェッチ元となる小数点位置を決定するために使用する分母。

### <a name="return-value"></a>戻り値

標準の HRESULT です。

### <a name="remarks"></a>解説

`MoveToRatio` は、次の式に従って、おおよその行をフェッチします。

`(nNumerator *  RowsetSize ) / nDenominator`

ここで `RowsetSize` には行セットのサイズを指定します。 この数式の精度は、特定のプロバイダーによって異なります。 詳細については、 *OLE DB プログラマーリファレンス*の「 [IRowsetScroll:: GetRowsAtRatio](/previous-versions/windows/desktop/ms709602(v=vs.85)) 」を参照してください。

## <a name="cbulkrowsetreleaserows"></a><a name="releaserows"></a>CBulkRowset:: ReleaseRows

[IRowset:: ReleaseRows](/previous-versions/windows/desktop/ms719771(v=vs.85))を呼び出して、一括行セットから現在取得されているすべての行の参照カウントをデクリメントします。

### <a name="syntax"></a>構文

```cpp
HRESULT ReleaseRows() throw();
```

### <a name="return-value"></a>戻り値

標準の HRESULT です。

## <a name="cbulkrowsetsetrows"></a><a name="setrows"></a>CBulkRowset:: SetRows

各呼び出しによって取得される行ハンドルの数を設定します。

### <a name="syntax"></a>構文

```cpp
void SetRows(DBROWCOUNT nRows) throw();
```

#### <a name="parameters"></a>パラメーター

*nRows*<br/>
から行セットの新しいサイズ (行の数)。

### <a name="remarks"></a>解説

この関数を呼び出す場合は、行セットを開く前ににする必要があります。

## <a name="see-also"></a>参照

[OLE DB コンシューマー テンプレートに関するページ](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB コンシューマー テンプレート リファレンス](../../data/oledb/ole-db-consumer-templates-reference.md)
