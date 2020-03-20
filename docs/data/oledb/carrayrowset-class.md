---
title: CArrayRowset クラス
ms.date: 11/04/2016
f1_keywords:
- ATL.CArrayRowset<TAccessor>
- ATL.CArrayRowset
- CArrayRowset
- ATL::CArrayRowset
- ATL::CArrayRowset<TAccessor>
- ATL::CArrayRowset::CArrayRowset
- CArrayRowset.CArrayRowset
- ATL.CArrayRowset.CArrayRowset
- ATL.CArrayRowset<TAccessor>.CArrayRowset
- CArrayRowset::CArrayRowset
- CArrayRowset<TAccessor>::CArrayRowset
- ATL::CArrayRowset<TAccessor>::CArrayRowset
- CArrayRowset<TAccessor>.Snapshot
- ATL::CArrayRowset::Snapshot
- Snapshot
- CArrayRowset<TAccessor>::Snapshot
- ATL.CArrayRowset.Snapshot
- ATL.CArrayRowset<TAccessor>.Snapshot
- ATL::CArrayRowset<TAccessor>::Snapshot
- CArrayRowset::Snapshot
- CArrayRowset.Snapshot
- CArrayRowset::operator[]
- CArrayRowset.operator[]
- ATL::CArrayRowset::m_nRowsRead
- ATL::CArrayRowset<TAccessor>::m_nRowsRead
- CArrayRowset<TAccessor>::m_nRowsRead
- ATL.CArrayRowset<TAccessor>.m_nRowsRead
- CArrayRowset.m_nRowsRead
- m_nRowsRead
- ATL.CArrayRowset.m_nRowsRead
- CArrayRowset::m_nRowsRead
helpviewer_keywords:
- CArrayRowset class
- CArrayRowset class, constructor
- Snapshot method
- operator [], arrays
- '[] operator'
- operator[], arrays
- m_nRowsRead
ms.assetid: 511427e1-73ca-4fd8-9ba1-ae9463557cb6
ms.openlocfilehash: 66b7607eb28392196f6b7d3790aee976a861f2b6
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2020
ms.locfileid: "79545613"
---
# <a name="carrayrowset-class"></a>CArrayRowset クラス

配列構文を使用して、行セットの要素にアクセスします。

## <a name="syntax"></a>構文

```cpp
template < class TAccessor >
class CArrayRowset :
   public CVirtualBuffer <TAccessor>,
   protected CBulkRowset <TAccessor>
```

### <a name="parameters"></a>パラメーター

*TAccessor*<br/>
行セットで使用するアクセサークラスの型。

## <a name="requirements"></a>要件

**ヘッダー:** atldbcli.h

## <a name="members"></a>メンバー

### <a name="methods"></a>メソッド

|||
|-|-|
|[CArrayRowset](#carrayrowset)|コンストラクターです。|
|[スナップショット](#snapshot)|行セット全体をメモリに読み込みます。|

### <a name="operators"></a>演算子

|||
|-|-|
|[Operator&#91;&#93;](#operator)|行セットの要素にアクセスします。|

### <a name="data-members"></a>データ メンバー

|||
|-|-|
|[CArrayRowset::m_nRowsRead](#nrowsread)|既に読み取られた行の数。|

## <a name="carrayrowsetcarrayrowset"></a><a name="carrayrowset"></a>CArrayRowset:: CArrayRowset

新しい `CArrayRowset` オブジェクトを作成します。

### <a name="syntax"></a>構文

```cpp
CArrayRowset(int nMax = 100000);
```

#### <a name="parameters"></a>パラメーター

*N1 日*<br/>
から行セット内の行の最大数。

## <a name="carrayrowsetsnapshot"></a><a name="snapshot"></a>CArrayRowset:: Snapshot

行セット全体をメモリに読み込み、そのイメージまたはスナップショットを作成します。

### <a name="syntax"></a>構文

```cpp
HRESULT Snapshot() throw();
```

## <a name="carrayrowsetoperator"></a><a name="operator"></a>CArrayRowset:: operator

行セット内の行にアクセスするための配列のような構文を提供します。

### <a name="syntax"></a>構文

```cpp
TAccessor & operator[](int nrow);
```

#### <a name="parameters"></a>パラメーター

*TAccessor*<br/>
行セットに格納されているアクセサーの種類を指定するテンプレートパラメーター。

*nRow*<br/>
[in] (配列) にアクセスする、行の数です。

### <a name="return-value"></a>戻り値

要求された行の内容。

### <a name="remarks"></a>コメント

*Nrow*が行セット内の行の数を超えると、例外がスローされます。

## <a name="carrayrowsetm_nrowsread"></a><a name="nrowsread"></a>CArrayRowset:: m_nRowsRead

既に読み取られた行セット内の行の数を格納します。

### <a name="syntax"></a>構文

```cpp
ULONG m_nRowsRead;
```

## <a name="see-also"></a>参照

[OLE DB コンシューマー テンプレートに関するページ](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB コンシューマー テンプレート リファレンス](../../data/oledb/ole-db-consumer-templates-reference.md)<br/>
[CRowset クラス](../../data/oledb/crowset-class.md)