---
description: 詳細については、OLE DB コンシューマーテンプレートのマクロとグローバル関数に関するページを参照してください。
title: OLE DB コンシューマー テンプレート用マクロおよびグローバル関数
ms.date: 02/11/2019
f1_keywords:
- ATL.AtlTraceErrorRecords
- ATL::AtlTraceErrorRecords
- AtlTraceErrorRecords
- BEGIN_ACCESSOR
- BEGIN_ACCESSOR_MAP
- END_ACCESSOR
- END_ACCESSOR_MAP
- BEGIN_COLUMN_MAP
- BLOB_ENTRY
- BLOB_ENTRY_LENGTH
- BLOB_ENTRY_LENGTH_STATUS
- BLOB_ENTRY_STATUS
- BLOB_NAME
- BLOB_NAME_LENGTH
- BLOB_NAME_LENGTH_STATUS
- BLOB_NAME_STATUS
- BOOKMARK_ENTRY
- COLUMN_ENTRY
- COLUMN_ENTRY_EX
- COLUMN_ENTRY_LENGTH
- COLUMN_ENTRY_LENGTH_STATUS
- COLUMN_ENTRY_PS
- COLUMN_ENTRY_PS_LENGTH
- COLUMN_ENTRY_PS_LENGTH_STATUS
- COLUMN_ENTRY_PS_STATUS
- COLUMN_ENTRY_STATUS
- COLUMN_ENTRY_TYPE
- COLUMN_ENTRY_TYPE_SIZE
- COLUMN_NAME
- COLUMN_NAME_EX
- COLUMN_NAME_LENGTH
- COLUMN_NAME_LENGTH_STATUS
- COLUMN_NAME_PS
- COLUMN_NAME_PS_LENGTH
- COLUMN_NAME_PS_LENGTH_STATUS
- COLUMN_NAME_PS_STATUS
- COLUMN_NAME_STATUS
- COLUMN_NAME_TYPE
- COLUMN_NAME_TYPE_PS
- COLUMN_NAME_TYPE_SIZE
- COLUMN_NAME_TYPE_STATUS
- END_COLUMN_MAP
- DEFINE_COMMAND
- DEFINE_COMMAND_EX
- BEGIN_PARAM_MAP
- END_PARAM_MAP
- SET_PARAM_TYPE
helpviewer_keywords:
- OLE DB consumer templates, macros
- macros, OLE DB consumer template
- AtlTraceErrorRecords function
- BEGIN_ACCESSOR macro, syntax
- BEGIN_ACCESSOR macro
- BEGIN_ACCESSOR_MAP macro
- END_ACCESSOR macro
- END_ACCESSOR_MAP macro
- BEGIN_COLUMN_MAP macro
- BLOB_ENTRY macro
- BLOB_ENTRY_LENGTH macro
- BLOB_ENTRY_LENGTH_STATUS macro
- BLOB_ENTRY_STATUS macro
- BLOB_NAME macro
- BLOB_NAME_LENGTH macro
- BLOB_NAME_LENGTH_STATUS macro
- BLOB_NAME_STATUS macro
- BOOKMARK_ENTRY macro
- COLUMN_ENTRY macro
- COLUMN_ENTRY_EX macro
- COLUMN_ENTRY_LENGTH macro
- COLUMN_ENTRY_LENGTH_STATUS macro
- COLUMN_ENTRY_PS macro
- COLUMN_ENTRY_PS_LENGTH macro
- COLUMN_ENTRY_PS_LENGTH_STATUS macro
- COLUMN_ENTRY_PS_STATUS macro
- COLUMN_ENTRY_STATUS macro
- COLUMN_ENTRY_TYPE macro
- COLUMN_ENTRY_TYPE_SIZE macro
- COLUMN_NAME macro
- COLUMN_NAME_EX macro
- COLUMN_NAME_LENGTH macro
- COLUMN_NAME_LENGTH_STATUS macro
- COLUMN_NAME_PS macro
- COLUMN_NAME_PS_LENGTH macro
- COLUMN_NAME_PS_LENGTH_STATUS macro
- COLUMN_NAME_PS_STATUS macro
- COLUMN_NAME_STATUS macro
- COLUMN_NAME_TYPE macro
- COLUMN_NAME_TYPE_PS macro
- COLUMN_NAME_TYPE_SIZE macro
- COLUMN_NAME_TYPE_STATUS macro
- END_COLUMN_MAP macro
- DEFINE_COMMAND macro
- DEFINE_COMMAND_EX macro
- BEGIN_PARAM_MAP macro
- END_PARAM_MAP macro
- SET_PARAM_TYPE macro
ms.assetid: 8765eb7b-32dd-407c-bacf-8890ef959837
ms.openlocfilehash: fb6e126483690e43ceaf3814f6c288ecfdc69da1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97287074"
---
# <a name="macros-and-global-functions-for-ole-db-consumer-templates"></a>OLE DB コンシューマー テンプレート用マクロおよびグローバル関数

OLE DB コンシューマーテンプレートには、次のマクロとグローバル関数が含まれています。

## <a name="global-functions"></a>グローバル関数

| 名前 | 説明 |
|-|-|
|[AtlTraceErrorRecords](#atltraceerrorrecords)|エラーが返された場合は、エラーレコード情報をダンプデバイスにダンプ OLE DB ます。|

## <a name="accessor-map-macros"></a>アクセサーマップマクロ

| 名前 | 説明 |
|-|-|
|[BEGIN_ACCESSOR](#begin_accessor)|アクセサーエントリの先頭をマークします。|
|[BEGIN_ACCESSOR_MAP](#begin_accessor_map)|アクセサー マップ エントリの開始位置を示します。|
|[END_ACCESSOR](#end_accessor)|アクセサーエントリの末尾をマークします。|
|[END_ACCESSOR_MAP](#end_accessor_map)|アクセサーマップエントリの末尾をマークします。|

## <a name="column-map-macros"></a>列マップマクロ

| 名前 | 説明 |
|-|-|
|[BEGIN_COLUMN_MAP](#begin_column_map)|ユーザーレコードクラスの列マップエントリの先頭にマークを付けます。|
|[BLOB_ENTRY](#blob_entry)|バイナリラージオブジェクト (BLOB) をバインドするために使用されます。|
|[BLOB_ENTRY_LENGTH](#blob_entry_length)|BLOB データ列の長さを報告します。|
|[BLOB_ENTRY_LENGTH_STATUS](#blob_entry_length_status)|BLOB データ列の長さと状態を報告します。|
|[BLOB_ENTRY_STATUS](#blob_entry_status)|BLOB データ列の状態を報告します。|
|[BLOB_NAME](#blob_name)|列名でバイナリラージオブジェクトをバインドするために使用されます。|
|[BLOB_NAME_LENGTH](#blob_name_length)|BLOB データ列の長さを報告します。|
|[BLOB_NAME_LENGTH_STATUS](#blob_name_length_status)|BLOB データ列の長さと状態を報告します。|
|[BLOB_NAME_STATUS](#blob_name_status)|BLOB データ列の状態を報告します。|
|[BOOKMARK_ENTRY](#bookmark_entry)|行セットのブックマークエントリを表します。 ブックマークエントリは、特殊な種類の列エントリです。|
|[COLUMN_ENTRY](#column_entry)|データベース内の特定の列へのバインドを表します。|
|[COLUMN_ENTRY_EX](#column_entry_ex)|データベース内の特定の列へのバインドを表します。 *型*、*長さ*、*有効桁数*、*小数点以下桁数*、および *状態* のパラメーターをサポートします。|
|[COLUMN_ENTRY_LENGTH](#column_entry_length)|データベース内の特定の列へのバインドを表します。 *長さ* の変数をサポートします。|
|[COLUMN_ENTRY_LENGTH_STATUS](#column_entry_length_status)|データベース内の特定の列へのバインドを表します。 は、 *ステータス* と *長さ* のパラメーターをサポートしています。|
|[COLUMN_ENTRY_PS](#column_entry_ps)|データベース内の特定の列へのバインドを表します。 *有効桁数* と *小数点以下* 桁数のパラメーターをサポートします。|
|[COLUMN_ENTRY_PS_LENGTH](#column_entry_ps_length)|データベース内の特定の列へのバインドを表します。 *長さ* の変数、*有効桁数*、および *小数点以下桁数* のパラメーターをサポートします。|
|[COLUMN_ENTRY_PS_LENGTH_STATUS](#column_entry_ps_length_status)|データベース内の特定の列へのバインドを表します。 では、 *状態* と *長さ* の変数、 *有効桁数* 、および *小数点以下桁数* のパラメーターがサポートされます。|
|[COLUMN_ENTRY_PS_STATUS](#column_entry_ps_status)|データベース内の特定の列へのバインドを表します。 では、 *状態* 変数、 *有効桁数* 、および *小数点以下桁数* のパラメーターがサポートされます。|
|[COLUMN_ENTRY_STATUS](#column_entry_status)|データベース内の特定の列へのバインドを表します。 *Status* 変数をサポートします。|
|[COLUMN_ENTRY_TYPE](#column_entry_type)|データベース内の特定の列へのバインドを表します。 *型* パラメーターをサポートします。|
|[COLUMN_ENTRY_TYPE_SIZE](#column_entry_type_size)|データベース内の特定の列へのバインドを表します。 では、 *型* パラメーターと *サイズ* パラメーターがサポートされています。|
|[COLUMN_NAME](#column_name)|名前を指定して、データベース内の特定の列へのバインドを表します。|
|[COLUMN_NAME_EX](#column_name_ex)|名前を指定して、データベース内の特定の列へのバインドを表します。 では、データ型、サイズ、有効桁数、小数点以下桁数、列の長さ、および列の状態の指定をサポートしています。|
|[COLUMN_NAME_LENGTH](#column_name_length)|名前を指定して、データベース内の特定の列へのバインドを表します。 列の長さの指定をサポートします。|
|[COLUMN_NAME_LENGTH_STATUS](#column_name_length_status)|名前を指定して、データベース内の特定の列へのバインドを表します。 列の長さと状態の指定をサポートします。|
|[COLUMN_NAME_PS](#column_name_ps)|名前を指定して、データベース内の特定の列へのバインドを表します。 は、有効桁数と小数点以下桁数の指定をサポートしています。|
|[COLUMN_NAME_PS_LENGTH](#column_name_ps_length)|名前を指定して、データベース内の特定の列へのバインドを表します。 は、有効桁数、小数点以下桁数、および列の長さの指定をサポートしています。|
|[COLUMN_NAME_PS_LENGTH_STATUS](#column_name_ps_length_status)|名前を指定して、データベース内の特定の列へのバインドを表します。 では、有効桁数、小数点以下桁数、列の長さ、および列の状態の指定をサポートしています。|
|[COLUMN_NAME_PS_STATUS](#column_name_ps_status)|名前を指定して、データベース内の特定の列へのバインドを表します。 有効桁数、小数点以下桁数、および列の状態の指定をサポートします。|
|[COLUMN_NAME_STATUS](#column_name_status)|名前を指定して、データベース内の特定の列へのバインドを表します。 列の状態の指定をサポートします。|
|[COLUMN_NAME_TYPE](#column_name_type)|名前を指定して、データベース内の特定の列へのバインドを表します。 データ型の指定をサポートします。|
|[COLUMN_NAME_TYPE_PS](#column_name_type_ps)|名前を指定して、データベース内の特定の列へのバインドを表します。 データ型、有効桁数、および小数点以下桁数の指定をサポートします。|
|[COLUMN_NAME_TYPE_SIZE](#column_name_type_size)|名前を指定して、データベース内の特定の列へのバインドを表します。 データ型とサイズの指定をサポートします。|
|[COLUMN_NAME_TYPE_STATUS](#column_name_type_status)|名前を指定して、データベース内の特定の列へのバインドを表します。 データ型と列の状態の指定をサポートします。|
|[END_COLUMN_MAP](#end_column_map)|列マップエントリの末尾をマークします。|

## <a name="command-macros"></a>コマンドマクロ

| 名前 | 説明 |
|-|-|
|[DEFINE_COMMAND](#define_command)|[CCommand](../../data/oledb/ccommand-class.md)クラスを使用するときに行セットを作成するために使用されるコマンドを指定します。 指定されたアプリケーションの種類 (ANSI または Unicode) に一致する文字列型のみを受け入れます。 DEFINE_COMMAND ではなく [DEFINE_COMMAND_EX](#define_command_ex) を使用することをお勧めします。|
|[DEFINE_COMMAND_EX](#define_command_ex)|[CCommand](../../data/oledb/ccommand-class.md)クラスを使用するときに行セットを作成するために使用されるコマンドを指定します。 は、ANSI および Unicode のアプリケーションをサポートしています。|

## <a name="parameter-map-macros"></a>パラメーターマップマクロ

| 名前 | 説明 |
|-|-|
|[BEGIN_PARAM_MAP](#begin_param_map)|ユーザーレコードクラスのパラメーターマップエントリの開始をマークします。|
|[END_PARAM_MAP](#end_param_map)|パラメーターマップエントリの末尾をマークします。|
|[SET_PARAM_TYPE](#set_param_type)|SET_PARAM_TYPE マクロの後に入力、出力、または入力/出力として実行するマクロ COLUMN_ENTRY を指定します。|

### <a name="atltraceerrorrecords"></a><a name="atltraceerrorrecords"></a> AtlTraceErrorRecords

エラーが返された場合は、エラーレコード情報をダンプデバイスにダンプ OLE DB ます。

#### <a name="syntax"></a>構文

```cpp
inline void AtlTraceErrorRecords(HRESULT hrErr = S_OK);
```

#### <a name="parameters"></a>パラメーター

*hErr*<br/>
からOLE DB コンシューマーテンプレートメンバー関数によって返される HRESULT。

#### <a name="remarks"></a>解説

*HErr* が S_OK ない場合、 `AtlTraceErrorRecords` OLE DB エラーレコード情報をダンプデバイス ([出力] ウィンドウの [**デバッグ**] タブまたはファイル) にダンプします。 プロバイダーから取得されるエラーレコード情報には、行番号、ソース、説明、ヘルプファイル、コンテキスト、および各エラーレコードエントリの GUID が含まれます。 `AtlTraceErrorRecords` デバッグビルドでのみこの情報をダンプします。 リリースビルドでは、空のスタブは最適化されています。詳細については、「 [CDBErrorInfo クラス](../../data/oledb/cdberrorinfo-class.md)」を参照してください。

### <a name="begin_accessor"></a><a name="begin_accessor"></a> BEGIN_ACCESSOR

アクセサーエントリの先頭をマークします。

#### <a name="syntax"></a>構文

```cpp
BEGIN_ACCESSOR(num, bAuto)
```

#### <a name="parameters"></a>パラメーター

*num*<br/>
からこのアクセサーマップのアクセサーの0オフセット番号。

*bAuto*<br/>
からこのアクセサーが自動アクセサーまたは手動アクセサーのどちらであるかを指定します。 の場合 **`true`** 、アクセサーは auto です。の場合 **`false`** 、アクセサーは手動です。 自動アクセサーは、移動操作でデータがフェッチされることを意味します。

#### <a name="remarks"></a>解説

行セットに複数のアクセサーがある場合は、BEGIN_ACCESSOR_MAP を指定し、個々のアクセサーに対して BEGIN_ACCESSOR マクロを使用する必要があります。 BEGIN_ACCESSOR マクロは、END_ACCESSOR マクロを使用して完了します。 BEGIN_ACCESSOR_MAP マクロは、END_ACCESSOR_MAP マクロを使用して完了します。

#### <a name="example"></a>例

「 [BEGIN_ACCESSOR_MAP](#begin_accessor_map)」を参照してください。

### <a name="begin_accessor_map"></a><a name="begin_accessor_map"></a> BEGIN_ACCESSOR_MAP

アクセサー マップ エントリの開始位置を示します。

#### <a name="syntax"></a>構文

```cpp
BEGIN_ACCESSOR_MAP(x, num)
```

#### <a name="parameters"></a>パラメーター

*x*<br/>
[入力] ユーザー レコード クラスの名前。

*num*<br/>
[入力] このアクセサー マップのアクセサーの数。

#### <a name="remarks"></a>解説

行セットに複数のアクセサーがある場合は、先頭に BEGIN_ACCESSOR_MAP を指定し、個々のアクセサーに対して BEGIN_ACCESSOR マクロを使用する必要があります。 BEGIN_ACCESSOR マクロは、END_ACCESSOR マクロを使用して完了します。 アクセサーマップは、END_ACCESSOR_MAP マクロを使用して完了します。

ユーザー レコードに含まれるアクセサーが 1 つのみの場合は、 [BEGIN_COLUMN_MAP](#begin_column_map)マクロを使用します。

#### <a name="example"></a>例

```cpp
class CArtistsAccessor
{
public:
// Data Elements
   TCHAR m_szFirstName[21];
   TCHAR m_szLastName[31];
   short m_nAge;

// Output binding map
BEGIN_ACCESSOR_MAP(CArtistsAccessor, 2)
   BEGIN_ACCESSOR(0, true)
      COLUMN_ENTRY(1, m_szFirstName)
      COLUMN_ENTRY(2, m_szLastName)
   END_ACCESSOR()
   BEGIN_ACCESSOR(1, false) // Not an auto accessor
      COLUMN_ENTRY(3, m_nAge)
   END_ACCESSOR()
END_ACCESSOR_MAP()

   HRESULT OpenDataSource()
   {
      CDataSource _db;
      _db.Open();
      return m_session.Open(_db);
   }

   void CloseDataSource()
   {
      m_session.Close();
   }

   CSession m_session;

   DEFINE_COMMAND_EX(CArtistsAccessor, L" \
   SELECT \
      FirstName, \
      LastName, \
      Age \
      FROM Artists")
};
```

### <a name="end_accessor"></a><a name="end_accessor"></a> END_ACCESSOR

アクセサーエントリの末尾をマークします。

#### <a name="syntax"></a>構文

```cpp
END_ACCESSOR()
```

#### <a name="remarks"></a>解説

行セットの複数のアクセサーについては、BEGIN_ACCESSOR_MAP を指定し、個々のアクセサーに対して BEGIN_ACCESSOR マクロを使用する必要があります。 BEGIN_ACCESSOR マクロは、END_ACCESSOR マクロを使用して完了します。 BEGIN_ACCESSOR_MAP マクロは、END_ACCESSOR_MAP マクロを使用して完了します。

#### <a name="example"></a>例

「 [BEGIN_ACCESSOR_MAP](#begin_accessor_map)」を参照してください。

### <a name="end_accessor_map"></a><a name="end_accessor_map"></a> END_ACCESSOR_MAP

アクセサーマップエントリの末尾をマークします。

#### <a name="syntax"></a>構文

```cpp
END_ACCESSOR_MAP()
```

#### <a name="remarks"></a>解説

行セットの複数のアクセサーについては、BEGIN_ACCESSOR_MAP を指定し、個々のアクセサーに対して BEGIN_ACCESSOR マクロを使用する必要があります。 BEGIN_ACCESSOR マクロは、END_ACCESSOR マクロを使用して完了します。 BEGIN_ACCESSOR_MAP マクロは、END_ACCESSOR_MAP マクロを使用して完了します。

#### <a name="example"></a>例

「 [BEGIN_ACCESSOR_MAP](#begin_accessor_map)」を参照してください。

### <a name="begin_column_map"></a><a name="begin_column_map"></a> BEGIN_COLUMN_MAP

列マップ エントリの先頭を示します。

#### <a name="syntax"></a>構文

```cpp
BEGIN_COLUMN_MAP(x)
```

#### <a name="parameters"></a>パラメーター

*x*<br/>
[入力] `CAccessor`から派生したユーザー レコード クラスの名前。

#### <a name="remarks"></a>解説

このマクロは、行セットに対してアクセサーが 1 つしか必要ない場合に使用します。 1 つの行セットに対して複数のアクセサーが必要な場合は、 [BEGIN_ACCESSOR_MAP](#begin_accessor_map)を使用します。

BEGIN_COLUMN_MAP マクロは、END_COLUMN_MAP マクロを使用して完了します。 このマクロは、ユーザー レコードで 1 つのアクセサーだけが必要な場合に使用します。

列は、バインドする行セットのフィールドに相当します。

#### <a name="example"></a>例

列およびパラメーター マップのコード例を次に示します。

<!--[!CODE [NVC_OLEDB_Consumer#16](../codesnippet/vs_snippets_cpp/nvc_oledb_consumer#16)]  -->

### <a name="blob_entry"></a><a name="blob_entry"></a> BLOB_ENTRY

BEGIN_COLUMN_MAP および END_COLUMN_MAP と共に使用して、バイナリラージオブジェクト ([BLOB](/previous-versions/windows/desktop/ms711511(v=vs.85))) をバインドします。

#### <a name="syntax"></a>構文

```cpp
BLOB_ENTRY(nOrdinal, IID, flags, data)
```

#### <a name="parameters"></a>パラメーター

*nOrdinal*<br/>
から列番号。

*IID*<br/>
から `IDD_ISequentialStream`BLOB を取得するために使用されるなどのインターフェイスの GUID。

*flags*<br/>
からOLE 構造化ストレージモデルで定義されているストレージモードフラグ (たとえば、 `STGM_READ` )。

*data*<br/>
からユーザーレコード内の対応するデータメンバー。

#### <a name="example"></a>例

[BLOB を取得する方法については、](../../data/oledb/retrieving-a-blob.md)「」を参照してください。

### <a name="blob_entry_length"></a><a name="blob_entry_length"></a> BLOB_ENTRY_LENGTH

BEGIN_COLUMN_MAP および END_COLUMN_MAP と共に使用して、バイナリラージオブジェクト ([BLOB](/previous-versions/windows/desktop/ms711511(v=vs.85))) をバインドします。 [BLOB_ENTRY](#blob_entry)に似ていますが、このマクロも BLOB 列の長さをバイト単位で取得する点が異なります。

#### <a name="syntax"></a>構文

```cpp
BLOB_ENTRY_LENGTH(nOrdinal, IID, flags, data, length)
```

#### <a name="parameters"></a>パラメーター

*nOrdinal*<br/>
から列番号。

*IID*<br/>
から `IDD_ISequentialStream`BLOB を取得するために使用されるなどのインターフェイスの GUID。

*flags*<br/>
からOLE 構造化ストレージモデルで定義されているストレージモードフラグ (たとえば、 `STGM_READ` )。

*data*<br/>
からユーザーレコード内の対応するデータメンバー。

*length*<br/>
入出力BLOB 列の (実際の) 長さ (バイト単位)。

#### <a name="example"></a>例

[BLOB を取得する方法については、](../../data/oledb/retrieving-a-blob.md)「」を参照してください。

### <a name="blob_entry_length_status"></a><a name="blob_entry_length_status"></a> BLOB_ENTRY_LENGTH_STATUS

BEGIN_COLUMN_MAP および END_COLUMN_MAP と共に使用して、バイナリラージオブジェクト ([BLOB](/previous-versions/windows/desktop/ms711511(v=vs.85))) をバインドします。 [BLOB_ENTRY](#blob_entry)に似ていますが、このマクロも BLOB 列の長さと状態を取得する点が異なります。

#### <a name="syntax"></a>構文

```cpp
BLOB_ENTRY_LENGTH_STATUS(
    nOrdinal,
    IID,
    flags,
    data,
    length,
    status )
```

#### <a name="parameters"></a>パラメーター

*nOrdinal*<br/>
から列番号。

*IID*<br/>
から `IDD_ISequentialStream`BLOB を取得するために使用されるなどのインターフェイスの GUID。

*flags*<br/>
からOLE 構造化ストレージモデルで定義されているストレージモードフラグ (たとえば、 `STGM_READ` )。

*data*<br/>
からユーザーレコード内の対応するデータメンバー。

*length*<br/>
入出力BLOB 列の (実際の) 長さ (バイト単位)。

*status*<br/>
入出力BLOB データ列の状態です。

#### <a name="example"></a>例

[BLOB を取得する方法については、](../../data/oledb/retrieving-a-blob.md)「」を参照してください。

### <a name="blob_entry_status"></a><a name="blob_entry_status"></a> BLOB_ENTRY_STATUS

BEGIN_COLUMN_MAP または BEGIN_ACCESSOR_MAP と共に使用して、バイナリラージオブジェクト ([BLOB](/previous-versions/windows/desktop/ms711511(v=vs.85))) をバインドします。 [BLOB_ENTRY](#blob_entry)に似ていますが、このマクロは BLOB 列の状態も取得する点が異なります。

#### <a name="syntax"></a>構文

```cpp
BLOB_ENTRY_STATUS(nOrdinal, IID, flags, data, status)
```

#### <a name="parameters"></a>パラメーター

*nOrdinal*<br/>
から列番号。

*IID*<br/>
から `IDD_ISequentialStream`BLOB を取得するために使用されるなどのインターフェイスの GUID。

*flags*<br/>
からOLE 構造化ストレージモデルで定義されているストレージモードフラグ (たとえば、 `STGM_READ` )。

*data*<br/>
からユーザーレコード内の対応するデータメンバー。

*status*<br/>
入出力BLOB フィールドの状態です。

#### <a name="example"></a>例

[BLOB を取得する方法については、](../../data/oledb/retrieving-a-blob.md)「」を参照してください。

### <a name="blob_name"></a><a name="blob_name"></a> BLOB_NAME

BEGIN_COLUMN_MAP および END_COLUMN_MAP と共に使用して、バイナリラージオブジェクト ([BLOB](/previous-versions/windows/desktop/ms711511(v=vs.85))) をバインドします。 [BLOB_ENTRY](#blob_entry)に似ていますが、このマクロは列番号ではなく列名を受け取る点が異なります。

#### <a name="syntax"></a>構文

```cpp
BLOB_NAME(pszName, IID, flags, data )
```

#### <a name="parameters"></a>パラメーター

*pszName*<br/>
から列名へのポインター。 名前は Unicode 文字列である必要があります。 これを行うには、名前の前に ' L ' を挿入します。たとえば、のように指定 `L"MyColumn"` します。

*IID*<br/>
から `IDD_ISequentialStream`BLOB を取得するために使用されるなどのインターフェイスの GUID。

*flags*<br/>
からOLE 構造化ストレージモデルで定義されているストレージモードフラグ (たとえば、 `STGM_READ` )。

*data*<br/>
からユーザーレコード内の対応するデータメンバー。

#### <a name="example"></a>例

[BLOB を取得する方法については、](../../data/oledb/retrieving-a-blob.md)「」を参照してください。

### <a name="blob_name_length"></a><a name="blob_name_length"></a> BLOB_NAME_LENGTH

BEGIN_COLUMN_MAP および END_COLUMN_MAP と共に使用して、バイナリラージオブジェクト ([BLOB](/previous-versions/windows/desktop/ms711511(v=vs.85))) をバインドします。 [BLOB_NAME](#blob_name)に似ていますが、このマクロでも BLOB データ列の長さ (バイト単位) が取得される点が異なります。

#### <a name="syntax"></a>構文

```cpp
BLOB_NAME_LENGTH(pszName, IID, flags, data, length )
```

#### <a name="parameters"></a>パラメーター

*pszName*<br/>
から列名へのポインター。 名前は Unicode 文字列である必要があります。 これを行うには、名前の前に ' L ' を挿入します。たとえば、のように指定 `L"MyColumn"` します。

*IID*<br/>
から `IDD_ISequentialStream`BLOB を取得するために使用されるなどのインターフェイスの GUID。

*flags*<br/>
からOLE 構造化ストレージモデルで定義されているストレージモードフラグ (たとえば、 `STGM_READ` )。

*data*<br/>
からユーザーレコード内の対応するデータメンバー。

*length*<br/>
入出力BLOB 列の (実際の) 長さ (バイト単位)。

### <a name="blob_name_length_status"></a><a name="blob_name_length_status"></a> BLOB_NAME_LENGTH_STATUS

BEGIN_COLUMN_MAP および END_COLUMN_MAP と共に使用して、バイナリラージオブジェクト ([BLOB](/previous-versions/windows/desktop/ms711511(v=vs.85))) をバインドします。 [BLOB_NAME](#blob_name)に似ていますが、このマクロも BLOB データ列の長さと状態を取得する点が異なります。

#### <a name="syntax"></a>構文

```cpp
BLOB_NAME_LENGTH_STATUS(pszName, IID, flags, data, length, status )
```

#### <a name="parameters"></a>パラメーター

*pszName*<br/>
から列名へのポインター。 名前は Unicode 文字列である必要があります。 これを行うには、名前の前に ' L ' を挿入します。たとえば、のように指定 `L"MyColumn"` します。

*IID*<br/>
から `IDD_ISequentialStream`BLOB を取得するために使用されるなどのインターフェイスの GUID。

*flags*<br/>
からOLE 構造化ストレージモデルで定義されているストレージモードフラグ (たとえば、 `STGM_READ` )。

*data*<br/>
からユーザーレコード内の対応するデータメンバー。

*length*<br/>
入出力BLOB 列の (実際の) 長さ (バイト単位)。

*status*<br/>
入出力BLOB フィールドの状態です。

### <a name="blob_name_status"></a><a name="blob_name_status"></a> BLOB_NAME_STATUS

BEGIN_COLUMN_MAP および END_COLUMN_MAP と共に使用して、バイナリラージオブジェクト ([BLOB](/previous-versions/windows/desktop/ms711511(v=vs.85))) をバインドします。 [BLOB_NAME](#blob_name)に似ていますが、このマクロは BLOB データ列の状態も取得する点が異なります。

#### <a name="syntax"></a>構文

```cpp
BLOB_NAME_STATUS(pszName, IID, flags, data, status )
```

#### <a name="parameters"></a>パラメーター

*pszName*<br/>
から列名へのポインター。 名前は Unicode 文字列である必要があります。 これを行うには、名前の前に ' L ' を挿入します。たとえば、のように指定 `L"MyColumn"` します。

*IID*<br/>
から `IDD_ISequentialStream`BLOB を取得するために使用されるなどのインターフェイスの GUID。

*flags*<br/>
からOLE 構造化ストレージモデルで定義されているストレージモードフラグ (たとえば、 `STGM_READ` )。

*data*<br/>
からユーザーレコード内の対応するデータメンバー。

*status*<br/>
入出力BLOB フィールドの状態です。

### <a name="bookmark_entry"></a><a name="bookmark_entry"></a> BOOKMARK_ENTRY

ブックマーク列をバインドします。

#### <a name="syntax"></a>構文

```cpp
BOOKMARK_ENTRY(variable)
```

#### <a name="parameters"></a>パラメーター

*variable*<br/>
からブックマーク列にバインドされる変数。

#### <a name="example"></a>例

```cpp
class CArtistsBookmark
{
public:
// Data Elements
   CBookmark<4> m_bookmark;
   short m_nAge;
   TCHAR m_szFirstName[21];
   TCHAR m_szLastName[31];

// Output binding map
BEGIN_COLUMN_MAP(CArtistsBookmark)
   BOOKMARK_ENTRY(m_bookmark)
   COLUMN_ENTRY(1, m_nAge)
   COLUMN_ENTRY(2, m_szFirstName)
   COLUMN_ENTRY(3, m_szLastName)
END_COLUMN_MAP()

   void GetRowsetProperties(CDBPropSet* pPropSet)
   {
      pPropSet->AddProperty(DBPROP_BOOKMARKS, true);
   }

   HRESULT OpenDataSource()
   {
      CDataSource _db;
      _db.Open();
      return m_session.Open(_db);
   }

   void CloseDataSource()
   {
      m_session.Close();
   }

   CSession m_session;

   DEFINE_COMMAND_EX(CArtistsBookmark, L" \
   SELECT \
      Age, \
      FirstName, \
      LastName \
      FROM Artists")
};
```

詳細については、「 [Using Bookmarks](using-bookmarks.md) And [CBookmark Class](../../data/oledb/cbookmark-class.md)」を参照してください。

### <a name="column_entry"></a><a name="column_entry"></a> COLUMN_ENTRY

行セットのバインドを、行セット内の特定の列に対して表します。

#### <a name="syntax"></a>構文

```cpp
COLUMN_ENTRY(nOrdinal, data)
```

#### <a name="parameters"></a>パラメーター

*OLE DB プログラマーリファレンス* の「 [DBBINDING](/previous-versions/windows/desktop/ms716845(v=vs.85)) 」を参照してください。

*nOrdinal*<br/>
から列番号。

*data*<br/>
からユーザーレコード内の対応するデータメンバー。

#### <a name="remarks"></a>解説

COLUMN_ENTRY マクロは、次の場所で使用されます。

- [BEGIN_COLUMN_MAP](#begin_column_map)と[END_COLUMN_MAP](#end_column_map)のマクロの間。

- [BEGIN_ACCESSOR](#begin_accessor)と[END_ACCESSOR](#end_accessor)のマクロの間。

- [BEGIN_PARAM_MAP](#begin_param_map)と[END_PARAM_MAP](#end_param_map)のマクロの間。

#### <a name="example"></a>例

マクロに関するトピックの例を参照してください。 [BEGIN_COLUMN_MAP](#begin_column_map) と [BEGIN_ACCESSOR_MAP](#begin_accessor_map)です。

### <a name="column_entry_ex"></a><a name="column_entry_ex"></a> COLUMN_ENTRY_EX

行セットのバインドを、データベース内の特定の列に対して表します。

#### <a name="syntax"></a>構文

```cpp
COLUMN_ENTRY_EX(nOrdinal, wType, nLength, nPrecision, nScale, data, length, status)
```

#### <a name="parameters"></a>パラメーター

*OLE DB プログラマーリファレンス* の「 [DBBINDING](/previous-versions/windows/desktop/ms716845(v=vs.85)) 」を参照してください。

*nOrdinal*<br/>
から列番号。

*wType*<br/>
からデータ型。

*nLength*<br/>
からデータサイズ (バイト単位)。

*nPrecision*<br/>
からデータの取得時に使用する最大有効桁数と *Wtype* が `DBTYPE_NUMERIC` です。 それ以外の場合、このパラメーターは無視されます。

*nScale*<br/>
からデータの取得時に使用する小数点以下桁数、および *Wtype* が `DBTYPE_NUMERIC` または `DBTYPE_DECIMAL` です。

*data*<br/>
からユーザーレコード内の対応するデータメンバー。

*length*<br/>
から列の長さにバインドされる変数。

*status*<br/>
から列の状態にバインドされる変数。

#### <a name="remarks"></a>解説

COLUMN_ENTRY_EX マクロは、次の場所で使用されます。

- [BEGIN_COLUMN_MAP](#begin_column_map)と[END_COLUMN_MAP](#end_column_map)のマクロの間。

- [BEGIN_ACCESSOR](#begin_accessor)と[END_ACCESSOR](#end_accessor)のマクロの間。

- [BEGIN_PARAM_MAP](#begin_param_map)と[END_PARAM_MAP](#end_param_map)のマクロの間。

#### <a name="example"></a>例

「 [BOOKMARK_ENTRY](#bookmark_entry)」を参照してください。

### <a name="column_entry_length"></a><a name="column_entry_length"></a> COLUMN_ENTRY_LENGTH

行セットのバインドを、データベース内の特定の列に対して表します。

#### <a name="syntax"></a>構文

```cpp
COLUMN_ENTRY_LENGTH(nOrdinal, data, length)
```

#### <a name="parameters"></a>パラメーター

*OLE DB プログラマーリファレンス* の「 [DBBINDING](/previous-versions/windows/desktop/ms716845(v=vs.85)) 」を参照してください。

*nOrdinal*<br/>
から1から始まる列番号。 ブックマークは列0に対応します。

*data*<br/>
からユーザーレコード内の対応するデータメンバー。

*length*<br/>
から列の長さにバインドされる変数。

#### <a name="remarks"></a>解説

このマクロは、 *長さ* の変数をサポートします。 これは次の場所で使用されます。

- [BEGIN_COLUMN_MAP](#begin_column_map)と[END_COLUMN_MAP](#end_column_map)のマクロの間。

- [BEGIN_ACCESSOR](#begin_accessor)と[END_ACCESSOR](#end_accessor)のマクロの間。

- [BEGIN_PARAM_MAP](#begin_param_map)と[END_PARAM_MAP](#end_param_map)のマクロの間。

### <a name="column_entry_length_status"></a><a name="column_entry_length_status"></a> COLUMN_ENTRY_LENGTH_STATUS

行セットのバインドを、データベース内の特定の列に対して表します。

#### <a name="syntax"></a>構文

```cpp
COLUMN_ENTRY_LENGTH_STATUS(nOrdinal, data, length, status)
```

#### <a name="parameters"></a>パラメーター

*OLE DB プログラマーリファレンス* の「 [DBBINDING](/previous-versions/windows/desktop/ms716845(v=vs.85)) 」を参照してください。

*nOrdinal*<br/>
から列番号。

*data*<br/>
からユーザーレコード内の対応するデータメンバー。

*length*<br/>
から列の長さにバインドされる変数。

*status*<br/>
から列の状態にバインドされる変数。

#### <a name="remarks"></a>解説

このマクロは、長さと状態の変数をサポートする場合に使用します。 これは次の場所で使用されます。

- [BEGIN_COLUMN_MAP](#begin_column_map)と[END_COLUMN_MAP](#end_column_map)のマクロの間。

- [BEGIN_ACCESSOR](#begin_accessor)と[END_ACCESSOR](#end_accessor)のマクロの間。

- [BEGIN_PARAM_MAP](#begin_param_map)と[END_PARAM_MAP](#end_param_map)のマクロの間。

### <a name="column_entry_ps"></a><a name="column_entry_ps"></a> COLUMN_ENTRY_PS

行セットのバインドを、行セット内の特定の列に対して表します。

#### <a name="syntax"></a>構文

```cpp
COLUMN_ENTRY_PS(nOrdinal, nPrecision, nScale, data)
```

#### <a name="parameters"></a>パラメーター

*OLE DB プログラマーリファレンス* の「 [DBBINDING](/previous-versions/windows/desktop/ms716845(v=vs.85)) 」を参照してください。

*nOrdinal*<br/>
から列番号。

*nPrecision*<br/>
からバインドする列の最大有効桁数。

*nScale*<br/>
からバインドする列の小数点以下桁数です。

*data*<br/>
からユーザーレコード内の対応するデータメンバー。

#### <a name="remarks"></a>解説

バインドする列の有効桁数と小数点以下桁数を指定できます。 これは次の場所で使用されます。

- [BEGIN_COLUMN_MAP](#begin_column_map)と[END_COLUMN_MAP](#end_column_map)のマクロの間。

- [BEGIN_ACCESSOR](#begin_accessor)と[END_ACCESSOR](#end_accessor)のマクロの間。

- [BEGIN_PARAM_MAP](#begin_param_map)と[END_PARAM_MAP](#end_param_map)のマクロの間。

### <a name="column_entry_ps_length"></a><a name="column_entry_ps_length"></a> COLUMN_ENTRY_PS_LENGTH

行セットのバインドを、データベース内の特定の列に対して表します。

#### <a name="syntax"></a>構文

```cpp
COLUMN_ENTRY_PS_LENGTH(nOrdinal, nPrecision, nScale, data, length)
```

#### <a name="parameters"></a>パラメーター

*OLE DB プログラマーリファレンス* の「 [DBBINDING](/previous-versions/windows/desktop/ms716845(v=vs.85)) 」を参照してください。

*nOrdinal*<br/>
から1から始まる列番号。 ブックマークは列0に対応します。

*nPrecision*<br/>
からバインドする列の最大有効桁数。

*nScale*<br/>
からバインドする列の小数点以下桁数です。

*data*<br/>
からユーザーレコード内の対応するデータメンバー。

*length*<br/>
から列の長さにバインドされる変数。

#### <a name="remarks"></a>解説

バインドする列の有効桁数と小数点以下桁数を指定できます。 このマクロは、 *長さ* の変数をサポートします。 これは次の場所で使用されます。

- [BEGIN_COLUMN_MAP](#begin_column_map)と[END_COLUMN_MAP](#end_column_map)のマクロの間。

- [BEGIN_ACCESSOR](#begin_accessor)と[END_ACCESSOR](#end_accessor)のマクロの間。

- [BEGIN_PARAM_MAP](#begin_param_map)と[END_PARAM_MAP](#end_param_map)のマクロの間。

### <a name="column_entry_ps_length_status"></a><a name="column_entry_ps_length_status"></a> COLUMN_ENTRY_PS_LENGTH_STATUS

行セットのバインドを、データベース内の特定の列に対して表します。

#### <a name="syntax"></a>構文

```cpp
COLUMN_ENTRY_PS_LENGTH_STATUS(nOrdinal, nPrecision, nScale, data, length, status)
```

#### <a name="parameters"></a>パラメーター

*OLE DB プログラマーリファレンス* の「 [DBBINDING](/previous-versions/windows/desktop/ms716845(v=vs.85)) 」を参照してください。

*nOrdinal*<br/>
から列番号。

*nPrecision*<br/>
からバインドする列の最大有効桁数。

*nScale*<br/>
からバインドする列の小数点以下桁数です。

*data*<br/>
からユーザーレコード内の対応するデータメンバー。

*length*<br/>
から列の長さにバインドされる変数。

*status*<br/>
から列の状態にバインドされる変数。

#### <a name="remarks"></a>解説

バインドする列の有効桁数と小数点以下桁数を指定できます。 このマクロは、長さと状態の変数をサポートする場合に使用します。 これは次の場所で使用されます。

- [BEGIN_COLUMN_MAP](#begin_column_map)と[END_COLUMN_MAP](#end_column_map)のマクロの間。

- [BEGIN_ACCESSOR](#begin_accessor)と[END_ACCESSOR](#end_accessor)のマクロの間。

- [BEGIN_PARAM_MAP](#begin_param_map)と[END_PARAM_MAP](#end_param_map)のマクロの間。

### <a name="column_entry_ps_status"></a><a name="column_entry_ps_status"></a> COLUMN_ENTRY_PS_STATUS

行セットのバインドを、データベース内の特定の列に対して表します。

#### <a name="syntax"></a>構文

```cpp
COLUMN_ENTRY_PS_STATUS(nOrdinal, nPrecision, nScale, data, status)
```

#### <a name="parameters"></a>パラメーター

*OLE DB プログラマーリファレンス* の「 [DBBINDING](/previous-versions/windows/desktop/ms716845(v=vs.85)) 」を参照してください。

*nOrdinal*<br/>
から列番号。

*nPrecision*<br/>
からバインドする列の最大有効桁数。

*nScale*<br/>
からバインドする列の小数点以下桁数です。

*data*<br/>
からユーザーレコード内の対応するデータメンバー。

*status*<br/>
から列の状態にバインドされる変数。

#### <a name="remarks"></a>解説

バインドする列の有効桁数と小数点以下桁数を指定できます。 このマクロは、 *status* 変数をサポートしています。 これは次の場所で使用されます。

- [BEGIN_COLUMN_MAP](#begin_column_map)と[END_COLUMN_MAP](#end_column_map)のマクロの間。

- [BEGIN_ACCESSOR](#begin_accessor)と[END_ACCESSOR](#end_accessor)のマクロの間。

- [BEGIN_PARAM_MAP](#begin_param_map)と[END_PARAM_MAP](#end_param_map)のマクロの間。

### <a name="column_entry_status"></a><a name="column_entry_status"></a> COLUMN_ENTRY_STATUS

行セットのバインドを、データベース内の特定の列に対して表します。

#### <a name="syntax"></a>構文

```cpp
COLUMN_ENTRY_STATUS(nOrdinal, data, status)
```

#### <a name="parameters"></a>パラメーター

*OLE DB プログラマーリファレンス* の「 [DBBINDING](/previous-versions/windows/desktop/ms716845(v=vs.85)) 」を参照してください。

*nOrdinal*<br/>
から列番号。

*data*<br/>
からユーザーレコード内の対応するデータメンバー。

*status*<br/>
から列の状態にバインドされる変数。

#### <a name="remarks"></a>解説

このマクロは、 *status* 変数をサポートしています。 これは次の場所で使用されます。

- [BEGIN_COLUMN_MAP](#begin_column_map)と[END_COLUMN_MAP](#end_column_map)のマクロの間。

- [BEGIN_ACCESSOR](#begin_accessor)と[END_ACCESSOR](#end_accessor)のマクロの間。

- [BEGIN_PARAM_MAP](#begin_param_map)と[END_PARAM_MAP](#end_param_map)のマクロの間。

### <a name="column_entry_type"></a><a name="column_entry_type"></a> COLUMN_ENTRY_TYPE

データベース内の特定の列へのバインドを表します。 *型* パラメーターをサポートします。

#### <a name="syntax"></a>構文

```cpp
COLUMN_ENTRY_TYPE (nOrdinal, wType, data)
```

#### <a name="parameters"></a>パラメーター

*nOrdinal*<br/>
から列番号。

*wType*<br/>
から列エントリのデータ型。

*data*<br/>
からユーザーレコード内の対応するデータメンバー。

#### <a name="remarks"></a>解説

このマクロは、データ型を指定する手段を提供する [COLUMN_ENTRY](#column_entry) マクロの特殊なバリアントです。

### <a name="column_entry_type_size"></a><a name="column_entry_type_size"></a> COLUMN_ENTRY_TYPE_SIZE

データベース内の特定の列へのバインドを表します。 では、 *型* パラメーターと *サイズ* パラメーターがサポートされています。

#### <a name="syntax"></a>構文

```cpp
COLUMN_ENTRY_TYPE_SIZE(nOrdinal, wType, nLength, data)
```

#### <a name="parameters"></a>パラメーター

*nOrdinal*<br/>
から列番号。

*wType*<br/>
から列エントリのデータ型。

*nLength*<br/>
から列エントリのサイズ (バイト単位)。

*data*<br/>
からユーザーレコード内の対応するデータメンバー。

#### <a name="remarks"></a>解説

このマクロは、データサイズと型を指定する手段を提供する、 [COLUMN_ENTRY](#column_entry) マクロの特殊なバリアントです。

### <a name="column_name"></a><a name="column_name"></a> COLUMN_NAME

行セットのバインドを、行セット内の特定の列に対して表します。 [COLUMN_ENTRY](#column_entry)に似ていますが、このマクロは列番号ではなく列名を受け取る点が異なります。

#### <a name="syntax"></a>構文

```cpp
COLUMN_NAME(pszName, data)
```

#### <a name="parameters"></a>パラメーター

*pszName*<br/>
から列名へのポインター。 名前は Unicode 文字列である必要があります。 これを行うには、名前の前に ' L ' を挿入します。たとえば、のように指定 `L"MyColumn"` します。

*data*<br/>
からユーザーレコード内の対応するデータメンバー。

#### <a name="remarks"></a>解説

COLUMN_NAME_ * マクロは、 [COLUMN_ENTRY](#column_entry)と同じ場所で使用されます。

- [BEGIN_COLUMN_MAP](#begin_column_map)と[END_COLUMN_MAP](#end_column_map)のマクロの間。

- [BEGIN_ACCESSOR](#begin_accessor)と[END_ACCESSOR](#end_accessor)のマクロの間。

- [BEGIN_PARAM_MAP](#begin_param_map)と[END_PARAM_MAP](#end_param_map)のマクロの間。

### <a name="column_name_ex"></a><a name="column_name_ex"></a> COLUMN_NAME_EX

行セットのバインドを、行セット内の特定の列に対して表します。 [COLUMN_NAME](#column_name)に似ていますが、このマクロもデータ型、サイズ、有効桁数、小数点以下桁数、列の長さ、列の状態を取得する点が異なります。

#### <a name="syntax"></a>構文

```cpp
COLUMN_NAME_EX(pszName, wType, nLength, nPrecision, nScale, data, length, status )
```

#### <a name="parameters"></a>パラメーター

*pszName*<br/>
から列名へのポインター。 名前は Unicode 文字列である必要があります。 これを行うには、名前の前に ' L ' を挿入します。たとえば、のように指定 `L"MyColumn"` します。

*wType*<br/>
からデータ型。

*nLength*<br/>
からデータサイズ (バイト単位)。

*nPrecision*<br/>
からデータの取得時に使用する最大有効桁数と *Wtype* が `DBTYPE_NUMERIC` です。 それ以外の場合、このパラメーターは無視されます。

*nScale*<br/>
からデータの取得時に使用する小数点以下桁数、および *Wtype* が `DBTYPE_NUMERIC` または `DBTYPE_DECIMAL` です。

*data*<br/>
からユーザーレコード内の対応するデータメンバー。

*length*<br/>
から列の長さにバインドされる変数。

*status*<br/>
から列の状態にバインドされる変数。

#### <a name="remarks"></a>解説

COLUMN_NAME_ * マクロを使用する場所の詳細については、「 [COLUMN_NAME](#column_name) 」を参照してください。

### <a name="column_name_length"></a><a name="column_name_length"></a> COLUMN_NAME_LENGTH

行セットのバインドを、行セット内の特定の列に対して表します。 [COLUMN_NAME](#column_name)に似ていますが、このマクロも列長をとります。

#### <a name="syntax"></a>構文

```cpp
COLUMN_NAME_LENGTH(pszName, data, length)
```

#### <a name="parameters"></a>パラメーター

*pszName*<br/>
から列名へのポインター。 名前は Unicode 文字列である必要があります。 これを行うには、名前の前に ' L ' を挿入します。たとえば、のように指定 `L"MyColumn"` します。

*data*<br/>
からユーザーレコード内の対応するデータメンバー。

*length*<br/>
から列の長さにバインドされる変数。

#### <a name="remarks"></a>解説

COLUMN_NAME_ * マクロを使用する場所の詳細については、「 [COLUMN_NAME](#column_name) 」を参照してください。

### <a name="column_name_length_status"></a><a name="column_name_length_status"></a> COLUMN_NAME_LENGTH_STATUS

行セットのバインドを、行セット内の特定の列に対して表します。 [COLUMN_NAME](#column_name)に似ていますが、このマクロも列の長さと列の状態を取得する点が異なります。

#### <a name="syntax"></a>構文

```cpp
COLUMN_NAME_LENGTH_STATUS(pszName, data, length, status )
```

#### <a name="parameters"></a>パラメーター

*pszName*<br/>
から列名へのポインター。 名前は Unicode 文字列である必要があります。 これを行うには、名前の前に ' L ' を挿入します。たとえば、のように指定 `L"MyColumn"` します。

*data*<br/>
からユーザーレコード内の対応するデータメンバー。

*length*<br/>
から列の長さにバインドされる変数。

*status*<br/>
から列の状態にバインドされる変数。

#### <a name="remarks"></a>解説

COLUMN_NAME_ * マクロを使用する場所の詳細については、「 [COLUMN_NAME](#column_name) 」を参照してください。

### <a name="column_name_ps"></a><a name="column_name_ps"></a> COLUMN_NAME_PS

行セットのバインドを、行セット内の特定の列に対して表します。 [COLUMN_NAME](#column_name)に似ていますが、このマクロも有効桁数と小数点以下桁数が異なります。

#### <a name="syntax"></a>構文

```cpp
COLUMN_NAME_PS(pszName, nPrecision, nScale, data )
```

#### <a name="parameters"></a>パラメーター

*pszName*<br/>
から列名へのポインター。 名前は Unicode 文字列である必要があります。 これを行うには、名前の前に ' L ' を挿入します。たとえば、のように指定 `L"MyColumn"` します。

*nPrecision*<br/>
からバインドする列の最大有効桁数。

*nScale*<br/>
からバインドする列の小数点以下桁数です。

*data*<br/>
からユーザーレコード内の対応するデータメンバー。

#### <a name="remarks"></a>解説

COLUMN_NAME_ * マクロを使用する場所の詳細については、「 [COLUMN_NAME](#column_name) 」を参照してください。

### <a name="column_name_ps_length"></a><a name="column_name_ps_length"></a> COLUMN_NAME_PS_LENGTH

行セットのバインドを、行セット内の特定の列に対して表します。 [COLUMN_NAME](#column_name)に似ていますが、このマクロでも有効桁数、小数点以下桁数、および列の長さが必要です。

#### <a name="syntax"></a>構文

```cpp
COLUMN_NAME_PS_LENGTH(pszName, nPrecision, nScale, data, length )
```

#### <a name="parameters"></a>パラメーター

*pszName*<br/>
から列名へのポインター。 名前は Unicode 文字列である必要があります。 これを行うには、名前の前に ' L ' を挿入します。たとえば、のように指定 `L"MyColumn"` します。

*nPrecision*<br/>
からバインドする列の最大有効桁数。

*nScale*<br/>
からバインドする列の小数点以下桁数です。

*data*<br/>
からユーザーレコード内の対応するデータメンバー。

*length*<br/>
から列の長さにバインドされる変数。

#### <a name="remarks"></a>解説

COLUMN_NAME_ * マクロを使用する場所の詳細については、「 [COLUMN_NAME](#column_name) 」を参照してください。

### <a name="column_name_ps_length_status"></a><a name="column_name_ps_length_status"></a> COLUMN_NAME_PS_LENGTH_STATUS

行セットのバインドを、行セット内の特定の列に対して表します。 [COLUMN_NAME](#column_name)に似ていますが、このマクロでは、有効桁数、小数点以下桁数、列の長さ、および列の状態も取得します。

#### <a name="syntax"></a>構文

```cpp
COLUMN_NAME_PS_LENGTH_STATUS(pszName, nPrecision, nScale, data, length, status )
```

#### <a name="parameters"></a>パラメーター

*pszName*<br/>
から列名へのポインター。 名前は Unicode 文字列である必要があります。 これを行うには、名前の前に ' L ' を挿入します。たとえば、のように指定 `L"MyColumn"` します。

*nPrecision*<br/>
からバインドする列の最大有効桁数。

*nScale*<br/>
からバインドする列の小数点以下桁数です。

*data*<br/>
からユーザーレコード内の対応するデータメンバー。

*length*<br/>
から列の長さにバインドされる変数。

*status*<br/>
から列の状態にバインドされる変数。

#### <a name="remarks"></a>解説

COLUMN_NAME_ * マクロを使用する場所の詳細については、「 [COLUMN_NAME](#column_name) 」を参照してください。

### <a name="column_name_ps_status"></a><a name="column_name_ps_status"></a> COLUMN_NAME_PS_STATUS

行セットのバインドを、行セット内の特定の列に対して表します。 [COLUMN_NAME](#column_name)に似ていますが、このマクロも有効桁数、小数点以下桁数、および列の状態を取得する点が異なります。

#### <a name="syntax"></a>構文

```cpp
COLUMN_NAME_PS_STATUS(pszName, nPrecision, nScale, data, status )
```

#### <a name="parameters"></a>パラメーター

*pszName*<br/>
から列名へのポインター。 名前は Unicode 文字列である必要があります。 これを行うには、名前の前に ' L ' を挿入します。たとえば、のように指定 `L"MyColumn"` します。

*nPrecision*<br/>
からバインドする列の最大有効桁数。

*nScale*<br/>
からバインドする列の小数点以下桁数です。

*data*<br/>
からユーザーレコード内の対応するデータメンバー。

*status*<br/>
から列の状態にバインドされる変数。

#### <a name="remarks"></a>解説

COLUMN_NAME_ * マクロを使用する場所の詳細については、「 [COLUMN_NAME](#column_name) 」を参照してください。

### <a name="column_name_status"></a><a name="column_name_status"></a> COLUMN_NAME_STATUS

行セットのバインドを、行セット内の特定の列に対して表します。 [COLUMN_NAME](#column_name)に似ていますが、このマクロも列の状態を取得する点が異なります。

#### <a name="syntax"></a>構文

```cpp
COLUMN_NAME_STATUS(pszName, data, status )
```

#### <a name="parameters"></a>パラメーター

*pszName*<br/>
から列名へのポインター。 名前は Unicode 文字列である必要があります。 これを行うには、名前の前に ' L ' を挿入します。たとえば、のように指定 `L"MyColumn"` します。

*data*<br/>
からユーザーレコード内の対応するデータメンバー。

*status*<br/>
から列の状態にバインドされる変数。

#### <a name="remarks"></a>解説

COLUMN_NAME_ * マクロを使用する場所の詳細については、「 [COLUMN_NAME](#column_name) 」を参照してください。

### <a name="column_name_type"></a><a name="column_name_type"></a> COLUMN_NAME_TYPE

行セットのバインドを、行セット内の特定の列に対して表します。 [COLUMN_NAME](#column_name)に似ていますが、このマクロもデータ型を受け取る点が異なります。

#### <a name="syntax"></a>構文

```cpp
COLUMN_NAME_TYPE(pszName, wType, data)
```

#### <a name="parameters"></a>パラメーター

*pszName*<br/>
から列名へのポインター。 名前は Unicode 文字列である必要があります。 これを行うには、名前の前に ' L ' を挿入します。たとえば、のように指定 `L"MyColumn"` します。

*wType*<br/>
からデータ型。

*data*<br/>
からユーザーレコード内の対応するデータメンバー。

#### <a name="remarks"></a>解説

COLUMN_NAME_ * マクロを使用する場所の詳細については、「 [COLUMN_NAME](#column_name) 」を参照してください。

### <a name="column_name_type_ps"></a><a name="column_name_type_ps"></a> COLUMN_NAME_TYPE_PS

行セットのバインドを、行セット内の特定の列に対して表します。 [COLUMN_NAME](#column_name)に似ていますが、このマクロもデータ型、有効桁数、および小数点以下桁数を取得します。

#### <a name="syntax"></a>構文

```cpp
COLUMN_NAME_TYPE_PS(pszName, wType, nPrecision, nScale, data)
```

#### <a name="parameters"></a>パラメーター

*pszName*<br/>
から列名へのポインター。 名前は Unicode 文字列である必要があります。 これを行うには、名前の前に ' L ' を挿入します。たとえば、のように指定 `L"MyColumn"` します。

*wType*<br/>
からデータ型。

*nPrecision*<br/>
からデータの取得時に使用する最大有効桁数と *Wtype* が `DBTYPE_NUMERIC` です。 それ以外の場合、このパラメーターは無視されます。

*nScale*<br/>
からデータの取得時に使用する小数点以下桁数、および *Wtype* が `DBTYPE_NUMERIC` または `DBTYPE_DECIMAL` です。

*data*<br/>
からユーザーレコード内の対応するデータメンバー。

#### <a name="remarks"></a>解説

COLUMN_NAME_ * マクロを使用する場所の詳細については、「 [COLUMN_NAME](#column_name) 」を参照してください。

### <a name="column_name_type_size"></a><a name="column_name_type_size"></a> COLUMN_NAME_TYPE_SIZE

行セットのバインドを、行セット内の特定の列に対して表します。 [COLUMN_NAME](#column_name)と似ていますが、このマクロもデータ型とサイズを取得する点が異なります。

#### <a name="syntax"></a>構文

```cpp
COLUMN_NAME_TYPE_SIZE(pszName, wType, nLength, data)
```

#### <a name="parameters"></a>パラメーター

*pszName*<br/>
から列名へのポインター。 名前は Unicode 文字列である必要があります。 これを行うには、名前の前に ' L ' を挿入します。たとえば、のように指定 `L"MyColumn"` します。

*wType*<br/>
からデータ型。

*nLength*<br/>
からデータサイズ (バイト単位)。

*data*<br/>
からユーザーレコード内の対応するデータメンバー。

#### <a name="remarks"></a>解説

COLUMN_NAME_ * マクロを使用する場所の詳細については、「 [COLUMN_NAME](#column_name) 」を参照してください。

### <a name="column_name_type_status"></a><a name="column_name_type_status"></a> COLUMN_NAME_TYPE_STATUS

行セットのバインドを、行セット内の特定の列に対して表します。 [COLUMN_NAME](#column_name)に似ていますが、このマクロでもデータ型と列の状態が取得される点が異なります。

#### <a name="syntax"></a>構文

```cpp
COLUMN_NAME_TYPE_STATUS(pszName, wType, status, data)
```

#### <a name="parameters"></a>パラメーター

*pszName*<br/>
から列名へのポインター。 名前は Unicode 文字列である必要があります。 これを行うには、名前の前に ' L ' を挿入します。たとえば、のように指定 `L"MyColumn"` します。

*wType*<br/>
からデータ型。

*status*<br/>
から列の状態にバインドされる変数。

*data*<br/>
からユーザーレコード内の対応するデータメンバー。

#### <a name="remarks"></a>解説

COLUMN_NAME_ * マクロを使用する場所の詳細については、「 [COLUMN_NAME](#column_name) 」を参照してください。

### <a name="end_column_map"></a><a name="end_column_map"></a> END_COLUMN_MAP

列マップエントリの末尾をマークします。

#### <a name="syntax"></a>構文

```cpp
END_COLUMN_MAP()
```

#### <a name="remarks"></a>解説

これは、行セットの1つのアクセサーと共に使用されます。 BEGIN_COLUMN_MAP マクロは、END_COLUMN_MAP マクロを使用して完了します。

#### <a name="example"></a>例

「 [BEGIN_COLUMN_MAP](#begin_column_map)」を参照してください。

### <a name="define_command"></a><a name="define_command"></a> DEFINE_COMMAND

[CCommand](../../data/oledb/ccommand-class.md)クラスを使用するときに行セットを作成するために使用されるコマンドを指定します。 指定されたアプリケーションの種類 (ANSI または Unicode) に一致する文字列型のみを受け入れます。

> [!NOTE]
> DEFINE_COMMAND ではなく [DEFINE_COMMAND_EX](#define_command_ex) を使用することをお勧めします。

#### <a name="syntax"></a>構文

```cpp
DEFINE_COMMAND(x, szCommand)
```

#### <a name="parameters"></a>パラメーター

*x*<br/>
からユーザーレコード (コマンド) クラスの名前。

*szCommand*<br/>
から [CCommand](../../data/oledb/ccommand-class.md)を使用するときに行セットを作成するために使用されるコマンド文字列。

#### <a name="remarks"></a>解説

[CCommand:: Open](./ccommand-class.md#open)メソッドでコマンドテキストを指定しない場合、指定したコマンド文字列が既定値として使用されます。

アプリケーションを ANSI としてビルドする場合、または unicode としてアプリケーションをビルドする場合は Unicode 文字列を使用します。 DEFINE_COMMAND ではなく [DEFINE_COMMAND_EX](#define_command_ex) を使用することをお勧めします。これは、ANSI または unicode のアプリケーションの種類に関係なく、unicode 文字列を許可するためです。

#### <a name="example"></a>例

「 [BOOKMARK_ENTRY](#bookmark_entry)」を参照してください。

### <a name="define_command_ex"></a><a name="define_command_ex"></a> DEFINE_COMMAND_EX

[CCommand](../../data/oledb/ccommand-class.md)クラスを使用するときに行セットを作成するために使用されるコマンドを指定します。 Unicode および ANSI アプリケーションをサポートします。

#### <a name="syntax"></a>構文

```cpp
DEFINE_COMMAND_EX(x, wszCommand)
```

#### <a name="parameters"></a>パラメーター

*x*<br/>
からユーザーレコード (コマンド) クラスの名前。

*wszCommand*<br/>
から [CCommand](../../data/oledb/ccommand-class.md)を使用するときに行セットを作成するために使用されるコマンド文字列。

#### <a name="remarks"></a>解説

[CCommand:: Open](./ccommand-class.md#open)メソッドでコマンドテキストを指定しない場合、指定したコマンド文字列が既定値として使用されます。

このマクロは、アプリケーションの種類に関係なく、Unicode 文字列を受け入れます。 このマクロは、Unicode と ANSI アプリケーションをサポートしているため、 [DEFINE_COMMAND](#define_command) よりも優先されます。

#### <a name="example"></a>例

「 [BOOKMARK_ENTRY](#bookmark_entry)」を参照してください。

### <a name="begin_param_map"></a><a name="begin_param_map"></a> BEGIN_PARAM_MAP

パラメーターマップエントリの先頭をマークします。

#### <a name="syntax"></a>構文

```cpp
BEGIN_PARAM_MAP(x)
```

#### <a name="parameters"></a>パラメーター

*x*<br/>
[入力] ユーザー レコード クラスの名前。

#### <a name="remarks"></a>解説

パラメーターは [コマンド](/previous-versions/windows/desktop/ms724608(v=vs.85))によって使用されます。

#### <a name="example"></a>例

[BEGIN_COLUMN_MAP](#begin_column_map)マクロの例を参照してください。

### <a name="end_param_map"></a><a name="end_param_map"></a> END_PARAM_MAP

パラメーターマップエントリの末尾をマークします。

#### <a name="syntax"></a>構文

```cpp
END_PARAM_MAP()
```

#### <a name="example"></a>例

[BEGIN_PARAM_MAP](#begin_param_map)マクロの例を参照してください。

### <a name="set_param_type"></a><a name="set_param_type"></a> SET_PARAM_TYPE

SET_PARAM_TYPE マクロ入力、出力、または入力/出力に続くマクロ COLUMN_ENTRY を指定します。

#### <a name="syntax"></a>構文

```cpp
SET_PARAM_TYPE(type)
```

#### <a name="parameters"></a>パラメーター

*type*<br/>
[入力] 設定するパラメーターの種類。

#### <a name="remarks"></a>解説

プロバイダーは、基になるデータ ソースによってサポートされているパラメーター入出力タイプだけをサポートします。 型は1つ以上の値の組み合わせです `DBPARAMIO` ( *OLE DB プログラマーリファレンス* の「 [DBBINDING 構造体](/previous-versions/windows/desktop/ms716845(v=vs.85))」を参照してください)。

- `DBPARAMIO_NOTPARAM` アクセサーにはパラメーターがありません。 通常、 `eParamIO` 行アクセサーでは、この値をに設定して、パラメーターが無視されることをユーザーに通知します。

- `DBPARAMIO_INPUT` 入力パラメーター。

- `DBPARAMIO_OUTPUT` 出力パラメーター。

- `DBPARAMIO_INPUT | DBPARAMIO_OUTPUT` パラメーターは、入力パラメーターと出力パラメーターの両方です。

#### <a name="example"></a>例

```cpp
class CArtistsProperty
{
public:
   short m_nReturn;
   short m_nAge;
   TCHAR m_szFirstName[21];
   TCHAR m_szLastName[31];

BEGIN_PARAM_MAP(CArtistsProperty)
   SET_PARAM_TYPE(DBPARAMIO_OUTPUT)
   COLUMN_ENTRY(1, m_nReturn)
   SET_PARAM_TYPE(DBPARAMIO_INPUT)
   COLUMN_ENTRY(2, m_nAge)
END_PARAM_MAP()

BEGIN_COLUMN_MAP(CArtistsProperty)
   COLUMN_ENTRY(1, m_szFirstName)
   COLUMN_ENTRY(2, m_szLastName)
END_COLUMN_MAP()

   HRESULT OpenDataSource()
   {
      CDataSource _db;
      _db.Open();
      return m_session.Open(_db);
   }

   void CloseDataSource()
   {
      m_session.Close();
   }

   CSession m_session;

   DEFINE_COMMAND_EX(CArtistsProperty, L" \
      { ? = SELECT Age FROM Artists WHERE Age < ? }")
};
```

## <a name="requirements"></a>要件

**ヘッダー:** atldbcli.h

## <a name="see-also"></a>関連項目

[OLE DB コンシューマーテンプレートのマクロとグローバル関数](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)<br/>
[OLE DB コンシューマー テンプレート](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB コンシューマーテンプレートリファレンス](../../data/oledb/ole-db-consumer-templates-reference.md)
