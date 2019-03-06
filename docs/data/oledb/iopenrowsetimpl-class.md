---
title: IOpenRowsetImpl クラス
ms.date: 11/04/2016
f1_keywords:
- IOpenRowsetImpl
- IOpenRowsetImpl.CreateRowset
- IOpenRowsetImpl::CreateRowset
- CreateRowset
- OpenRowset
- IOpenRowsetImpl::OpenRowset
- IOpenRowsetImpl.OpenRowset
helpviewer_keywords:
- IOpenRowsetImpl class
- CreateRowset method
- OpenRowset method
ms.assetid: d259cedc-1db4-41cf-bc9f-5030907ab486
ms.openlocfilehash: 3d4f778f560b55f22c1c54185bea79af07949ceb
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57422757"
---
# <a name="iopenrowsetimpl-class"></a>IOpenRowsetImpl クラス

実装を提供、`IOpenRowset`インターフェイス。

## <a name="syntax"></a>構文

```cpp
template <class SessionClass>
class IOpenRowsetImpl : public IOpenRowset
```

### <a name="parameters"></a>パラメーター

*SessionClass*<br/>
派生したクラス、`IOpenRowsetImpl`します。

## <a name="requirements"></a>必要条件

**ヘッダー:** atldb.h

## <a name="members"></a>メンバー

### <a name="methods"></a>メソッド

|||
|-|-|
|[CreateRowset](#createrowset)|行セット オブジェクトを作成します。 ユーザーが直接呼び出されません。|
|[OpenRowset](#openrowset)|開き、1 つのベース テーブルまたはインデックスからすべての行が含まれる行セットを返します。 (ATLDB ではないです。H)|

## <a name="remarks"></a>Remarks

[IOpenRowset](/previous-versions/windows/desktop/ms716946(v=vs.85))セッション オブジェクトの必須インターフェイスです。 これによりが表示され、1 つのベース テーブルまたはインデックスからすべての行が含まれる行セットを返します。

## <a name="createrowset"></a> IOpenRowsetImpl::CreateRowset

行セット オブジェクトを作成します。 ユーザーが直接呼び出されません。 参照してください[iopenrowset::openrowset](/previous-versions/windows/desktop/ms716724(v=vs.85))で、 *OLE DB プログラマーズ リファレンス。*

### <a name="syntax"></a>構文

```cpp
template template <class RowsetClass>
HRESULT CreateRowset(IUnknown* pUnkOuter,
   DBID* pTableID,
   DBID* pIndexID,
   REFIID riid,
   ULONG cPropertySets,
   DBPROPSET rgPropertySets[],
   IUnknown** ppRowset,
   RowsetClass*& pRowsetObj);
```

#### <a name="parameters"></a>パラメーター

*RowsetClass*<br/>
ユーザーの行セット クラスを表すテンプレート クラスのメンバー。 通常、ウィザードによって生成されます。

*pRowsetObj*<br/>
[out]行セット オブジェクトへのポインター。 通常、このパラメーターは使用されませんが COM オブジェクトに渡す前に、行セットに対してより多くの作業を実行する必要がある場合に使用できます。 有効期間*pRowsetObj*連結された*ppRowset*します。

その他のパラメーターでは、次を参照してください。 [iopenrowset::openrowset](/previous-versions/windows/desktop/ms716724(v=vs.85))で、 *OLE DB プログラマーズ リファレンス。*

## <a name="openrowset"></a> IOpenRowsetImpl::OpenRowset

開き、1 つのベース テーブルまたはインデックスからすべての行が含まれる行セットを返します。

### <a name="syntax"></a>構文

```cpp
HRESULT OpenRowset(IUnknown* pUnkOuter,
   DBID* pTableID,
   DBID* pIndexID,
   REFIID riid,
   ULONG cPropertySets,
   DBPROPSET rgPropertySets[],
   IUnknown** ppRowset);
```

#### <a name="parameters"></a>パラメーター

参照してください[iopenrowset::openrowset](/previous-versions/windows/desktop/ms716724(v=vs.85))で、 *OLE DB プログラマーズ リファレンス*します。

### <a name="remarks"></a>Remarks

ATLDB でこのメソッドが見つかりませんでした。H. プロバイダーを作成するときに、ATL オブジェクト ウィザードによって作成されます。

## <a name="see-also"></a>関連項目

[OLE DB プロバイダー テンプレート](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB プロバイダー テンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)