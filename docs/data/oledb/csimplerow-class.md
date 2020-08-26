---
title: CSimpleRow クラス
ms.date: 11/04/2016
f1_keywords:
- CSimpleRow
- ATL::CSimpleRow
- ATL.CSimpleRow
- CSimpleRow::AddRefRow
- AddRefRow
- ATL.CSimpleRow.AddRefRow
- ATL::CSimpleRow::AddRefRow
- CSimpleRow.AddRefRow
- CSimpleRow.Compare
- CSimpleRow::Compare
- ATL::CSimpleRow::CSimpleRow
- CSimpleRow.CSimpleRow
- ATL.CSimpleRow.CSimpleRow
- CSimpleRow::CSimpleRow
- ATL::CSimpleRow::ReleaseRow
- CSimpleRow::ReleaseRow
- ReleaseRow
- CSimpleRow.ReleaseRow
- ATL.CSimpleRow.ReleaseRow
- CSimpleRow.m_dwRef
- CSimpleRow::m_dwRef
- CSimpleRow::m_iRowset
- CSimpleRow.m_iRowset
helpviewer_keywords:
- CSimpleRow class
- AddRefRow method
- Compare method
- CSimpleRow class, constructor
- ReleaseRow method
- m_dwRef
- m_iRowset
ms.assetid: 06d9621d-60cc-4508-8b0c-528d1b1a809b
ms.openlocfilehash: c332fc0c653bbde3a69421b8166d4d099eaeeaf4
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88841078"
---
# <a name="csimplerow-class"></a>CSimpleRow クラス

[IRowsetImpl](../../data/oledb/irowsetimpl-class.md)クラスで使用される行ハンドルの既定の実装を提供します。

## <a name="syntax"></a>構文

```cpp
class CSimpleRow
```

## <a name="requirements"></a>必要条件

**ヘッダー:** atldb.h

## <a name="members"></a>メンバー

### <a name="methods"></a>メソッド

| 名前 | 説明 |
|-|-|
|[AddRefRow](#addrefrow)|既存の行ハンドルの参照カウントをインクリメントします。|
|[比較](#compare)|2つの行を比較して、同じ行インスタンスを参照しているかどうかを確認します。|
|[CSimpleRow](#csimplerow)|コンストラクターです。|
|[ReleaseRow](#releaserow)|行を解放します。|

### <a name="data-members"></a>データ メンバー

| 名前 | 説明 |
|-|-|
|[m_dwRef](#dwref)|既存の行ハンドルに対する参照カウント。|
|[m_iRowset](#irowset)|カーソルを表す行セットへのインデックス。|

## <a name="remarks"></a>解説

行ハンドルは、論理的には結果行の一意のタグです。 `IRowsetImpl``CSimpleRow` [IRowsetImpl:: GetNextRows](../../data/oledb/irowsetimpl-getnextrows.md)で要求されたすべての行に対して新しいを作成します。 `CSimpleRow` は、の既定のテンプレート引数であるため、行ハンドルの独自の実装に置き換えることもでき `IRowsetImpl` ます。 このクラスを置き換える唯一の要件は、置換クラスに **LONG**型の1つのパラメーターを受け取るコンストラクターを提供させることです。

## <a name="csimplerowaddrefrow"></a><a name="addrefrow"></a> CSimpleRow:: AddRefRow

スレッドセーフな方法で、既存の行ハンドルに参照カウントを追加します。

### <a name="syntax"></a>構文

```cpp
DWORD AddRefRow();
```

## <a name="csimplerowcompare"></a><a name="compare"></a> CSimpleRow:: Compare

2つの行を比較して、同じ行インスタンスを参照しているかどうかを確認します。

### <a name="syntax"></a>構文

```cpp
HRESULT Compare(CSimpleRow* pRow);
```

#### <a name="parameters"></a>パラメーター

*pRow*<br/>
`CSimpleRow` オブジェクトを指すポインターです。

### <a name="return-value"></a>戻り値

2つの行が同じ行インスタンスであるか S_FALSE であることを示す HRESULT 値 (通常は S_OK)。2つの行が異なることを示します。 その他の可能性のある戻り値については、 *OLE DB プログラマーリファレンス*の「 [IRowsetIdentity:: IsSameRow](/previous-versions/windows/desktop/ms719629(v=vs.85)) 」を参照してください。

## <a name="csimplerowcsimplerow"></a><a name="csimplerow"></a> CSimpleRow:: CSimpleRow

コンストラクターです。

### <a name="syntax"></a>構文

```cpp
CSimpleRow(DBCOUNTITEM iRowsetCur);
```

#### <a name="parameters"></a>パラメーター

*iRowsetCur*<br/>
から現在の行セットへのインデックス。

### <a name="remarks"></a>解説

[M_iRowset](../../data/oledb/csimplerow-m-irowset.md)を*iRowsetCur*に設定します。

## <a name="csimplerowreleaserow"></a><a name="releaserow"></a> CSimpleRow:: ReleaseRow

スレッドセーフな方法で行を解放します。

### <a name="syntax"></a>構文

```cpp
DWORD ReleaseRow();
```

## <a name="csimplerowm_dwref"></a><a name="dwref"></a> CSimpleRow:: m_dwRef

既存の行ハンドルに対する参照カウント。

### <a name="syntax"></a>構文

```cpp
DWORD m_dwRef;
```

## <a name="csimplerowm_irowset"></a><a name="irowset"></a> CSimpleRow:: m_iRowset

カーソルを表す行セットへのインデックス。

### <a name="syntax"></a>構文

```cpp
KeyType m_iRowset;
```

## <a name="see-also"></a>関連項目

[OLE DB プロバイダー テンプレートに関するページ](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB プロバイダーテンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)<br/>
[IRowsetImpl クラス](../../data/oledb/irowsetimpl-class.md)
