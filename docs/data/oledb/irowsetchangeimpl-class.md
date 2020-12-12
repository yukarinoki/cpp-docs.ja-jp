---
description: '詳細情報: IRowsetChangeImpl クラス'
title: IRowsetChangeImpl クラス
ms.date: 11/04/2016
f1_keywords:
- ATL::IRowsetChangeImpl
- IRowsetChangeImpl
- ATL.IRowsetChangeImpl
- ATL.IRowsetChangeImpl.DeleteRows
- ATL::IRowsetChangeImpl::DeleteRows
- IRowsetChangeImpl.DeleteRows
- DeleteRows
- IRowsetChangeImpl::DeleteRows
- ATL.IRowsetChangeImpl.InsertRow
- InsertRow
- IRowsetChangeImpl.InsertRow
- ATL::IRowsetChangeImpl::InsertRow
- IRowsetChangeImpl::InsertRow
- IRowsetChangeImpl::SetData
- ATL.IRowsetChangeImpl.SetData
- IRowsetChangeImpl.SetData
- ATL::IRowsetChangeImpl::SetData
- IRowsetChangeImpl::FlushData
- IRowsetChangeImpl.FlushData
- FlushData
helpviewer_keywords:
- providers, updatable
- updatable providers, immediate update
- IRowsetChangeImpl class
- DeleteRows method
- InsertRow method
- SetData method
- FlushData method
ms.assetid: 1e9fee15-ed9e-4387-af8f-215569beca6c
ms.openlocfilehash: 6536b589cdf936b653d87941fb717e96ff88422c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97287230"
---
# <a name="irowsetchangeimpl-class"></a>IRowsetChangeImpl クラス

OLE DB 仕様の [IRowsetChange](/previous-versions/windows/desktop/ms715790(v=vs.85)) インターフェイスの OLE DB テンプレート実装。

## <a name="syntax"></a>構文

```cpp
template <
   class T,
   class Storage,
   class BaseInterface = IRowsetChange,
   class RowClass = CSimpleRow,
   class MapClass = CAtlMap <RowClass::KeyType, RowClass*>>
class ATL_NO_VTABLE IRowsetChangeImpl : public BaseInterface
```

### <a name="parameters"></a>パラメーター

*T*<br/>
から派生したクラス `IRowsetChangeImpl` 。

*Storage*<br/>
ユーザーレコード。

*BaseInterface*<br/>
インターフェイスの基本クラス (など) `IRowsetChange` 。

*RowClass*<br/>
行ハンドルのストレージ単位。

*MapClass*<br/>
プロバイダーによって保持されているすべての行ハンドルのストレージユニット。

## <a name="requirements"></a>要件

**ヘッダー:** atldb.h

## <a name="members"></a>メンバー

### <a name="interface-methods-used-with-irowsetchange"></a>インターフェイスメソッド (IRowsetChange と共に使用)

| 名前 | 説明 |
|-|-|
|[DeleteRows](#deleterows)|行セットから行を削除します。|
|[InsertRow](#insertrow)|行セットに行を挿入します。|
|[SetData](#setdata)|1つ以上の列にデータ値を設定します。|

### <a name="implementation-method-callback"></a>実装方法 (コールバック)

| 名前 | 説明 |
|-|-|
|[FlushData](#flushdata)|データをストアにコミットするためにプロバイダーによってオーバーライドされます。|

## <a name="remarks"></a>解説

このインターフェイスは、データストアに対する即時書き込み操作を行います。 "Immediate" とは、エンドユーザー (コンシューマーを使用しているユーザー) が変更を加えたときに、その変更が直ちにデータストアに送信されることを意味します (元に戻すことはできません)。

`IRowsetChangeImpl` OLE DB インターフェイスを実装します `IRowsetChange` 。これにより、既存の行の列の値を更新したり、行を削除したり、新しい行を挿入したりできます。

OLE DB テンプレートの実装では、すべての基本メソッド (、、および) がサポートされて `SetData` `InsertRow` `DeleteRows` います。

> [!IMPORTANT]
> プロバイダーを実装する前に、次のドキュメントを読むことを強くお勧めします。

- [更新可能なプロバイダーの作成](../../data/oledb/creating-an-updatable-provider.md)

- *OLE DB プログラマーリファレンス* の第6章

- また、UpdatePV サンプルでのクラスの使用方法についても説明し `RUpdateRowset` ます。 [](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/ATL/OLEDB/Provider/UPDATEPV)

## <a name="irowsetchangeimpldeleterows"></a><a name="deleterows"></a> IRowsetChangeImpl::D eleteRows

行セットから行を削除します。

### <a name="syntax"></a>構文

```cpp
STDMETHOD (DeleteRows )(HCHAPTER /* hReserved */,
   DBCOUNTITEM cRows,
   const HROW rghRows[],
   DBROWSTATUS rgRowStatus[]);
```

#### <a name="parameters"></a>パラメーター

*OLE DB プログラマーリファレンス* の「 [IRowsetChange::D eleterows](/previous-versions/windows/desktop/ms724362(v=vs.85)) 」を参照してください。

## <a name="irowsetchangeimplinsertrow"></a><a name="insertrow"></a> IRowsetChangeImpl:: InsertRow

行セット内の新しい行を作成して初期化します。

### <a name="syntax"></a>構文

```cpp
STDMETHOD (InsertRow )(HCHAPTER /* hReserved */,
   HACCESSOR hAccessor,
   void* pData,
   HROW* phRow);
```

#### <a name="parameters"></a>パラメーター

*OLE DB プログラマーリファレンス* の「 [IRowsetChange:: InsertRow](/previous-versions/windows/desktop/ms716921(v=vs.85)) 」を参照してください。

## <a name="irowsetchangeimplsetdata"></a><a name="setdata"></a> IRowsetChangeImpl:: SetData

1つ以上の列にデータ値を設定します。

### <a name="syntax"></a>構文

```cpp
STDMETHOD (SetData )(HROW hRow,
   HACCESSOR hAccessor,
   void* pSrcData);
```

#### <a name="parameters"></a>パラメーター

*OLE DB プログラマーリファレンス* の「 [IRowsetChange:: SetData](/previous-versions/windows/desktop/ms721232(v=vs.85)) 」を参照してください。

## <a name="irowsetchangeimplflushdata"></a><a name="flushdata"></a> IRowsetChangeImpl:: FlushData

データをストアにコミットするためにプロバイダーによってオーバーライドされます。

### <a name="syntax"></a>構文

```cpp
HRESULT FlushData(HROW hRowToFlush,
   HACCESSOR hAccessorToFlush);
```

#### <a name="parameters"></a>パラメーター

*hRowToFlush*<br/>
からデータの行を処理します。 この行の型は、クラスの *Rowclass* テンプレート引数 (既定では) から決定され `IRowsetImpl` `CSimpleRow` ます。

*hAccessorToFlush*<br/>
からのバインディング情報と型情報を格納するアクセサーへのハンドル `PROVIDER_MAP` (「 [IAccessorImpl](../../data/oledb/iaccessorimpl-class.md)」を参照)。

### <a name="return-value"></a>戻り値

標準の HRESULT です。

## <a name="see-also"></a>関連項目

[OLE DB プロバイダー テンプレートに関するページ](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB プロバイダーテンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)
