---
title: IRowsetIdentityImpl クラス
ms.date: 11/04/2016
f1_keywords:
- ATL::IRowsetIdentityImpl
- ATL.IRowsetIdentityImpl
- IRowsetIdentityImpl
- IRowsetIdentityImpl.IsSameRow
- ATL.IRowsetIdentityImpl.IsSameRow
- IRowsetIdentityImpl::IsSameRow
- ATL::IRowsetIdentityImpl::IsSameRow
helpviewer_keywords:
- IRowsetIdentityImpl class
- IsSameRow method
ms.assetid: 56821edf-e045-40c8-96bd-231552cd5799
ms.openlocfilehash: 3e8c976fcb23bf41d88d88be3887db4dde52379d
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2020
ms.locfileid: "79545895"
---
# <a name="irowsetidentityimpl-class"></a>IRowsetIdentityImpl クラス

行 id のテストを可能にする OLE DB [IRowsetIdentity](/previous-versions/windows/desktop/ms715913(v=vs.85))インターフェイスを実装します。

## <a name="syntax"></a>構文

```cpp
template <class T, class RowClass = CSimpleRow>
class ATL_NO_VTABLE IRowsetIdentityImpl
   : public IRowsetIdentity
```

### <a name="parameters"></a>パラメーター

*T*<br/>
`IRowsetIdentityImpl`から派生したクラス。

*RowClass*<br/>
`HROW`のストレージユニット。

## <a name="requirements"></a>要件

**ヘッダー:** atldb.h

## <a name="members"></a>メンバー

### <a name="methods"></a>メソッド

|||
|-|-|
|[IsSameRow](#issamerow)|2つの行ハンドルを比較して、同じ行を参照しているかどうかを確認します。|

## <a name="irowsetidentityimplissamerow"></a><a name="issamerow"></a>IRowsetIdentityImpl:: IsSameRow

2つの行ハンドルを比較して、同じ行を参照しているかどうかを確認します。

### <a name="syntax"></a>構文

```cpp
STDMETHOD(IsSameRow )(HROW hThisRow,
   HROW hThatRow);
```

#### <a name="parameters"></a>パラメーター

*OLE DB プログラマーリファレンス*の「 [IRowsetIdentity:: IsSameRow](/previous-versions/windows/desktop/ms719629(v=vs.85)) 」を参照してください。

### <a name="remarks"></a>コメント

行ハンドルを比較するために、このメソッドは `HROW` ハンドルを `RowClass` メンバーにキャストし、ポインターに対して `memcmp` を呼び出します。

## <a name="see-also"></a>参照

[OLE DB プロバイダー テンプレートに関するページ](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB プロバイダー テンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)