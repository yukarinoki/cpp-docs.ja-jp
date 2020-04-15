---
title: OLE DB プロバイダー テンプレート用マクロ
ms.date: 02/11/2019
f1_keywords:
- BEGIN_PROPERTY_SET
- BEGIN_PROPERTY_SET_EX
- BEGIN_PROPSET_MAP
- CHAIN_PROPERTY_SET
- END_PROPERTY_SET
- END_PROPSET_MAP
- PROPERTY_INFO_ENTRY
- PROPERTY_INFO_ENTRY_EX
- PROPERTY_INFO_ENTRY_VALUE
- BEGIN_PROVIDER_COLUMN_MAP
- END_PROVIDER_COLUMN_MAP
- PROVIDER_COLUMN_ENTRY
- PROVIDER_COLUMN_ENTRY_FIXED
- PROVIDER_COLUMN_ENTRY_GN
- PROVIDER_COLUMN_ENTRY_LENGTH
- PROVIDER_COLUMN_ENTRY_STR
- PROVIDER_COLUMN_ENTRY_TYPE_LENGTH
- PROVIDER_COLUMN_ENTRY_WSTR
- BEGIN_SCHEMA_MAP
- END_SCHEMA_MAP
- SCHEMA_ENTRY
helpviewer_keywords:
- OLE DB provider templates, macros
- macros, OLE DB Provider Templates
- Provider Template macros (OLE DB)
- OLE DB Provider Template macros
- BEGIN_PROPERTY_SET macro
- BEGIN_PROPERTY_SET_EX macro
- BEGIN_PROPSET_MAP macro
- CHAIN_PROPERTY_SET macro
- END_PROPERTY_SET macro
- END_PROPSET_MAP macro
- PROPERTY_INFO_ENTRY macro
- PROPERTY_INFO_ENTRY_EX macro
- PROPERTY_INFO_ENTRY_VALUE macro
- BEGIN_PROVIDER_COLUMN_MAP macro
- END_PROVIDER_COLUMN_MAP macro
- PROVIDER_COLUMN_ENTRY macro
- PROVIDER_COLUMN_ENTRY_FIXED macro
- PROVIDER_COLUMN_ENTRY_GN macro
- PROVIDER_COLUMN_ENTRY_LENGTH macro
- PROVIDER_COLUMN_ENTRY_STR macro
- PROVIDER_COLUMN_ENTRY_TYPE_LENGTH macro
- PROVIDER_COLUMN_ENTRY_WSTR macro
- BEGIN_SCHEMA_MAP macro
- END_SCHEMA_MAP macro
- SCHEMA_ENTRY macro
ms.assetid: 909482c5-64ab-4e52-84a9-1c07091db183
ms.openlocfilehash: 5d29b2548102b056a21ebfccb037af3a766788ba
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369803"
---
# <a name="macros-for-ole-db-provider-templates"></a>OLE DB プロバイダー テンプレート用マクロ

OLE DB テンプレート プロバイダー マクロは、次のカテゴリの機能を提供します。

## <a name="property-set-map-macros"></a>プロパティ セット マップ マクロ

|||
|-|-|
|[BEGIN_PROPERTY_SET](#begin_property_set)|プロパティ セットの先頭を示します。|
|[BEGIN_PROPERTY_SET_EX](#begin_property_set_ex)|プロパティ セットの先頭を示します。|
|[BEGIN_PROPSET_MAP](#begin_propset_map)|プロバイダーのスコープ外で非表示または定義できるプロパティ セットの先頭をマークします。|
|[CHAIN_PROPERTY_SET](#chain_property_set)|プロパティ グループを連結します。|
|[END_PROPERTY_SET](#end_property_set)|プロパティ セットの末尾をマークします。|
|[END_PROPSET_MAP](#end_propset_map)|プロパティ セット マップの終わりを示します。|
|[PROPERTY_INFO_ENTRY](#property_info_entry)|プロパティ セットの特定のプロパティを既定値に設定します。|
|[PROPERTY_INFO_ENTRY_EX](#property_info_entry_ex)|プロパティ セットの特定のプロパティを、ユーザーが指定した値に設定します。 また、フラグとオプションを設定することもできます。|
|[PROPERTY_INFO_ENTRY_VALUE](#property_info_entry_value)|プロパティ セットの特定のプロパティを、ユーザーが指定した値に設定します。|

## <a name="column-map-macros"></a>列マップ マクロ

|||
|-|-|
|[BEGIN_PROVIDER_COLUMN_MAP](#begin_provider_column_map)|プロバイダー列マップのエントリの先頭を示します。|
|[END_PROVIDER_COLUMN_MAP](#end_provider_column_map)|プロバイダー列マップのエントリの末尾をマークします。|
|[PROVIDER_COLUMN_ENTRY](#provider_column_entry)|プロバイダーでサポートされる特定の列を表します。|
|[PROVIDER_COLUMN_ENTRY_FIXED](#provider_column_entry_fixed)|プロバイダーでサポートされる特定の列を表します。 列のデータ型を指定できます。|
|[PROVIDER_COLUMN_ENTRY_GN](#provider_column_entry_gn)|プロバイダーでサポートされる特定の列を表します。 列のサイズ、データ型、有効桁数、スケール、およびスキーマ行セット GUID を指定できます。|
|[PROVIDER_COLUMN_ENTRY_LENGTH](#provider_column_entry_length)|プロバイダーでサポートされる特定の列を表します。 列サイズを指定できます。|
|[PROVIDER_COLUMN_ENTRY_STR](#provider_column_entry_str)|プロバイダーでサポートされる特定の列を表します。 列の型は文字列であると見なされます。|
|[PROVIDER_COLUMN_ENTRY_TYPE_LENGTH](#provider_column_entry_type_length)|プロバイダーでサポートされる特定の列を表します。 PROVIDER_COLUMN_ENTRY_LENGTH同様ですが、列のデータ型とサイズを指定することもできます。|
|[PROVIDER_COLUMN_ENTRY_WSTR](#provider_column_entry_wstr)|プロバイダーでサポートされる特定の列を表します。 列の型は Unicode 文字ストリングであると見なされます。|

## <a name="schema-rowset-macros"></a>スキーマ行セット マクロ

|||
|-|-|
|[BEGIN_SCHEMA_MAP](#begin_schema_map)|スキーマ マップの先頭を示します。|
|[END_SCHEMA_MAP](#end_schema_map)|スキーマ マップの末尾をマークします。|
|[SCHEMA_ENTRY](#schema_entry)|GUID をクラスに関連付けます。|

## <a name="requirements"></a>必要条件

**ヘッダー:** atldb.h

### <a name="begin_property_set"></a><a name="begin_property_set"></a>BEGIN_PROPERTY_SET

プロパティ セット マップ内のプロパティ セットの先頭を示します。

#### <a name="syntax"></a>構文

```cpp
BEGIN_PROPERTY_SET(guid)
```

#### <a name="parameters"></a>パラメーター

*guid*<br/>
[in]プロパティ GUID。

#### <a name="example"></a>例

「 [BEGIN_PROPSET_MAP](../../data/oledb/begin-propset-map.md)」を参照してください。

### <a name="begin_property_set_ex"></a><a name="begin_property_set_ex"></a>BEGIN_PROPERTY_SET_EX

プロパティ セット マップ内のプロパティ セットの先頭を示します。

#### <a name="syntax"></a>構文

```cpp
BEGIN_PROPERTY_SET_EX(guid, flags)
```

#### <a name="parameters"></a>パラメーター

*guid*<br/>
[in]プロパティ GUID。

*フラグ*<br/>
[in]UPROPSET_HIDDEN公開しないプロパティ セット、またはプロバイダのスコープ外で定義されているプロパティを公開するプロバイダのUPROPSET_PASSTHROUGHを行います。

#### <a name="example"></a>例

「 [BEGIN_PROPSET_MAP](../../data/oledb/begin-propset-map.md)」を参照してください。

### <a name="begin_propset_map"></a><a name="begin_propset_map"></a>BEGIN_PROPSET_MAP

プロパティ セット マップ エントリの先頭を示します。

#### <a name="syntax"></a>構文

```cpp
BEGIN_PROPSET_MAP(Class)
```

#### <a name="parameters"></a>パラメーター

*クラス*<br/>
[in]このプロパティ セットが指定されているクラス。 プロパティ セットは、次の OLE DB オブジェクトで指定できます。

- [データ ソース オブジェクト](/previous-versions/windows/desktop/ms721278(v=vs.85))

- [セッション オブジェクト](/previous-versions/windows/desktop/ms711572(v=vs.85))

- [コマンド](/previous-versions/windows/desktop/ms724608(v=vs.85))

#### <a name="example"></a>例

次に、プロパティ セット マップの例を示します。

[!code-cpp[NVC_OLEDB_Provider#3](../../data/oledb/codesnippet/cpp/begin-propset-map_1.h)]

### <a name="chain_property_set"></a><a name="chain_property_set"></a>CHAIN_PROPERTY_SET

このマクロは、プロパティ グループを連結します。

#### <a name="syntax"></a>構文

```cpp
CHAIN_PROPERTY_SET(ChainClass)
```

#### <a name="parameters"></a>パラメーター

*チェーンクラス*<br/>
[in]プロパティをチェーンするクラスの名前。 これは、ATL プロジェクト ウィザードによって生成されたクラスで、既にマップ (セッション、コマンド、データ ソース オブジェクト クラスなど) が含まれています。

#### <a name="remarks"></a>解説

プロパティ セットを別のクラスから独自のクラスに連結し、クラスから直接プロパティにアクセスできます。

> [!CAUTION]
> このマクロは控えめに使用してください。 不適切な使用は、コンシューマが OLE DB 準拠テストに失敗する原因となる可能性があります。

### <a name="end_property_set"></a><a name="end_property_set"></a>END_PROPERTY_SET

プロパティ セットの末尾をマークします。

#### <a name="syntax"></a>構文

```cpp
END_PROPERTY_SET(guid)
```

#### <a name="parameters"></a>パラメーター

*guid*<br/>
[in]プロパティ GUID。

#### <a name="example"></a>例

「 [BEGIN_PROPSET_MAP](../../data/oledb/begin-propset-map.md)」を参照してください。

### <a name="end_propset_map"></a><a name="end_propset_map"></a>END_PROPSET_MAP

プロパティ セット マップ エントリの末尾をマークします。

#### <a name="syntax"></a>構文

```cpp
END_PROPSET_MAP()
```

#### <a name="example"></a>例

「 [BEGIN_PROPSET_MAP](../../data/oledb/begin-propset-map.md)」を参照してください。

### <a name="property_info_entry"></a><a name="property_info_entry"></a>PROPERTY_INFO_ENTRY

プロパティ セットの特定のプロパティを表します。

#### <a name="syntax"></a>構文

```cpp
PROPERTY_INFO_ENTRY(dwPropID)
```

#### <a name="parameters"></a>パラメーター

*dwPropID*<br/>
[入力] プロパティ セット GUID と組み合わせて使用してプロパティを特定する [DBPROPID](/previous-versions/windows/desktop/ms723882(v=vs.85)) 値。

#### <a name="remarks"></a>解説

このマクロは、 `DWORD` 型のプロパティ値を、ATLDB.H で定義された既定値に設定します。 選択した値にプロパティを設定するには、 [PROPERTY_INFO_ENTRY_VALUE](../../data/oledb/property-info-entry-value.md)を使用します。 プロパティに`VARTYPE`対して[DBPROPFLAGS](/previous-versions/windows/desktop/ms724342(v=vs.85))を同時に設定するには[、PROPERTY_INFO_ENTRY_EX](../../data/oledb/property-info-entry-ex.md)を使用します。

#### <a name="example"></a>例

「 [BEGIN_PROPSET_MAP](../../data/oledb/begin-propset-map.md)」を参照してください。

### <a name="property_info_entry_ex"></a><a name="property_info_entry_ex"></a>PROPERTY_INFO_ENTRY_EX

プロパティ セットの特定のプロパティを表します。

#### <a name="syntax"></a>構文

```cpp
PROPERTY_INFO_ENTRY_EX(dwPropID, vt, dwFlags, value, options)
```

#### <a name="parameters"></a>パラメーター

*dwPropID*<br/>
[入力] プロパティ セット GUID と組み合わせて使用してプロパティを特定する [DBPROPID](/previous-versions/windows/desktop/ms723882(v=vs.85)) 値。

*vt*<br/>
[入力] このプロパティ エントリの `VARTYPE`。 (wtypes.h で定義されています)

*dwFlags*<br/>
[入力] このプロパティ エントリを記述している [DBPROPFLAGS](/previous-versions/windows/desktop/ms724342(v=vs.85)) 値。

*value*<br/>
[入力] `DWORD`型のプロパティ値。

*オプション*<br/>
DBPROPOPTIONS_REQUIRED または DBPROPOPTIONS_SETIFCHEAP。 通常、プロバイダーはコンシューマーによって設定されるため、*オプション*を設定する必要はありません。

#### <a name="remarks"></a>解説

このマクロでは、オプションとフラグだけでなく、 `DWORD` 型のプロパティの値を直接指定できます。 単にプロパティを ATLDB.H に定義されている既定値に設定するには、 [PROPERTY_INFO_ENTRY](../../data/oledb/property-info-entry.md)を使用します。 オプションやフラグを設定せずに任意の値にプロパティを設定するには、 [PROPERTY_INFO_ENTRY_VALUE](../../data/oledb/property-info-entry-value.md)を使用します。

#### <a name="example"></a>例

「 [BEGIN_PROPSET_MAP](../../data/oledb/begin-propset-map.md)」を参照してください。

### <a name="property_info_entry_value"></a><a name="property_info_entry_value"></a>PROPERTY_INFO_ENTRY_VALUE

プロパティ セットの特定のプロパティを表します。

#### <a name="syntax"></a>構文

```cpp
PROPERTY_INFO_ENTRY_VALUE(dwPropID, value)
```

#### <a name="parameters"></a>パラメーター

*dwPropID*<br/>
[入力] プロパティ セット GUID と組み合わせて使用してプロパティを特定する [DBPROPID](/previous-versions/windows/desktop/ms723882(v=vs.85)) 値。

*value*<br/>
[入力] `DWORD`型のプロパティ値。

#### <a name="remarks"></a>解説

このマクロを使用すると、 type`DWORD`のプロパティ値を直接指定できます。 ATLDB で定義された既定値にプロパティを設定します。H, [PROPERTY_INFO_ENTRY](../../data/oledb/property-info-entry.md)を使用します。 プロパティの値、フラグ、およびオプションを設定するには、 [PROPERTY_INFO_ENTRY_EX](../../data/oledb/property-info-entry-ex.md)を使用します。

#### <a name="example"></a>例

「 [BEGIN_PROPSET_MAP](../../data/oledb/begin-propset-map.md)」を参照してください。

### <a name="begin_provider_column_map"></a><a name="begin_provider_column_map"></a>BEGIN_PROVIDER_COLUMN_MAP

プロバイダー列マップのエントリの先頭を示します。

#### <a name="syntax"></a>構文

```cpp
BEGIN_PROVIDER_COLUMN_MAP(theClass)
```

#### <a name="parameters"></a>パラメーター

*クラス*<br/>
[in]このマップが属するクラスの名前。

#### <a name="example"></a>例

プロバイダー列マップの例を次に示します。

[!code-cpp[NVC_OLEDB_Provider#4](../../data/oledb/codesnippet/cpp/begin-provider-column-map_1.h)]

### <a name="end_provider_column_map"></a><a name="end_provider_column_map"></a>END_PROVIDER_COLUMN_MAP

プロバイダー列マップのエントリの末尾をマークします。

#### <a name="syntax"></a>構文

```cpp
END_PROVIDER_COLUMN_MAP()
```

#### <a name="example"></a>例

[BEGIN_PROVIDER_COLUMN_MAP](../../data/oledb/begin-provider-column-map.md)を参照してください。

### <a name="provider_column_entry"></a><a name="provider_column_entry"></a>PROVIDER_COLUMN_ENTRY

プロバイダーでサポートされる特定の列を表します。

#### <a name="syntax"></a>構文

```cpp
PROVIDER_COLUMN_ENTRY (name, ordinal, member)
```

#### <a name="parameters"></a>パラメーター

*name*<br/>
[in]列名。

*序数*<br/>
[in]列番号。 列がブックマーク列でない場合、列番号は 0 にすることはできません。

*メンバー*<br/>
[in]列に`dataClass`対応するメンバー変数。

### <a name="provider_column_entry_fixed"></a><a name="provider_column_entry_fixed"></a>PROVIDER_COLUMN_ENTRY_FIXED

プロバイダーでサポートされる特定の列を表します。

#### <a name="syntax"></a>構文

```cpp
PROVIDER_COLUMN_ENTRY_FIXED(name, ordinal, dbtype, member)
```

#### <a name="parameters"></a>パラメーター

*name*<br/>
[in]列名。

*序数*<br/>
[in]列番号。 列がブックマーク列でない場合、列番号は 0 にすることはできません。

*Dbtype*<br/>
[in][DBTYPE](/previous-versions/windows/desktop/ms711251(v=vs.85))のデータ型。

*メンバー*<br/>
[in]データを格納する`dataClass`メンバー変数。

#### <a name="remarks"></a>解説

列のデータ型を指定できます。

#### <a name="example"></a>例

[BEGIN_PROVIDER_COLUMN_MAP](../../data/oledb/begin-provider-column-map.md)を参照してください。

### <a name="provider_column_entry_gn"></a><a name="provider_column_entry_gn"></a>PROVIDER_COLUMN_ENTRY_GN

プロバイダーでサポートされる特定の列を表します。

#### <a name="syntax"></a>構文

```cpp
PROVIDER_COLUMN_ENTRY_GN (name, ordinal, flags, colSize, dbtype, precision, scale, guid)
```

#### <a name="parameters"></a>パラメーター

*name*<br/>
[in]列名。

*序数*<br/>
[in]列番号。 列がブックマーク列でない場合、列番号は 0 にすることはできません。

*フラグ*<br/>
[in]データの返し方を指定します。 DBBINDING`dwFlags`構造体 の説明[を](/previous-versions/windows/desktop/ms716845(v=vs.85))参照してください。

*コルサイズ*<br/>
[in]列のサイズ。

*Dbtype*<br/>
[in]値のデータ型を示します。 DBBINDING`wType`構造体 の説明[を](/previous-versions/windows/desktop/ms716845(v=vs.85))参照してください。

*精度*<br/>
[in]*dbType*がDBTYPE_NUMERICまたはDBTYPE_DECIMALの場合に、データを取得するときに使用する精度を示します。 DBBINDING`bPrecision`構造体 の説明[を](/previous-versions/windows/desktop/ms716845(v=vs.85))参照してください。

*スケール*<br/>
[in]dbType がDBTYPE_NUMERICまたはDBTYPE_DECIMALの場合にデータを取得するときに使用するスケールを示します。 DBBINDING`bScale`構造体 の説明[を](/previous-versions/windows/desktop/ms716845(v=vs.85))参照してください。

*guid*<br/>
スキーマ行セット GUID。 スキーマ行セットとその GUID の一覧については *、「OLE DB プログラマ リファレンス*」の[IDBSchemaRowset](/previous-versions/windows/desktop/ms713686(v=vs.85))を参照してください。

#### <a name="remarks"></a>解説

列のサイズ、データ型、有効桁数、スケール、およびスキーマ行セット GUID を指定できます。

### <a name="provider_column_entry_length"></a><a name="provider_column_entry_length"></a>PROVIDER_COLUMN_ENTRY_LENGTH

プロバイダーでサポートされる特定の列を表します。

#### <a name="syntax"></a>構文

```cpp
PROVIDER_COLUMN_ENTRY_LENGTH(name, ordinal, size, member)
```

#### <a name="parameters"></a>パラメーター

*name*<br/>
[in]列名。

*序数*<br/>
[in]列番号。 列がブックマーク列でない場合、列番号は 0 にすることはできません。

*サイズ*<br/>
[in]列のサイズ (バイト単位)。

*メンバー*<br/>
[in]列データ`dataClass`を格納するメンバー変数。

#### <a name="remarks"></a>解説

列サイズを指定できます。

#### <a name="example"></a>例

[BEGIN_PROVIDER_COLUMN_MAP](../../data/oledb/begin-provider-column-map.md)を参照してください。

### <a name="provider_column_entry_str"></a><a name="provider_column_entry_str"></a>PROVIDER_COLUMN_ENTRY_STR

プロバイダーでサポートされる特定の列を表します。

#### <a name="syntax"></a>構文

```cpp
PROVIDER_COLUMN_ENTRY_STR(name, ordinal, member)
```

#### <a name="parameters"></a>パラメーター

*name*<br/>
[in]列名。

*序数*<br/>
[in]列番号。 列がブックマーク列でない場合、列番号は 0 にすることはできません。

*メンバー*<br/>
[in]データを格納するデータ クラスのメンバー変数。

#### <a name="remarks"></a>解説

列データが[DBTYPE_STR](/previous-versions/windows/desktop/ms711251(v=vs.85))であると想定される場合に、このマクロを使用します。

#### <a name="example"></a>例

[BEGIN_PROVIDER_COLUMN_MAP](../../data/oledb/begin-provider-column-map.md)を参照してください。

### <a name="provider_column_entry_type_length"></a><a name="provider_column_entry_type_length"></a>PROVIDER_COLUMN_ENTRY_TYPE_LENGTH

プロバイダーでサポートされる特定の列を表します。

#### <a name="syntax"></a>構文

```cpp
PROVIDER_COLUMN_ENTRY_TYPE_LENGTH(name, ordinal, dbtype, size, member)
```

#### <a name="parameters"></a>パラメーター

*name*<br/>
[in]列名。

*序数*<br/>
[in]列番号。 列がブックマーク列でない場合、列番号は 0 にすることはできません。

*Dbtype*<br/>
[in][DBTYPE](/previous-versions/windows/desktop/ms711251(v=vs.85))のデータ型。

*サイズ*<br/>
[in]列のサイズ (バイト単位)。

*メンバー*<br/>
[in]データを格納するデータ クラスのメンバー変数。

#### <a name="remarks"></a>解説

[PROVIDER_COLUMN_ENTRY_LENGTH](../../data/oledb/provider-column-entry-length.md)に似ていますが、列のデータ型とサイズを指定することもできます。

### <a name="provider_column_entry_wstr"></a><a name="provider_column_entry_wstr"></a>PROVIDER_COLUMN_ENTRY_WSTR

プロバイダーでサポートされる特定の列を表します。

#### <a name="syntax"></a>構文

```cpp
PROVIDER_COLUMN_ENTRY_WSTR(name, ordinal, member)
```

#### <a name="parameters"></a>パラメーター

*name*<br/>
[in]列名。

*序数*<br/>
[in]列番号。 列がブックマーク列でない場合、列番号は 0 にすることはできません。

*メンバー*<br/>
[in]データを格納するデータ クラスのメンバー変数。

#### <a name="remarks"></a>解説

列データが null で終わる Unicode 文字ストリングである場合、このマクロ[DBTYPE_WSTR](/previous-versions/windows/desktop/ms711251(v=vs.85))使用します。

### <a name="begin_schema_map"></a><a name="begin_schema_map"></a>BEGIN_SCHEMA_MAP

スキーマ マップの先頭を示します。

#### <a name="syntax"></a>構文

```cpp
BEGIN_SCHEMA_MAP(SchemaClass);
```

#### <a name="parameters"></a>パラメーター

*スキーマクラス*<br/>
MAP を含むクラス。 通常、これはセッション クラスになります。

#### <a name="remarks"></a>解説

スキーマ行セットの詳細については、Windows SDK の[IDB スキーマ行](/previous-versions/windows/desktop/ms713686(v=vs.85))セットを参照してください。

### <a name="end_schema_map"></a><a name="end_schema_map"></a>END_SCHEMA_MAP

スキーマ マップの末尾を示します。

#### <a name="syntax"></a>構文

```cpp
END_SCHEMA_MAP()
```

#### <a name="remarks"></a>解説

詳細については、「[クラス」](../../data/oledb/idbschemarowsetimpl-class.md)を参照してください。

### <a name="schema_entry"></a><a name="schema_entry"></a>SCHEMA_ENTRY

GUID をクラスに関連付けます。

#### <a name="syntax"></a>構文

```cpp
SCHEMA_ENTRY(guid,
   rowsetClass);
```

#### <a name="parameters"></a>パラメーター

*guid*<br/>
スキーマ行セット GUID。 スキーマ行セットとその GUID の一覧については *、「OLE DB プログラマ リファレンス*」の[IDBSchemaRowset](/previous-versions/windows/desktop/ms713686(v=vs.85))を参照してください。

*行セットクラス*<br/>
スキーマ行セットを表すために作成されるクラス。

#### <a name="remarks"></a>解説

[IDBSchemaRowsetImpl](../../data/oledb/idbschemarowsetimpl-class.md)は、GUID の一覧をマップに照会するか、GUID が与えられている場合は行セットを作成できます。 スキーマ行セット`IDBSchemaRowsetImpl`の作成は、標準`CRowsetImpl`の派生クラスに似ていますが、次のシグネチャ`Execute`を持つメソッドを提供する必要があります。

```cpp
HRESULT Execute (LONG* pcRowsAffected,
    ULONG cRestrictions,
    const VARIANT* rgRestrictions);
```

この`Execute`関数は、行セットのデータを設定します。 ATL プロジェクト ウィザードは *、OLE DB プログラマ リファレンス*の[IDBSchemaRowset](/previous-versions/windows/desktop/ms713686(v=vs.85))で説明されているように、3 つの必須 OLE DB スキーマのそれぞれについてプロジェクト内の 3 つの初期スキーマ行セットを作成します。

- DBSCHEMA_TABLES

- DBSCHEMA_COLUMNS

- DBSCHEMA_PROVIDER_TYPES

また、ウィザードは、対応する 3 つのエントリをスキーマ マップに追加します。 ウィザード[を使用してプロバイダーを作成](../../data/oledb/creating-an-ole-db-provider.md)する方法の詳細については、「OLE DB テンプレート プロバイダーの作成」を参照してください。

## <a name="see-also"></a>関連項目

[OLE DB プロバイダー テンプレートに関するページ](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB プロバイダー テンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)<br/>
[OLE DB プロバイダの作成](../../data/oledb/creating-an-ole-db-provider.md)<br/>
[OLE DB プロバイダ テンプレート リファレンス](../../data/oledb/ole-db-provider-templates-reference.md)<br/>
[OLE DB プロバイダ テンプレートのマクロ](../../data/oledb/macros-for-ole-db-provider-templates.md)
