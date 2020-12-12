---
description: '詳細情報: IOpenRowsetImpl クラス'
title: IOpenRowsetImpl クラス
ms.date: 11/04/2016
f1_keywords:
- IOpenRowsetImpl
- IOpenRowsetImpl.CreateRowset
- IOpenRowsetImpl::CreateRowset
- OpenRowset
- IOpenRowsetImpl::OpenRowset
- IOpenRowsetImpl.OpenRowset
helpviewer_keywords:
- IOpenRowsetImpl class
- CreateRowset method
- OpenRowset method
ms.assetid: d259cedc-1db4-41cf-bc9f-5030907ab486
ms.openlocfilehash: 4ec7f8ebdab132854172f7e5f4dff7387e46717f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97317429"
---
# <a name="iopenrowsetimpl-class"></a>IOpenRowsetImpl クラス

インターフェイスの実装を提供 `IOpenRowset` します。

## <a name="syntax"></a>構文

```cpp
template <class SessionClass>
class IOpenRowsetImpl : public IOpenRowset
```

### <a name="parameters"></a>パラメーター

*SessionClass*<br/>
から派生したクラス `IOpenRowsetImpl` 。

## <a name="requirements"></a>要件

**ヘッダー:** atldb.h

## <a name="members"></a>メンバー

### <a name="methods"></a>メソッド

| 名前 | 説明 |
|-|-|
|[CreateRowset](#createrowset)|行セットオブジェクトを作成します。 ユーザーによって直接呼び出されることはありません。|
|[OpenRowset](#openrowset)|を開き、1つのベーステーブルまたはインデックスのすべての行を含む行セットを返します。 (ATLDB.H ではありません。始め|

## <a name="remarks"></a>解説

セッションオブジェクトの場合、 [IOpenRowset](/previous-versions/windows/desktop/ms716946(v=vs.85)) インターフェイスは必須です。 これにより、1つのベーステーブルまたはインデックスのすべての行を含む行セットが開かれて返されます。

## <a name="iopenrowsetimplcreaterowset"></a><a name="createrowset"></a> IOpenRowsetImpl:: CreateRowset

行セットオブジェクトを作成します。 ユーザーによって直接呼び出されることはありません。 *OLE DB プログラマーリファレンス* の「 [IOpenRowset:: OpenRowset](/previous-versions/windows/desktop/ms716724(v=vs.85)) 」を参照してください。

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
ユーザーの行セットクラスを表すテンプレートクラスメンバー。 通常、ウィザードによって生成されます。

*pRowsetObj*<br/>
入出力行セットオブジェクトへのポインター。 通常、このパラメーターは使用されませんが、COM オブジェクトに渡す前に行セットに対してより多くの作業を実行する必要がある場合に使用できます。 *PRowsetObj* の有効期間は *ppRowset* によって制限されます。

その他のパラメーターについては、 *OLE DB プログラマーリファレンス* の「 [IOpenRowset:: OpenRowset](/previous-versions/windows/desktop/ms716724(v=vs.85)) 」を参照してください。

## <a name="iopenrowsetimplopenrowset"></a><a name="openrowset"></a> IOpenRowsetImpl:: OpenRowset

を開き、1つのベーステーブルまたはインデックスのすべての行を含む行セットを返します。

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

*OLE DB プログラマーリファレンス* の「 [IOpenRowset:: OpenRowset](/previous-versions/windows/desktop/ms716724(v=vs.85)) 」を参照してください。

### <a name="remarks"></a>解説

このメソッドは ATLDB.H に見つかりません。 これは、プロバイダーを作成するときに ATL オブジェクトウィザードによって作成されます。

## <a name="see-also"></a>関連項目

[OLE DB プロバイダー テンプレートに関するページ](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB プロバイダーテンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)
