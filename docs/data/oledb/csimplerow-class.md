---
title: CSimpleRow クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
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
- CSimpleRow
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
dev_langs:
- C++
helpviewer_keywords:
- CSimpleRow class
- AddRefRow method
- Compare method
- CSimpleRow class, constructor
- ReleaseRow method
- m_dwRef
- m_iRowset
ms.assetid: 06d9621d-60cc-4508-8b0c-528d1b1a809b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: d5ceb07577386f4b3fc9389cf9103fba4036b591
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2018
ms.locfileid: "50076791"
---
# <a name="csimplerow-class"></a>CSimpleRow クラス

使用されている行ハンドルの既定の実装を提供します、 [IRowsetImpl](../../data/oledb/irowsetimpl-class.md)クラス。

## <a name="syntax"></a>構文

```cpp
class CSimpleRow
```

## <a name="requirements"></a>必要条件

**ヘッダー:** atldb.h

## <a name="members"></a>メンバー

### <a name="methods"></a>メソッド

|||
|-|-|
|[AddRefRow](#addrefrow)|既存の行ハンドルには、参照カウントを追加します。|
|[Compare](#compare)|同じ行インスタンスを参照しているかを確認する 2 つの行を比較します。|
|[CSimpleRow](#csimplerow)|コンストラクターです。|
|[ReleaseRow](#releaserow)|行を解放します。|

### <a name="data-members"></a>データ メンバー

|||
|-|-|
|[m_dwRef](#dwref)|既存の行ハンドルの参照カウント。|
|[m_iRowset](#irowset)|カーソルを表す行セットのインデックスです。|

## <a name="remarks"></a>Remarks

行ハンドルは、論理的に結果の行の一意のタグです。 `IRowsetImpl` 新たに作成`CSimpleRow`で要求されたすべての行の[irowsetimpl::getnextrows](../../data/oledb/irowsetimpl-getnextrows.md)します。 `CSimpleRow` 既定のテンプレート引数にも、行ハンドルの独自の実装に置き換えることが`IRowsetImpl`します。 このクラスを置換する唯一の要件は、型の 1 つのパラメーターを受け取るコンス トラクターを提供する置換クラスを用意する**長い**します。

## <a name="addrefrow"></a> Csimplerow::addrefrow

既存の行ハンドルをスレッド セーフ方式で参照カウントを追加します。

### <a name="syntax"></a>構文

```cpp
DWORD AddRefRow();
```

## <a name="compare"></a> Csimplerow::compare

同じ行インスタンスを参照しているかを確認する 2 つの行を比較します。

### <a name="syntax"></a>構文

```cpp
HRESULT Compare(CSimpleRow* pRow);
```

#### <a name="parameters"></a>パラメーター

*pRow*<br/>
`CSimpleRow` オブジェクトへのポインター。

### <a name="return-value"></a>戻り値

HRESULT 値、通常は S_OK を示すは、2 つの行は、同じ行インスタンスまたは 2 つの行を示す S_FALSE は異なります。 参照してください[IRowsetIdentity::IsSameRow](/previous-versions/windows/desktop/ms719629)で、 *OLE DB プログラマーズ リファレンス*の他の戻り値。

## <a name="csimplerow"></a> Csimplerow::csimplerow

コンストラクターです。

### <a name="syntax"></a>構文

```cpp
CSimpleRow(DBCOUNTITEM iRowsetCur);
```

#### <a name="parameters"></a>パラメーター

*iRowsetCur*<br/>
[in]現在の行セットのインデックスです。

### <a name="remarks"></a>Remarks

セット[m_iRowset](../../data/oledb/csimplerow-m-irowset.md)に*iRowsetCur*します。

## <a name="releaserow"></a> Csimplerow::releaserow

スレッド セーフ方式で行を解放します。

### <a name="syntax"></a>構文

```cpp
DWORD ReleaseRow();
```

## <a name="dwref"></a> Csimplerow::m_dwref

既存の行ハンドルの参照カウント。

### <a name="syntax"></a>構文

```cpp
DWORD m_dwRef;
```

## <a name="irowset"></a> Csimplerow::m_irowset

カーソルを表す行セットのインデックスです。

### <a name="syntax"></a>構文

```cpp
KeyType m_iRowset;
```

## <a name="see-also"></a>関連項目

[OLE DB プロバイダー テンプレート](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB プロバイダー テンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)<br/>
[IRowsetImpl クラス](../../data/oledb/irowsetimpl-class.md)