---
title: IDBSchemaRowsetImpl クラス
ms.date: 11/04/2016
f1_keywords:
- IDBSchemaRowsetImpl
- CheckRestrictions
- IDBSchemaRowsetImpl::CheckRestrictions
- IDBSchemaRowsetImpl.CheckRestrictions
- IDBSchemaRowsetImpl::CreateSchemaRowset
- ATL::IDBSchemaRowsetImpl::CreateSchemaRowset
- CreateSchemaRowset
- IDBSchemaRowsetImpl.CreateSchemaRowset
- ATL.IDBSchemaRowsetImpl.CreateSchemaRowset
- IDBSchemaRowsetImpl::SetRestrictions
- SetRestrictions
- IDBSchemaRowsetImpl.SetRestrictions
- ATL::IDBSchemaRowsetImpl::GetRowset
- ATL.IDBSchemaRowsetImpl.GetRowset
- IDBSchemaRowsetImpl<SessionClass>::GetRowset
- IDBSchemaRowsetImpl.GetRowset
- IDBSchemaRowsetImpl::GetRowset
- ATL::IDBSchemaRowsetImpl<SessionClass>::GetRowset
- GetRowset
- ATL::IDBSchemaRowsetImpl::GetSchemas
- GetSchemas
- IDBSchemaRowsetImpl<SessionClass>::GetSchemas
- ATL.IDBSchemaRowsetImpl.GetSchemas
- ATL::IDBSchemaRowsetImpl<SessionClass>::GetSchemas
- IDBSchemaRowsetImpl.GetSchemas
- IDBSchemaRowsetImpl::GetSchemas
helpviewer_keywords:
- IDBSchemaRowsetImpl class
- CheckRestrictions method
- CreateSchemaRowset method
- SetRestrictions method
- GetRowset method
- GetSchemas method
ms.assetid: bd7bf0d7-a1c6-4afa-88e3-cfdbdf560703
ms.openlocfilehash: f6af0f61ca425a2a1fba98b4041a92163e2f1d4e
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80210627"
---
# <a name="idbschemarowsetimpl-class"></a>IDBSchemaRowsetImpl クラス

スキーマ行セットの実装を提供します。

## <a name="syntax"></a>構文

```cpp
template <class SessionClass>
class ATL_NO_VTABLE IDBSchemaRowsetImpl : public IDBSchemaRowset
```

### <a name="parameters"></a>パラメーター

*SessionClass*<br/>
`IDBSchemaRowsetImpl` が継承されるクラス。 通常、このクラスは、ユーザーのセッション クラスです。

## <a name="requirements"></a>必要条件

**ヘッダー:** atldb.h

## <a name="members"></a>メンバー

### <a name="methods"></a>メソッド

|||
|-|-|
|[CheckRestrictions](#checkrestrictions)|スキーマ行セットに対して制限の妥当性をチェックします。|
|[CreateSchemaRowset](#createschemarowset)|テンプレート パラメーターで指定されたオブジェクトの COM オブジェクトの作成関数を実装します。|
|[SetRestrictions](#setrestrictions)|特定のスキーマ行セットでサポートする制限を指定します。|

### <a name="interface-methods"></a>インターフェイス メソッド

|||
|-|-|
|[GetRowset](#getrowset)|スキーマ行セットを返します。|
|[GetSchemas](#getschemas)|[IDBSchemaRowsetImpl::GetRowset](../../data/oledb/idbschemarowsetimpl-getrowset.md)でアクセスできるスキーマ行セットの一覧を返します。|

## <a name="remarks"></a>解説

このクラスは、 [IDBSchemaRowset](/previous-versions/windows/desktop/ms713686(v=vs.85)) インターフェイスと、テンプレート化された作成関数 [CreateSchemaRowset](../../data/oledb/idbschemarowsetimpl-createschemarowset.md)を実装します。

OLE DB はスキーマ行セットを使用して、プロバイダーのデータに関するデータを返します。 このようなデータは、多くの場合、"メタデータ" と呼ばれます。 既定では、プロバイダーは常に `DBSCHEMA_TABLES`、`DBSCHEMA_COLUMNS`、および `DBSCHEMA_PROVIDER_TYPES`をサポートする必要があります。詳細については、「 [IDBSchemaRowset](/previous-versions/windows/desktop/ms713686(v=vs.85)) OLE DB」を*参照*してください。 スキーマ行セットはスキーマ マップで指定します。 スキーマ マップ エントリの詳細については、「 [SCHEMA_ENTRY](../../data/oledb/schema-entry.md)」を参照してください。

ATL オブジェクト ウィザードの OLE DB プロバイダー ウィザードでは、プロジェクトのスキーマ行セットのコードが自動的に生成されます (既定では、ウィザードは、前述の必須のスキーマ行セットをサポートしています)。ATL オブジェクトウィザードを使用してコンシューマーを作成する場合、ウィザードはスキーマ行セットを使用して、適切なデータをプロバイダーにバインドします。 正しいメタデータを提供するようにスキーマ行セットを実装していないと、正しいデータがバインドされません。

プロバイダーでスキーマ行セットをサポートする方法については、「 [スキーマ行セットのサポート](../../data/oledb/supporting-schema-rowsets.md)」を参照してください。

スキーマ行セットの詳細については、 [OLE DB プログラマーズ リファレンス](/previous-versions/windows/desktop/ms712921(v=vs.85)) の *スキーマ行セット*に関するセクションを参照してください。

## <a name="idbschemarowsetimplcheckrestrictions"></a><a name="checkrestrictions"></a>IDBSchemaRowsetImpl:: CheckRestrictions 制限事項

スキーマ行セットに対して制限の妥当性をチェックします。

### <a name="syntax"></a>構文

```cpp
HRESULT CheckRestrictions(REFGUID rguidSchema,
   ULONG cRestrictions,  const VARIANT rgRestrictions[]);
```

#### <a name="parameters"></a>パラメーター

*rguidSchema*<br/>
[入力] 要求するスキーマ行セット GUID ( `DBSCHEMA_TABLES`など) への参照。

*cRestrictions*<br/>
[入力] コンシューマーがスキーマ行セットに渡した制限の数。

*rgRestrictions*<br/>
[入力] 設定する制限値の長さ *cRestrictions* の配列。 詳細については、「 [Setrestrictions 制限](../../data/oledb/idbschemarowsetimpl-setrestrictions.md)」の*rgRestrictions*パラメーターの説明を参照してください。

### <a name="remarks"></a>解説

`CheckRestrictions` を使用して、スキーマ行セットに対して制限の妥当性をチェックします。 `DBSCHEMA_TABLES`、`DBSCHEMA_COLUMNS`、および `DBSCHEMA_PROVIDER_TYPES` スキーマ行セットの制限をチェックします。 コンシューマーの `IDBSchemaRowset::GetRowset` の呼び出しが正しいかどうかを判断するには、このメソッドを呼び出します。 上記以外のスキーマ行セットをサポートする場合は、このタスクを実行する独自の関数を作成する必要があります。

`CheckRestrictions` は、コンシューマーが、プロバイダーがサポートしている適切な制限と、適切な制限の種類 (文字列の VT_BSTR など) を持つ[Getrowset](../../data/oledb/idbschemarowsetimpl-getrowset.md)を呼び出しているかどうかを判断します。 また、正しい制限数がサポートされているかどうかも判断します。 `CheckRestrictions` は、既定で [SetRestrictions](../../data/oledb/idbschemarowsetimpl-setrestrictions.md) 呼び出しを通じて、任意の行セットについてプロバイダーがサポートしている制限の種類を確認します。 次に、コンシューマーが呼び出した制限とプロバイダーがサポートしている制限を比較することで、処理は成功または失敗します。

スキーマ行セットの詳細については、Windows SDK の*OLE DB プログラマーリファレンス*の「 [IDBSchemaRowset](/previous-versions/windows/desktop/ms713686(v=vs.85)) 」を参照してください。

## <a name="idbschemarowsetimplcreateschemarowset"></a><a name="createschemarowset"></a>IDBSchemaRowsetImpl:: CreateSchemaRowset

テンプレート パラメーターで指定されたオブジェクトの COM オブジェクトの作成関数を実装します。

### <a name="syntax"></a>構文

```cpp
template template <class SchemaRowsetClass>
HRESULT CreateSchemaRowset(IUnknown *pUnkOuter,
   ULONG cRestrictions,
   const VARIANT rgRestrictions[],
   REFIID riid,
   ULONG cPropertySets,
   DBPROPSET rgPropertySets[],
   IUnknown** ppRowset,
   SchemaRowsetClass*& pSchemaRowset);
```

#### <a name="parameters"></a>パラメーター

*pUnkOuter*<br/>
から集計時に外部[IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) 。それ以外の場合は NULL。

*cRestrictions*<br/>
[入力] スキーマ行セットに適用する制限の数。

*rgRestrictions*<br/>
[入力] 行セットに適用する `cRestrictions`**VARIANT**の配列。

*riid*<br/>
から出力 `IUnknown`の[QueryInterface](../../atl/queryinterface.md)のインターフェイス。

*cPropertySets*<br/>
[入力] 設定するプロパティ セットの数。

*rgPropertySets*<br/>
[入力] 設定するプロパティを指定する [DBPROPSET](/previous-versions/windows/desktop/ms714367(v=vs.85)) 構造体の配列。

*ppRowset*<br/>
入出力*Riid*によって要求された送信 `IUnknown`。 この `IUnknown` は、スキーマ行セットオブジェクトのインターフェイスです。

*pSchemaRowset*<br/>
[出力] スキーマ行セット クラスのインスタンスへのポインター。 通常、このパラメーターは使用されません。使用できるのは、スキーマ行セットを COM オブジェクトに渡す前に、その行セットで多くの作業を実行する必要があるときです。 *PSchemaRowset*の有効期間は*ppRowset*によって制限されます。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

この関数は、あらゆる種類のスキーマ行セットに対する汎用作成関数を実装します。 通常、この関数は、ユーザーからは呼び出されません。 これはスキーマ マップの実装によって呼び出されます。

## <a name="idbschemarowsetimplsetrestrictions"></a><a name="setrestrictions"></a>IDBSchemaRowsetImpl:: SetRestrictions 制限

特定のスキーマ行セットでサポートする制限を指定します。

### <a name="syntax"></a>構文

```cpp
void SetRestrictions(ULONG cRestrictions,
   GUID* /* rguidSchema */,
   ULONG* rgRestrictions);
```

#### <a name="parameters"></a>パラメーター

*cRestrictions*<br/>
から*RgRestrictions*配列内の制限の数と、 *rguidschema*配列の guid の数。

*rguidSchema*<br/>
[入力] 制限をフェッチするスキーマ行セットの GUID の配列。 配列の各要素は、1 つのスキーマ行セットの GUID ( `DBSCHEMA_TABLES`など) を保持します。

*rgRestrictions*<br/>
[入力] 設定する制限値の長さ *cRestrictions* の配列。 各要素は、GUID によって識別されるスキーマ行セットの制限に対応します。 スキーマ行セットがプロバイダーによってサポートされていない場合、その要素は 0 に設定されます。 それ以外の場合、 **ULONG** 値は、そのスキーマ行セットでサポートされている制限を表すビット マスクを保持します。 特定のスキーマ行セットに対応する制限の詳細については、Windows SDK の*OLE DB プログラマーリファレンス*[のスキーマ](/previous-versions/windows/desktop/ms713686(v=vs.85))行セット guid の表を参照してください。

### <a name="remarks"></a>解説

`IDBSchemaRowset` オブジェクトは、`SetRestrictions` を呼び出して、特定のスキーマ行セットでサポートする制限を判断します ( [getschemas](../../data/oledb/idbschemarowsetimpl-getschemas.md)によってアップキャストされたポインターによって呼び出されます)。 制限により、コンシューマーは一致する行だけをフェッチできます (たとえば、テーブル "MyTable" 内のすべての列を検索します)。 制限は省略可能であり、制限がサポートされていない場合 (既定)、常にすべてのデータが返されます。

このメソッドの既定の実装では、 *rgRestrictions*配列要素が0に設定されます。 既定以外の制限を設定する場合は、セッション クラスで既定値をオーバーライドします。

スキーマ行セットのサポートの実装については、「 [スキーマ行セットのサポート](../../data/oledb/supporting-schema-rowsets.md)」を参照してください。

スキーマ行セットをサポートするプロバイダーの例については、 [UpdatePV](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/ATL/OLEDB/Provider/UPDATEPV) サンプルを参照してください。

スキーマ行セットの詳細については、Windows SDK の*OLE DB プログラマーリファレンス*の「 [IDBSchemaRowset](/previous-versions/windows/desktop/ms713686(v=vs.85)) 」を参照してください。

## <a name="idbschemarowsetimplgetrowset"></a><a name="getrowset"></a>IDBSchemaRowsetImpl:: GetRowset

スキーマ行セットを返します。

### <a name="syntax"></a>構文

```cpp
STDMETHOD (GetRowset)(IUnknown *pUnkOuter,
   REFGUID rguidSchema,
   ULONG cRestrictions,
   const VARIANT rgRestrictions[],
   REFIID riid,
   ULONG cPropertySets,
   DBPROPSET rgPropertySets[],
   IUnknown **ppRowset);
```

#### <a name="parameters"></a>パラメーター

*pUnkOuter*<br/>
から集計時の外側の `IUnknown`。それ以外の場合は NULL。

*rguidSchema*<br/>
[入力] 要求するスキーマ行セット GUID ( `DBSCHEMA_TABLES`など) への参照。

*cRestrictions*<br/>
[入力] 行セットに適用する制限の数。

*rgRestrictions*<br/>
[入力] 制限を表す `cRestrictions`**VARIANT**の配列。

*riid*<br/>
[入力] 新しく作成されたスキーマ行セットに対して要求する IID。

*cPropertySets*<br/>
[入力] 設定するプロパティ セットの数。

*rgPropertySets*<br/>
[入力/出力] 新しく作成されたスキーマ行セットに対して設定する [DBPROPSET](/previous-versions/windows/desktop/ms714367(v=vs.85)) 構造体の配列。

*ppRowset*<br/>
[出力] 新しく作成されたスキーマ行セットに対して要求するインターフェイスへのポインター。

### <a name="remarks"></a>解説

このメソッドを使用するには、ユーザーはセッション クラスにスキーマ マップを持っている必要があります。 スキーママップ情報を使用すると、 *Rguidschema*パラメーターがいずれかのマップエントリの guid と等しい場合、`GetRowset` によって指定された行セットオブジェクトが作成されます。 マップ エントリについては、「 [SCHEMA_ENTRY](../../data/oledb/schema-entry.md) 」を参照してください。

Windows SDK の「 [IDBSchemaRowset:: GetRowset](/previous-versions/windows/desktop/ms722634(v=vs.85)) 」を参照してください。

## <a name="idbschemarowsetimplgetschemas"></a><a name="getschemas"></a>IDBSchemaRowsetImpl:: GetSchemas

[IDBSchemaRowsetImpl::GetRowset](../../data/oledb/idbschemarowsetimpl-getrowset.md)でアクセスできるスキーマ行セットの一覧を返します。

### <a name="syntax"></a>構文

```cpp
STDMETHOD (GetSchema s )(ULONG * pcSchemas,
   GUID ** prgSchemas,
   ULONG** prgRest);
```

#### <a name="parameters"></a>パラメーター

*pcSchemas*<br/>
[出力] スキーマの数が格納される **ULONG** へのポインター。

*prgSchemas*<br/>
[出力] スキーマ行セット GUID の配列へのポインターが格納される GUID の配列へのポインター。

*prgRest*<br/>
[出力] 制限配列が格納される **ULONG**の配列へのポインター。

### <a name="remarks"></a>解説

このメソッドは、プロバイダーによってサポートされるすべてのスキーマ行セットの配列を返します。 Windows SDK の「 [IDBSchemaRowset:: GetSchemas](/previous-versions/windows/desktop/ms719605(v=vs.85)) 」を参照してください。

この関数の実装では、セッション クラスでスキーマ マップを持っている必要があります。 スキーマ マップ情報を使用して、マップ内のスキーマの GUID の配列で応答します。 これは、プロバイダーによってサポートされるスキーマを表します。

## <a name="see-also"></a>参照

[スキーマ行セット クラスと Typedef クラス](../../data/oledb/schema-rowset-classes-and-typedef-classes.md)<br/>
[スキーマ行セットのサポート](../../data/oledb/supporting-schema-rowsets.md)<br/>
[SCHEMA_ENTRY](../../data/oledb/schema-entry.md)<br/>
[UpdatePV](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/ATL/OLEDB/Provider)
