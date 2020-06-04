---
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
ms.openlocfilehash: 8b898990672f590f6047eef6fdfd1ed7eecb3f92
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369819"
---
# <a name="macros-and-global-functions-for-ole-db-consumer-templates"></a>OLE DB コンシューマー テンプレート用マクロおよびグローバル関数

OLE DB コンシューマー テンプレートには、次のマクロとグローバル関数が含まれています。

## <a name="global-functions"></a>グローバル関数

|||
|-|-|
|[AtlTraceErrorRecords](#atltraceerrorrecords)|エラーが返された場合に、OLE DB エラー レコード情報をダンプ デバイスにダンプします。|

## <a name="accessor-map-macros"></a>アクセサマップマクロ

|||
|-|-|
|[BEGIN_ACCESSOR](#begin_accessor)|アクセサー エントリの先頭を示します。|
|[BEGIN_ACCESSOR_MAP](#begin_accessor_map)|アクセサー マップ エントリの開始位置を示します。|
|[END_ACCESSOR](#end_accessor)|アクセサー エントリの末尾を示します。|
|[END_ACCESSOR_MAP](#end_accessor_map)|アクセサ マップ エントリの末尾をマークします。|

## <a name="column-map-macros"></a>列マップ マクロ

|||
|-|-|
|[BEGIN_COLUMN_MAP](#begin_column_map)|ユーザー レコード クラスの列マップ エントリの先頭をマークします。|
|[BLOB_ENTRY](#blob_entry)|バイナリ ラージ オブジェクト (BLOB) をバインドするために使用します。|
|[BLOB_ENTRY_LENGTH](#blob_entry_length)|BLOB データ列の長さを報告します。|
|[BLOB_ENTRY_LENGTH_STATUS](#blob_entry_length_status)|BLOB データ列の長さと状態を報告します。|
|[BLOB_ENTRY_STATUS](#blob_entry_status)|BLOB データ列の状態を報告します。|
|[BLOB_NAME](#blob_name)|バイナリ ラージ オブジェクトを列名でバインドするために使用します。|
|[BLOB_NAME_LENGTH](#blob_name_length)|BLOB データ列の長さを報告します。|
|[BLOB_NAME_LENGTH_STATUS](#blob_name_length_status)|BLOB データ列の長さと状態を報告します。|
|[BLOB_NAME_STATUS](#blob_name_status)|BLOB データ列の状態を報告します。|
|[BOOKMARK_ENTRY](#bookmark_entry)|行セットのブックマーク エントリを表します。 ブックマークエントリは、特殊な種類の列エントリです。|
|[COLUMN_ENTRY](#column_entry)|データベース内の特定の列へのバインディングを表します。|
|[COLUMN_ENTRY_EX](#column_entry_ex)|データベース内の特定の列へのバインディングを表します。 *型*、*長さ*、*精度*、*スケール*、および*状態*の各パラメーターをサポートします。|
|[COLUMN_ENTRY_LENGTH](#column_entry_length)|データベース内の特定の列へのバインディングを表します。 *長さ*変数をサポートします。|
|[COLUMN_ENTRY_LENGTH_STATUS](#column_entry_length_status)|データベース内の特定の列へのバインディングを表します。 *ステータス*と*長さの*パラメータをサポートします。|
|[COLUMN_ENTRY_PS](#column_entry_ps)|データベース内の特定の列へのバインディングを表します。 *精度*と*スケール*のパラメータをサポートします。|
|[COLUMN_ENTRY_PS_LENGTH](#column_entry_ps_length)|データベース内の特定の列へのバインディングを表します。 *長さの*変数、*精度*および*スケール*のパラメーターをサポートします。|
|[COLUMN_ENTRY_PS_LENGTH_STATUS](#column_entry_ps_length_status)|データベース内の特定の列へのバインディングを表します。 *ステータス*変数と*長さの*変数、*精度*と*スケール*のパラメータをサポートします。|
|[COLUMN_ENTRY_PS_STATUS](#column_entry_ps_status)|データベース内の特定の列へのバインディングを表します。 *ステータス*変数、*精度*、*およびスケール*のパラメータをサポートします。|
|[COLUMN_ENTRY_STATUS](#column_entry_status)|データベース内の特定の列へのバインディングを表します。 *ステータス*変数をサポートします。|
|[COLUMN_ENTRY_TYPE](#column_entry_type)|データベース内の特定の列へのバインディングを表します。 *型パラメーターを*サポートします。|
|[COLUMN_ENTRY_TYPE_SIZE](#column_entry_type_size)|データベース内の特定の列へのバインディングを表します。 *型*と*サイズ*のパラメーターをサポートします。|
|[Column_name](#column_name)|データベース内の特定の列へのバインディングを名前で表します。|
|[COLUMN_NAME_EX](#column_name_ex)|データベース内の特定の列へのバインディングを名前で表します。 データ型、サイズ、精度、小数点以下桁数、列の長さ、および列の状態の指定をサポートします。|
|[COLUMN_NAME_LENGTH](#column_name_length)|データベース内の特定の列へのバインディングを名前で表します。 列の長さの指定をサポートします。|
|[COLUMN_NAME_LENGTH_STATUS](#column_name_length_status)|データベース内の特定の列へのバインディングを名前で表します。 列の長さと状態の指定をサポートします。|
|[COLUMN_NAME_PS](#column_name_ps)|データベース内の特定の列へのバインディングを名前で表します。 精度とスケールの仕様をサポートします。|
|[COLUMN_NAME_PS_LENGTH](#column_name_ps_length)|データベース内の特定の列へのバインディングを名前で表します。 精度、小数点以下桁数、および列の長さの仕様をサポートします。|
|[COLUMN_NAME_PS_LENGTH_STATUS](#column_name_ps_length_status)|データベース内の特定の列へのバインディングを名前で表します。 精度、位取り、列の長さ、および列の状態の指定をサポートします。|
|[COLUMN_NAME_PS_STATUS](#column_name_ps_status)|データベース内の特定の列へのバインディングを名前で表します。 精度、小数点以下桁数、および列の状態の指定をサポートします。|
|[COLUMN_NAME_STATUS](#column_name_status)|データベース内の特定の列へのバインディングを名前で表します。 列の状態の指定をサポートします。|
|[COLUMN_NAME_TYPE](#column_name_type)|データベース内の特定の列へのバインディングを名前で表します。 データ型の指定をサポートします。|
|[COLUMN_NAME_TYPE_PS](#column_name_type_ps)|データベース内の特定の列へのバインディングを名前で表します。 データ型、精度、およびスケールの仕様をサポートします。|
|[COLUMN_NAME_TYPE_SIZE](#column_name_type_size)|データベース内の特定の列へのバインディングを名前で表します。 データ型とサイズの仕様をサポートします。|
|[COLUMN_NAME_TYPE_STATUS](#column_name_type_status)|データベース内の特定の列へのバインディングを名前で表します。 データ型と列の状態の指定をサポートします。|
|[END_COLUMN_MAP](#end_column_map)|列マップエントリの終わりを示します。|

## <a name="command-macros"></a>コマンド マクロ

|||
|-|-|
|[DEFINE_COMMAND](#define_command)|[CCommand](../../data/oledb/ccommand-class.md)クラスを使用するときに行セットを作成するために使用するコマンドを指定します。 指定したアプリケーションの種類 (ANSI または Unicode) に一致する文字列型のみを受け入れます。 DEFINE_COMMANDの代わりに[DEFINE_COMMAND_EX](../../data/oledb/define-command-ex.md)を使用することをお勧めします。|
|[DEFINE_COMMAND_EX](#define_command_ex)|[CCommand](../../data/oledb/ccommand-class.md)クラスを使用するときに行セットを作成するために使用するコマンドを指定します。 ANSI およびユニコード アプリケーションをサポートします。|

## <a name="parameter-map-macros"></a>パラメータ マップ マクロ

|||
|-|-|
|[BEGIN_PARAM_MAP](#begin_param_map)|ユーザー レコード クラスのパラメーター マップ エントリの先頭をマークします。|
|[END_PARAM_MAP](#end_param_map)|パラメーター マップ エントリの末尾をマークします。|
|[SET_PARAM_TYPE](#set_param_type)|SET_PARAM_TYPE マクロに続くマクロを入力、出力、または入出力としてCOLUMN_ENTRY指定します。|

### <a name="atltraceerrorrecords"></a><a name="atltraceerrorrecords"></a>レコード

エラーが返された場合に、OLE DB エラー レコード情報をダンプ デバイスにダンプします。

#### <a name="syntax"></a>構文

```cpp
inline void AtlTraceErrorRecords(HRESULT hrErr = S_OK);
```

#### <a name="parameters"></a>パラメーター

*君*<br/>
[in]OLE DB コンシューマー テンプレートのメンバー関数によって返される HRESULT。

#### <a name="remarks"></a>解説

*hErr*がS_OKされていない場合`AtlTraceErrorRecords`は、OLE DB エラー レコード情報をダンプ デバイス ([出力] ウィンドウまたはファイルの [**デバッグ**] タブ) にダンプします。 プロバイダから取得されるエラー レコード情報には、各エラー レコード エントリの行番号、ソース、説明、ヘルプ ファイル、コンテキスト、および GUID が含まれます。 `AtlTraceErrorRecords`この情報はデバッグ ビルドでのみダンプされます。 リリース ビルドでは、最適化された空のスタブです。詳細については、「[クラス」](../../data/oledb/cdberrorinfo-class.md)を参照してください。

### <a name="begin_accessor"></a><a name="begin_accessor"></a>BEGIN_ACCESSOR

アクセサー エントリの先頭を示します。

#### <a name="syntax"></a>構文

```cpp
BEGIN_ACCESSOR(num, bAuto)
```

#### <a name="parameters"></a>パラメーター

*num*<br/>
[in]このアクセサ マップ内のアクセサーのオフセットオフセット 0。

*b自動*<br/>
[in]このアクセサーが自動アクセサーか手動アクセサーかどうかを指定します。 **true**の場合、アクセサーは auto です。**false の**場合、アクセサーは手動です。 自動アクセサは、移動操作でデータがフェッチされるという意味です。

#### <a name="remarks"></a>解説

行セットに複数のアクセサーがある場合は、BEGIN_ACCESSOR_MAP指定し、個々のアクセサーごとにBEGIN_ACCESSOR マクロを使用する必要があります。 BEGIN_ACCESSORマクロは、END_ACCESSOR マクロで完了します。 BEGIN_ACCESSOR_MAP マクロは、END_ACCESSOR_MAP マクロで完了します。

#### <a name="example"></a>例

BEGIN_ACCESSOR_MAP[を](../../data/oledb/begin-accessor-map.md)参照してください。

### <a name="begin_accessor_map"></a><a name="begin_accessor_map"></a>BEGIN_ACCESSOR_MAP

アクセサー マップ エントリの開始位置を示します。

#### <a name="syntax"></a>構文

```cpp
BEGIN_ACCESSOR_MAP(x, num)
```

#### <a name="parameters"></a>パラメーター

*X*<br/>
[入力] ユーザー レコード クラスの名前。

*num*<br/>
[入力] このアクセサー マップのアクセサーの数。

#### <a name="remarks"></a>解説

行セットに複数のアクセサーがある場合は、最初にBEGIN_ACCESSOR_MAPを指定し、各アクセサーに対してBEGIN_ACCESSOR マクロを使用する必要があります。 BEGIN_ACCESSORマクロは、END_ACCESSOR マクロで完了します。 アクセサ マップは、END_ACCESSOR_MAP マクロで完了します。

ユーザー レコードに含まれるアクセサーが 1 つのみの場合は、 [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md)マクロを使用します。

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

### <a name="end_accessor"></a><a name="end_accessor"></a>END_ACCESSOR

アクセサー エントリの末尾を示します。

#### <a name="syntax"></a>構文

```cpp
END_ACCESSOR()
```

#### <a name="remarks"></a>解説

行セットの複数のアクセサーの場合は、BEGIN_ACCESSOR_MAP指定し、個々のアクセサーごとにBEGIN_ACCESSOR マクロを使用する必要があります。 BEGIN_ACCESSORマクロは、END_ACCESSOR マクロで完了します。 BEGIN_ACCESSOR_MAP マクロは、END_ACCESSOR_MAP マクロで完了します。

#### <a name="example"></a>例

BEGIN_ACCESSOR_MAP[を](../../data/oledb/begin-accessor-map.md)参照してください。

### <a name="end_accessor_map"></a><a name="end_accessor_map"></a>END_ACCESSOR_MAP

アクセサ マップ エントリの末尾をマークします。

#### <a name="syntax"></a>構文

```cpp
END_ACCESSOR_MAP()
```

#### <a name="remarks"></a>解説

行セットの複数のアクセサーの場合は、BEGIN_ACCESSOR_MAP指定し、個々のアクセサーごとにBEGIN_ACCESSOR マクロを使用する必要があります。 BEGIN_ACCESSORマクロは、END_ACCESSOR マクロで完了します。 BEGIN_ACCESSOR_MAP マクロは、END_ACCESSOR_MAP マクロで完了します。

#### <a name="example"></a>例

BEGIN_ACCESSOR_MAP[を](../../data/oledb/begin-accessor-map.md)参照してください。

### <a name="begin_column_map"></a><a name="begin_column_map"></a>BEGIN_COLUMN_MAP

列マップ エントリの先頭を示します。

#### <a name="syntax"></a>構文

```cpp
BEGIN_COLUMN_MAP(x)
```

#### <a name="parameters"></a>パラメーター

*X*<br/>
[入力] `CAccessor`から派生したユーザー レコード クラスの名前。

#### <a name="remarks"></a>解説

このマクロは、行セットに対してアクセサーが 1 つしか必要ない場合に使用します。 1 つの行セットに対して複数のアクセサーが必要な場合は、 [BEGIN_ACCESSOR_MAP](../../data/oledb/begin-accessor-map.md)を使用します。

BEGIN_COLUMN_MAP マクロは、END_COLUMN_MAP マクロで完了します。 このマクロは、ユーザー レコードで 1 つのアクセサーだけが必要な場合に使用します。

列は、バインドする行セットのフィールドに相当します。

#### <a name="example"></a>例

列およびパラメーター マップのコード例を次に示します。

<!--[!CODE [NVC_OLEDB_Consumer#16](../codesnippet/vs_snippets_cpp/nvc_oledb_consumer#16)]  -->

### <a name="blob_entry"></a><a name="blob_entry"></a>BLOB_ENTRY

バイナリ ラージ オブジェクト ([BLOB](/previous-versions/windows/desktop/ms711511(v=vs.85))) をバインドするために、BEGIN_COLUMN_MAPおよびEND_COLUMN_MAPと共に使用します。

#### <a name="syntax"></a>構文

```cpp
BLOB_ENTRY(nOrdinal, IID, flags, data)
```

#### <a name="parameters"></a>パラメーター

*オルディナル*<br/>
[in]列番号。

*IID*<br/>
[in]BLOB の取得に`IDD_ISequentialStream`使用されるインターフェイス GUID ( など)

*フラグ*<br/>
[in]OLE 構造化ストレージ モデルで定義されているストレージ モード フラグ (`STGM_READ`たとえば、 )

*データ*<br/>
[in]ユーザー レコード内の対応するデータ メンバー。

#### <a name="example"></a>例

[「BLOB を取得する方法」](../../data/oledb/retrieving-a-blob.md)を参照してください。

### <a name="blob_entry_length"></a><a name="blob_entry_length"></a>BLOB_ENTRY_LENGTH

バイナリ ラージ オブジェクト ([BLOB](/previous-versions/windows/desktop/ms711511(v=vs.85))) をバインドするために、BEGIN_COLUMN_MAPおよびEND_COLUMN_MAPと共に使用します。 [BLOB_ENTRY](../../data/oledb/blob-entry.md)と同様に、このマクロは BLOB 列の長さ (バイト単位) も取得します。

#### <a name="syntax"></a>構文

```cpp
BLOB_ENTRY_LENGTH(nOrdinal, IID, flags, data, length)
```

#### <a name="parameters"></a>パラメーター

*オルディナル*<br/>
[in]列番号。

*IID*<br/>
[in]BLOB の取得に`IDD_ISequentialStream`使用されるインターフェイス GUID ( など)

*フラグ*<br/>
[in]OLE 構造化ストレージ モデルで定義されているストレージ モード フラグ (`STGM_READ`たとえば、 )

*データ*<br/>
[in]ユーザー レコード内の対応するデータ メンバー。

*length*<br/>
[アウト]BLOB 列の (実際の) 長さ (バイト単位)。

#### <a name="example"></a>例

[「BLOB を取得する方法」](../../data/oledb/retrieving-a-blob.md)を参照してください。

### <a name="blob_entry_length_status"></a><a name="blob_entry_length_status"></a>BLOB_ENTRY_LENGTH_STATUS

バイナリ ラージ オブジェクト ([BLOB](/previous-versions/windows/desktop/ms711511(v=vs.85))) をバインドするために、BEGIN_COLUMN_MAPおよびEND_COLUMN_MAPと共に使用します。 [BLOB_ENTRY](../../data/oledb/blob-entry.md)と同様に、このマクロは BLOB 列の長さおよび状態も取得します。

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

*オルディナル*<br/>
[in]列番号。

*IID*<br/>
[in]BLOB の取得に`IDD_ISequentialStream`使用されるインターフェイス GUID ( など)

*フラグ*<br/>
[in]OLE 構造化ストレージ モデルで定義されているストレージ モード フラグ (`STGM_READ`たとえば、 )

*データ*<br/>
[in]ユーザー レコード内の対応するデータ メンバー。

*length*<br/>
[アウト]BLOB 列の (実際の) 長さ (バイト単位)。

*status*<br/>
[アウト]BLOB データ列の状態。

#### <a name="example"></a>例

[「BLOB を取得する方法」](../../data/oledb/retrieving-a-blob.md)を参照してください。

### <a name="blob_entry_status"></a><a name="blob_entry_status"></a>BLOB_ENTRY_STATUS

バイナリ ラージ オブジェクト ([BLOB](/previous-versions/windows/desktop/ms711511(v=vs.85))) をバインドするために、BEGIN_COLUMN_MAPまたはBEGIN_ACCESSOR_MAPと共に使用します。 [BLOB_ENTRY](../../data/oledb/blob-entry.md)と同様に、このマクロは BLOB 列の状態も取得します。

#### <a name="syntax"></a>構文

```cpp
BLOB_ENTRY_STATUS(nOrdinal, IID, flags, data, status)
```

#### <a name="parameters"></a>パラメーター

*オルディナル*<br/>
[in]列番号。

*IID*<br/>
[in]BLOB の取得に`IDD_ISequentialStream`使用されるインターフェイス GUID ( など)

*フラグ*<br/>
[in]OLE 構造化ストレージ モデルで定義されているストレージ モード フラグ (`STGM_READ`たとえば、 )

*データ*<br/>
[in]ユーザー レコード内の対応するデータ メンバー。

*status*<br/>
[アウト]BLOB フィールドの状態。

#### <a name="example"></a>例

[「BLOB を取得する方法」](../../data/oledb/retrieving-a-blob.md)を参照してください。

### <a name="blob_name"></a><a name="blob_name"></a>BLOB_NAME

バイナリ ラージ オブジェクト ([BLOB](/previous-versions/windows/desktop/ms711511(v=vs.85))) をバインドするために、BEGIN_COLUMN_MAPおよびEND_COLUMN_MAPと共に使用します。 [BLOB_ENTRY](../../data/oledb/blob-entry.md)と同様ですが、このマクロは列番号の代わりに列名を取ります。

#### <a name="syntax"></a>構文

```cpp
BLOB_NAME(pszName, IID, flags, data )
```

#### <a name="parameters"></a>パラメーター

*名前*<br/>
[in]列名へのポインター。 名前は Unicode 文字列である必要があります。 これを実現するには、名前の前に「L」を付けます。 `L"MyColumn"`

*IID*<br/>
[in]BLOB の取得に`IDD_ISequentialStream`使用されるインターフェイス GUID ( など)

*フラグ*<br/>
[in]OLE 構造化ストレージ モデルで定義されているストレージ モード フラグ (`STGM_READ`たとえば、 )

*データ*<br/>
[in]ユーザー レコード内の対応するデータ メンバー。

#### <a name="example"></a>例

[「BLOB を取得する方法」](../../data/oledb/retrieving-a-blob.md)を参照してください。

### <a name="blob_name_length"></a><a name="blob_name_length"></a>BLOB_NAME_LENGTH

バイナリ ラージ オブジェクト ([BLOB](/previous-versions/windows/desktop/ms711511(v=vs.85))) をバインドするために、BEGIN_COLUMN_MAPおよびEND_COLUMN_MAPと共に使用します。 [BLOB_NAME](../../data/oledb/blob-name.md)と同様に、このマクロは BLOB データ列の長さ (バイト単位) も取得します。

#### <a name="syntax"></a>構文

```cpp
BLOB_NAME_LENGTH(pszName, IID, flags, data, length )
```

#### <a name="parameters"></a>パラメーター

*名前*<br/>
[in]列名へのポインター。 名前は Unicode 文字列である必要があります。 これを実現するには、名前の前に「L」を付けます。 `L"MyColumn"`

*IID*<br/>
[in]BLOB の取得に`IDD_ISequentialStream`使用されるインターフェイス GUID ( など)

*フラグ*<br/>
[in]OLE 構造化ストレージ モデルで定義されているストレージ モード フラグ (`STGM_READ`たとえば、 )

*データ*<br/>
[in]ユーザー レコード内の対応するデータ メンバー。

*length*<br/>
[アウト]BLOB 列の (実際の) 長さ (バイト単位)。

### <a name="blob_name_length_status"></a><a name="blob_name_length_status"></a>BLOB_NAME_LENGTH_STATUS

バイナリ ラージ オブジェクト ([BLOB](/previous-versions/windows/desktop/ms711511(v=vs.85))) をバインドするために、BEGIN_COLUMN_MAPおよびEND_COLUMN_MAPと共に使用します。 [BLOB_NAME](../../data/oledb/blob-name.md)と同様に、このマクロは BLOB データ列の長さおよび状態も取得します。

#### <a name="syntax"></a>構文

```cpp
BLOB_NAME_LENGTH_STATUS(pszName, IID, flags, data, length, status )
```

#### <a name="parameters"></a>パラメーター

*名前*<br/>
[in]列名へのポインター。 名前は Unicode 文字列である必要があります。 これを実現するには、名前の前に「L」を付けます。 `L"MyColumn"`

*IID*<br/>
[in]BLOB の取得に`IDD_ISequentialStream`使用されるインターフェイス GUID ( など)

*フラグ*<br/>
[in]OLE 構造化ストレージ モデルで定義されているストレージ モード フラグ (`STGM_READ`たとえば、 )

*データ*<br/>
[in]ユーザー レコード内の対応するデータ メンバー。

*length*<br/>
[アウト]BLOB 列の (実際の) 長さ (バイト単位)。

*status*<br/>
[アウト]BLOB フィールドの状態。

### <a name="blob_name_status"></a><a name="blob_name_status"></a>BLOB_NAME_STATUS

バイナリ ラージ オブジェクト ([BLOB](/previous-versions/windows/desktop/ms711511(v=vs.85))) をバインドするために、BEGIN_COLUMN_MAPおよびEND_COLUMN_MAPと共に使用します。 [BLOB_NAME](../../data/oledb/blob-name.md)と同様に、このマクロは BLOB データ列の状態も取得します。

#### <a name="syntax"></a>構文

```cpp
BLOB_NAME_STATUS(pszName, IID, flags, data, status )
```

#### <a name="parameters"></a>パラメーター

*名前*<br/>
[in]列名へのポインター。 名前は Unicode 文字列である必要があります。 これを実現するには、名前の前に「L」を付けます。 `L"MyColumn"`

*IID*<br/>
[in]BLOB の取得に`IDD_ISequentialStream`使用されるインターフェイス GUID ( など)

*フラグ*<br/>
[in]OLE 構造化ストレージ モデルで定義されているストレージ モード フラグ (`STGM_READ`たとえば、 )

*データ*<br/>
[in]ユーザー レコード内の対応するデータ メンバー。

*status*<br/>
[アウト]BLOB フィールドの状態。

### <a name="bookmark_entry"></a><a name="bookmark_entry"></a>BOOKMARK_ENTRY

ブックマーク列をバインドします。

#### <a name="syntax"></a>構文

```cpp
BOOKMARK_ENTRY(variable)
```

#### <a name="parameters"></a>パラメーター

*変数*<br/>
[in]ブックマーク列にバインドする変数。

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

詳細については、「 ブックマークと[CBookmark クラス](../../data/oledb/cbookmark-class.md)[の使用](using-bookmarks.md)」を参照してください。

### <a name="column_entry"></a><a name="column_entry"></a>COLUMN_ENTRY

行セットの特定の列への行セットのバインドを表します。

#### <a name="syntax"></a>構文

```cpp
COLUMN_ENTRY(nOrdinal, data)
```

#### <a name="parameters"></a>パラメーター

*「OLE*DB プログラマ リファレンス」の[「DB バインディング](/previous-versions/windows/desktop/ms716845(v=vs.85))」を参照してください。

*オルディナル*<br/>
[in]列番号。

*データ*<br/>
[in]ユーザー レコード内の対応するデータ メンバー。

#### <a name="remarks"></a>解説

COLUMN_ENTRY マクロは、次の場所で使用されます。

- BEGIN_COLUMN_MAP[と](../../data/oledb/begin-column-map.md)[END_COLUMN_MAP](../../data/oledb/end-column-map.md)マクロの間。

- BEGIN_ACCESSORと[BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md)[END_ACCESSOR](../../data/oledb/end-accessor.md)マクロの間。

- BEGIN_PARAM_MAPと[BEGIN_PARAM_MAP](../../data/oledb/begin-param-map.md)[END_PARAM_MAP](../../data/oledb/end-param-map.md)マクロの間。

#### <a name="example"></a>例

マクロのトピック[「BEGIN_COLUMN_MAP」](../../data/oledb/begin-column-map.md)および[「BEGIN_ACCESSOR_MAP」](../../data/oledb/begin-accessor-map.md)の例を参照してください。

### <a name="column_entry_ex"></a><a name="column_entry_ex"></a>COLUMN_ENTRY_EX

データベース内の特定の列に対する行セットのバインドを表します。

#### <a name="syntax"></a>構文

```cpp
COLUMN_ENTRY_EX(nOrdinal, wType, nLength, nPrecision, nScale, data, length, status)
```

#### <a name="parameters"></a>パラメーター

*「OLE*DB プログラマ リファレンス」の[「DB バインディング](/previous-versions/windows/desktop/ms716845(v=vs.85))」を参照してください。

*オルディナル*<br/>
[in]列番号。

*wType*<br/>
[in]データ型。

*nレングス*<br/>
[in]データ サイズ (バイト単位)。

*n精密*<br/>
[in]データと*wType*を取得するときに使用する最大`DBTYPE_NUMERIC`精度は です。 それ以外の場合、このパラメーターは無視されます。

*nスケール*<br/>
[in]データを取得するときに使用するスケールと*wType*は、`DBTYPE_NUMERIC`または`DBTYPE_DECIMAL`です。

*データ*<br/>
[in]ユーザー レコード内の対応するデータ メンバー。

*length*<br/>
[in]列の長さにバインドされる変数。

*status*<br/>
[in]列の状態にバインドされる変数。

#### <a name="remarks"></a>解説

COLUMN_ENTRY_EX マクロは、次の場所で使用されます。

- BEGIN_COLUMN_MAP[と](../../data/oledb/begin-column-map.md)[END_COLUMN_MAP](../../data/oledb/end-column-map.md)マクロの間。

- BEGIN_ACCESSORと[BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md)[END_ACCESSOR](../../data/oledb/end-accessor.md)マクロの間。

- BEGIN_PARAM_MAPと[BEGIN_PARAM_MAP](../../data/oledb/begin-param-map.md)[END_PARAM_MAP](../../data/oledb/end-param-map.md)マクロの間。

#### <a name="example"></a>例

[BOOKMARK_ENTRY](../../data/oledb/bookmark-entry.md)を参照してください。

### <a name="column_entry_length"></a><a name="column_entry_length"></a>COLUMN_ENTRY_LENGTH

データベース内の特定の列に対する行セットのバインドを表します。

#### <a name="syntax"></a>構文

```cpp
COLUMN_ENTRY_LENGTH(nOrdinal, data, length)
```

#### <a name="parameters"></a>パラメーター

*「OLE*DB プログラマ リファレンス」の[「DB バインディング](/previous-versions/windows/desktop/ms716845(v=vs.85))」を参照してください。

*オルディナル*<br/>
[in]1 から始まる列番号。 ブックマークは列 0 に対応します。

*データ*<br/>
[in]ユーザー レコード内の対応するデータ メンバー。

*length*<br/>
[in]列の長さにバインドされる変数。

#### <a name="remarks"></a>解説

このマクロは *、長さ*変数をサポートしています。 これは、次の場所で使用されます。

- BEGIN_COLUMN_MAP[と](../../data/oledb/begin-column-map.md)[END_COLUMN_MAP](../../data/oledb/end-column-map.md)マクロの間。

- BEGIN_ACCESSORと[BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md)[END_ACCESSOR](../../data/oledb/end-accessor.md)マクロの間。

- BEGIN_PARAM_MAPと[BEGIN_PARAM_MAP](../../data/oledb/begin-param-map.md)[END_PARAM_MAP](../../data/oledb/end-param-map.md)マクロの間。

### <a name="column_entry_length_status"></a><a name="column_entry_length_status"></a>COLUMN_ENTRY_LENGTH_STATUS

データベース内の特定の列に対する行セットのバインドを表します。

#### <a name="syntax"></a>構文

```cpp
COLUMN_ENTRY_LENGTH_STATUS(nOrdinal, data, length, status)
```

#### <a name="parameters"></a>パラメーター

*「OLE*DB プログラマ リファレンス」の[「DB バインディング](/previous-versions/windows/desktop/ms716845(v=vs.85))」を参照してください。

*オルディナル*<br/>
[in]列番号。

*データ*<br/>
[in]ユーザー レコード内の対応するデータ メンバー。

*length*<br/>
[in]列の長さにバインドされる変数。

*status*<br/>
[in]列の状態にバインドされる変数。

#### <a name="remarks"></a>解説

長さと状態の変数をサポートする場合は、このマクロを使用します。 これは、次の場所で使用されます。

- BEGIN_COLUMN_MAP[と](../../data/oledb/begin-column-map.md)[END_COLUMN_MAP](../../data/oledb/end-column-map.md)マクロの間。

- BEGIN_ACCESSORと[BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md)[END_ACCESSOR](../../data/oledb/end-accessor.md)マクロの間。

- BEGIN_PARAM_MAPと[BEGIN_PARAM_MAP](../../data/oledb/begin-param-map.md)[END_PARAM_MAP](../../data/oledb/end-param-map.md)マクロの間。

### <a name="column_entry_ps"></a><a name="column_entry_ps"></a>COLUMN_ENTRY_PS

行セットの特定の列への行セットのバインドを表します。

#### <a name="syntax"></a>構文

```cpp
COLUMN_ENTRY_PS(nOrdinal, nPrecision, nScale, data)
```

#### <a name="parameters"></a>パラメーター

*「OLE*DB プログラマ リファレンス」の[「DB バインディング](/previous-versions/windows/desktop/ms716845(v=vs.85))」を参照してください。

*オルディナル*<br/>
[in]列番号。

*n精密*<br/>
[in]バインドする列の最大精度。

*nスケール*<br/>
[in]バインドする列のスケール。

*データ*<br/>
[in]ユーザー レコード内の対応するデータ メンバー。

#### <a name="remarks"></a>解説

バインドする列の精度と小数点以下桁数を指定できます。 これは、次の場所で使用されます。

- BEGIN_COLUMN_MAP[と](../../data/oledb/begin-column-map.md)[END_COLUMN_MAP](../../data/oledb/end-column-map.md)マクロの間。

- BEGIN_ACCESSORと[BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md)[END_ACCESSOR](../../data/oledb/end-accessor.md)マクロの間。

- BEGIN_PARAM_MAPと[BEGIN_PARAM_MAP](../../data/oledb/begin-param-map.md)[END_PARAM_MAP](../../data/oledb/end-param-map.md)マクロの間。

### <a name="column_entry_ps_length"></a><a name="column_entry_ps_length"></a>COLUMN_ENTRY_PS_LENGTH

データベース内の特定の列に対する行セットのバインドを表します。

#### <a name="syntax"></a>構文

```cpp
COLUMN_ENTRY_PS_LENGTH(nOrdinal, nPrecision, nScale, data, length)
```

#### <a name="parameters"></a>パラメーター

*「OLE*DB プログラマ リファレンス」の[「DB バインディング](/previous-versions/windows/desktop/ms716845(v=vs.85))」を参照してください。

*オルディナル*<br/>
[in]1 から始まる列番号。 ブックマークは列 0 に対応します。

*n精密*<br/>
[in]バインドする列の最大精度。

*nスケール*<br/>
[in]バインドする列のスケール。

*データ*<br/>
[in]ユーザー レコード内の対応するデータ メンバー。

*length*<br/>
[in]列の長さにバインドされる変数。

#### <a name="remarks"></a>解説

バインドする列の精度と小数点以下桁数を指定できます。 このマクロは *、長さ*変数をサポートしています。 これは、次の場所で使用されます。

- BEGIN_COLUMN_MAP[と](../../data/oledb/begin-column-map.md)[END_COLUMN_MAP](../../data/oledb/end-column-map.md)マクロの間。

- BEGIN_ACCESSORと[BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md)[END_ACCESSOR](../../data/oledb/end-accessor.md)マクロの間。

- BEGIN_PARAM_MAPと[BEGIN_PARAM_MAP](../../data/oledb/begin-param-map.md)[END_PARAM_MAP](../../data/oledb/end-param-map.md)マクロの間。

### <a name="column_entry_ps_length_status"></a><a name="column_entry_ps_length_status"></a>COLUMN_ENTRY_PS_LENGTH_STATUS

データベース内の特定の列に対する行セットのバインドを表します。

#### <a name="syntax"></a>構文

```cpp
COLUMN_ENTRY_PS_LENGTH_STATUS(nOrdinal, nPrecision, nScale, data, length, status)
```

#### <a name="parameters"></a>パラメーター

*「OLE*DB プログラマ リファレンス」の[「DB バインディング](/previous-versions/windows/desktop/ms716845(v=vs.85))」を参照してください。

*オルディナル*<br/>
[in]列番号。

*n精密*<br/>
[in]バインドする列の最大精度。

*nスケール*<br/>
[in]バインドする列のスケール。

*データ*<br/>
[in]ユーザー レコード内の対応するデータ メンバー。

*length*<br/>
[in]列の長さにバインドされる変数。

*status*<br/>
[in]列の状態にバインドされる変数。

#### <a name="remarks"></a>解説

バインドする列の精度と小数点以下桁数を指定できます。 長さと状態の変数をサポートする場合は、このマクロを使用します。 これは、次の場所で使用されます。

- BEGIN_COLUMN_MAP[と](../../data/oledb/begin-column-map.md)[END_COLUMN_MAP](../../data/oledb/end-column-map.md)マクロの間。

- BEGIN_ACCESSORと[BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md)[END_ACCESSOR](../../data/oledb/end-accessor.md)マクロの間。

- BEGIN_PARAM_MAPと[BEGIN_PARAM_MAP](../../data/oledb/begin-param-map.md)[END_PARAM_MAP](../../data/oledb/end-param-map.md)マクロの間。

### <a name="column_entry_ps_status"></a><a name="column_entry_ps_status"></a>COLUMN_ENTRY_PS_STATUS

データベース内の特定の列に対する行セットのバインドを表します。

#### <a name="syntax"></a>構文

```cpp
COLUMN_ENTRY_PS_STATUS(nOrdinal, nPrecision, nScale, data, status)
```

#### <a name="parameters"></a>パラメーター

*「OLE*DB プログラマ リファレンス」の[「DB バインディング](/previous-versions/windows/desktop/ms716845(v=vs.85))」を参照してください。

*オルディナル*<br/>
[in]列番号。

*n精密*<br/>
[in]バインドする列の最大精度。

*nスケール*<br/>
[in]バインドする列のスケール。

*データ*<br/>
[in]ユーザー レコード内の対応するデータ メンバー。

*status*<br/>
[in]列の状態にバインドされる変数。

#### <a name="remarks"></a>解説

バインドする列の精度と小数点以下桁数を指定できます。 このマクロは *、ステータス*変数をサポートします。 これは、次の場所で使用されます。

- BEGIN_COLUMN_MAP[と](../../data/oledb/begin-column-map.md)[END_COLUMN_MAP](../../data/oledb/end-column-map.md)マクロの間。

- BEGIN_ACCESSORと[BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md)[END_ACCESSOR](../../data/oledb/end-accessor.md)マクロの間。

- BEGIN_PARAM_MAPと[BEGIN_PARAM_MAP](../../data/oledb/begin-param-map.md)[END_PARAM_MAP](../../data/oledb/end-param-map.md)マクロの間。

### <a name="column_entry_status"></a><a name="column_entry_status"></a>COLUMN_ENTRY_STATUS

データベース内の特定の列に対する行セットのバインドを表します。

#### <a name="syntax"></a>構文

```cpp
COLUMN_ENTRY_STATUS(nOrdinal, data, status)
```

#### <a name="parameters"></a>パラメーター

*「OLE*DB プログラマ リファレンス」の[「DB バインディング](/previous-versions/windows/desktop/ms716845(v=vs.85))」を参照してください。

*オルディナル*<br/>
[in]列番号。

*データ*<br/>
[in]ユーザー レコード内の対応するデータ メンバー。

*status*<br/>
[in]列の状態にバインドされる変数。

#### <a name="remarks"></a>解説

このマクロは *、ステータス*変数をサポートします。 これは、次の場所で使用されます。

- BEGIN_COLUMN_MAP[と](../../data/oledb/begin-column-map.md)[END_COLUMN_MAP](../../data/oledb/end-column-map.md)マクロの間。

- BEGIN_ACCESSORと[BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md)[END_ACCESSOR](../../data/oledb/end-accessor.md)マクロの間。

- BEGIN_PARAM_MAPと[BEGIN_PARAM_MAP](../../data/oledb/begin-param-map.md)[END_PARAM_MAP](../../data/oledb/end-param-map.md)マクロの間。

### <a name="column_entry_type"></a><a name="column_entry_type"></a>COLUMN_ENTRY_TYPE

データベース内の特定の列へのバインディングを表します。 *型パラメーターを*サポートします。

#### <a name="syntax"></a>構文

```cpp
COLUMN_ENTRY_TYPE (nOrdinal, wType, data)
```

#### <a name="parameters"></a>パラメーター

*オルディナル*<br/>
[in]列番号。

*wType*<br/>
[in]列エントリのデータ型です。

*データ*<br/>
[in]ユーザー レコード内の対応するデータ メンバー。

#### <a name="remarks"></a>解説

このマクロは、データ型を指定する手段を提供する[COLUMN_ENTRY](../../data/oledb/column-entry.md)マクロの特殊なバリアントです。

### <a name="column_entry_type_size"></a><a name="column_entry_type_size"></a>COLUMN_ENTRY_TYPE_SIZE

データベース内の特定の列へのバインディングを表します。 *型*と*サイズ*のパラメーターをサポートします。

#### <a name="syntax"></a>構文

```cpp
COLUMN_ENTRY_TYPE_SIZE(nOrdinal, wType, nLength, data)
```

#### <a name="parameters"></a>パラメーター

*オルディナル*<br/>
[in]列番号。

*wType*<br/>
[in]列エントリのデータ型です。

*nレングス*<br/>
[in]列エントリのサイズ (バイト単位)。

*データ*<br/>
[in]ユーザー レコード内の対応するデータ メンバー。

#### <a name="remarks"></a>解説

このマクロは、データ サイズと型を指定する手段を提供する[COLUMN_ENTRY](../../data/oledb/column-entry.md)マクロの特殊なバリアントです。

### <a name="column_name"></a><a name="column_name"></a>Column_name

行セットの特定の列への行セットのバインドを表します。 [COLUMN_ENTRY](../../data/oledb/column-entry.md)と同様ですが、このマクロは列番号の代わりに列名を取ります。

#### <a name="syntax"></a>構文

```cpp
COLUMN_NAME(pszName, data)
```

#### <a name="parameters"></a>パラメーター

*名前*<br/>
[in]列名へのポインター。 名前は Unicode 文字列である必要があります。 これを実現するには、名前の前に「L」を付けます。 `L"MyColumn"`

*データ*<br/>
[in]ユーザー レコード内の対応するデータ メンバー。

#### <a name="remarks"></a>解説

COLUMN_NAME_* マクロは[、COLUMN_ENTRY](../../data/oledb/column-entry.md)と同じ場所で使用されます。

- BEGIN_COLUMN_MAP[と](../../data/oledb/begin-column-map.md)[END_COLUMN_MAP](../../data/oledb/end-column-map.md)マクロの間。

- BEGIN_ACCESSORと[BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md)[END_ACCESSOR](../../data/oledb/end-accessor.md)マクロの間。

- BEGIN_PARAM_MAPと[BEGIN_PARAM_MAP](../../data/oledb/begin-param-map.md)[END_PARAM_MAP](../../data/oledb/end-param-map.md)マクロの間。

### <a name="column_name_ex"></a><a name="column_name_ex"></a>COLUMN_NAME_EX

行セットの特定の列への行セットのバインドを表します。 [COLUMN_NAME](../../data/oledb/column-name.md)と同様に、このマクロはデータ型、サイズ、精度、小数点以下桁数、列の長さ、および列の状態も受け取ります。

#### <a name="syntax"></a>構文

```cpp
COLUMN_NAME_EX(pszName, wType, nLength, nPrecision, nScale, data, length, status )
```

#### <a name="parameters"></a>パラメーター

*名前*<br/>
[in]列名へのポインター。 名前は Unicode 文字列である必要があります。 これを実現するには、名前の前に「L」を付けます。 `L"MyColumn"`

*wType*<br/>
[in]データ型。

*nレングス*<br/>
[in]データ サイズ (バイト単位)。

*n精密*<br/>
[in]データと*wType*を取得するときに使用する最大`DBTYPE_NUMERIC`精度は です。 それ以外の場合、このパラメーターは無視されます。

*nスケール*<br/>
[in]データを取得するときに使用するスケールと*wType*は、`DBTYPE_NUMERIC`または`DBTYPE_DECIMAL`です。

*データ*<br/>
[in]ユーザー レコード内の対応するデータ メンバー。

*length*<br/>
[in]列の長さにバインドされる変数。

*status*<br/>
[in]列の状態にバインドされる変数。

#### <a name="remarks"></a>解説

COLUMN_NAME_* マクロの使用場所については[、COLUMN_NAME](../../data/oledb/column-name.md)を参照してください。

### <a name="column_name_length"></a><a name="column_name_length"></a>COLUMN_NAME_LENGTH

行セットの特定の列への行セットのバインドを表します。 [COLUMN_NAME](../../data/oledb/column-name.md)と同様ですが、このマクロも列の長さを取ります。

#### <a name="syntax"></a>構文

```cpp
COLUMN_NAME_LENGTH(pszName, data, length)
```

#### <a name="parameters"></a>パラメーター

*名前*<br/>
[in]列名へのポインター。 名前は Unicode 文字列である必要があります。 これを実現するには、名前の前に「L」を付けます。 `L"MyColumn"`

*データ*<br/>
[in]ユーザー レコード内の対応するデータ メンバー。

*length*<br/>
[in]列の長さにバインドされる変数。

#### <a name="remarks"></a>解説

COLUMN_NAME_* マクロの使用場所については[、COLUMN_NAME](../../data/oledb/column-name.md)を参照してください。

### <a name="column_name_length_status"></a><a name="column_name_length_status"></a>COLUMN_NAME_LENGTH_STATUS

行セットの特定の列への行セットのバインドを表します。 [COLUMN_NAME](../../data/oledb/column-name.md)と同様ですが、このマクロは列の長さおよび列の状態も受け取ります。

#### <a name="syntax"></a>構文

```cpp
COLUMN_NAME_LENGTH_STATUS(pszName, data, length, status )
```

#### <a name="parameters"></a>パラメーター

*名前*<br/>
[in]列名へのポインター。 名前は Unicode 文字列である必要があります。 これを実現するには、名前の前に「L」を付けます。 `L"MyColumn"`

*データ*<br/>
[in]ユーザー レコード内の対応するデータ メンバー。

*length*<br/>
[in]列の長さにバインドされる変数。

*status*<br/>
[in]列の状態にバインドされる変数。

#### <a name="remarks"></a>解説

COLUMN_NAME_* マクロの使用場所については[、COLUMN_NAME](../../data/oledb/column-name.md)を参照してください。

### <a name="column_name_ps"></a><a name="column_name_ps"></a>COLUMN_NAME_PS

行セットの特定の列への行セットのバインドを表します。 [COLUMN_NAME](../../data/oledb/column-name.md)と同様ですが、このマクロも精度とスケールを取ります。

#### <a name="syntax"></a>構文

```cpp
COLUMN_NAME_PS(pszName, nPrecision, nScale, data )
```

#### <a name="parameters"></a>パラメーター

*名前*<br/>
[in]列名へのポインター。 名前は Unicode 文字列である必要があります。 これを実現するには、名前の前に「L」を付けます。 `L"MyColumn"`

*n精密*<br/>
[in]バインドする列の最大精度。

*nスケール*<br/>
[in]バインドする列のスケール。

*データ*<br/>
[in]ユーザー レコード内の対応するデータ メンバー。

#### <a name="remarks"></a>解説

COLUMN_NAME_* マクロの使用場所については[、COLUMN_NAME](../../data/oledb/column-name.md)を参照してください。

### <a name="column_name_ps_length"></a><a name="column_name_ps_length"></a>COLUMN_NAME_PS_LENGTH

行セットの特定の列への行セットのバインドを表します。 [COLUMN_NAME](../../data/oledb/column-name.md)と同様に、このマクロは精度、小数点以下桁数、および列の長さも取ります。

#### <a name="syntax"></a>構文

```cpp
COLUMN_NAME_PS_LENGTH(pszName, nPrecision, nScale, data, length )
```

#### <a name="parameters"></a>パラメーター

*名前*<br/>
[in]列名へのポインター。 名前は Unicode 文字列である必要があります。 これを実現するには、名前の前に「L」を付けます。 `L"MyColumn"`

*n精密*<br/>
[in]バインドする列の最大精度。

*nスケール*<br/>
[in]バインドする列のスケール。

*データ*<br/>
[in]ユーザー レコード内の対応するデータ メンバー。

*length*<br/>
[in]列の長さにバインドされる変数。

#### <a name="remarks"></a>解説

COLUMN_NAME_* マクロの使用場所については[、COLUMN_NAME](../../data/oledb/column-name.md)を参照してください。

### <a name="column_name_ps_length_status"></a><a name="column_name_ps_length_status"></a>COLUMN_NAME_PS_LENGTH_STATUS

行セットの特定の列への行セットのバインドを表します。 [COLUMN_NAME](../../data/oledb/column-name.md)と同様に、このマクロは精度、位取り、列の長さ、および列の状態も受け取ります。

#### <a name="syntax"></a>構文

```cpp
COLUMN_NAME_PS_LENGTH_STATUS(pszName, nPrecision, nScale, data, length, status )
```

#### <a name="parameters"></a>パラメーター

*名前*<br/>
[in]列名へのポインター。 名前は Unicode 文字列である必要があります。 これを実現するには、名前の前に「L」を付けます。 `L"MyColumn"`

*n精密*<br/>
[in]バインドする列の最大精度。

*nスケール*<br/>
[in]バインドする列のスケール。

*データ*<br/>
[in]ユーザー レコード内の対応するデータ メンバー。

*length*<br/>
[in]列の長さにバインドされる変数。

*status*<br/>
[in]列の状態にバインドされる変数。

#### <a name="remarks"></a>解説

COLUMN_NAME_* マクロの使用場所については[、COLUMN_NAME](../../data/oledb/column-name.md)を参照してください。

### <a name="column_name_ps_status"></a><a name="column_name_ps_status"></a>COLUMN_NAME_PS_STATUS

行セットの特定の列への行セットのバインドを表します。 [COLUMN_NAME](../../data/oledb/column-name.md)と同様に、このマクロは精度、小数点以下桁数、および列の状態も受け取ります。

#### <a name="syntax"></a>構文

```cpp
COLUMN_NAME_PS_STATUS(pszName, nPrecision, nScale, data, status )
```

#### <a name="parameters"></a>パラメーター

*名前*<br/>
[in]列名へのポインター。 名前は Unicode 文字列である必要があります。 これを実現するには、名前の前に「L」を付けます。 `L"MyColumn"`

*n精密*<br/>
[in]バインドする列の最大精度。

*nスケール*<br/>
[in]バインドする列のスケール。

*データ*<br/>
[in]ユーザー レコード内の対応するデータ メンバー。

*status*<br/>
[in]列の状態にバインドされる変数。

#### <a name="remarks"></a>解説

COLUMN_NAME_* マクロの使用場所については[、COLUMN_NAME](../../data/oledb/column-name.md)を参照してください。

### <a name="column_name_status"></a><a name="column_name_status"></a>COLUMN_NAME_STATUS

行セットの特定の列への行セットのバインドを表します。 [COLUMN_NAME](../../data/oledb/column-name.md)と同様ですが、このマクロも列の状態を取ります。

#### <a name="syntax"></a>構文

```cpp
COLUMN_NAME_STATUS(pszName, data, status )
```

#### <a name="parameters"></a>パラメーター

*名前*<br/>
[in]列名へのポインター。 名前は Unicode 文字列である必要があります。 これを実現するには、名前の前に「L」を付けます。 `L"MyColumn"`

*データ*<br/>
[in]ユーザー レコード内の対応するデータ メンバー。

*status*<br/>
[in]列の状態にバインドされる変数。

#### <a name="remarks"></a>解説

COLUMN_NAME_* マクロの使用場所については[、COLUMN_NAME](../../data/oledb/column-name.md)を参照してください。

### <a name="column_name_type"></a><a name="column_name_type"></a>COLUMN_NAME_TYPE

行セットの特定の列への行セットのバインドを表します。 [COLUMN_NAME](../../data/oledb/column-name.md)と同様ですが、このマクロもデータ型を取ります。

#### <a name="syntax"></a>構文

```cpp
COLUMN_NAME_TYPE(pszName, wType, data)
```

#### <a name="parameters"></a>パラメーター

*名前*<br/>
[in]列名へのポインター。 名前は Unicode 文字列である必要があります。 これを実現するには、名前の前に「L」を付けます。 `L"MyColumn"`

*wType*<br/>
[in]データ型。

*データ*<br/>
[in]ユーザー レコード内の対応するデータ メンバー。

#### <a name="remarks"></a>解説

COLUMN_NAME_* マクロの使用場所については[、COLUMN_NAME](../../data/oledb/column-name.md)を参照してください。

### <a name="column_name_type_ps"></a><a name="column_name_type_ps"></a>COLUMN_NAME_TYPE_PS

行セットの特定の列への行セットのバインドを表します。 [COLUMN_NAME](../../data/oledb/column-name.md)と同様に、このマクロはデータ型、有効桁数、および小数点以下桁数も取ります。

#### <a name="syntax"></a>構文

```cpp
COLUMN_NAME_TYPE_PS(pszName, wType, nPrecision, nScale, data)
```

#### <a name="parameters"></a>パラメーター

*名前*<br/>
[in]列名へのポインター。 名前は Unicode 文字列である必要があります。 これを実現するには、名前の前に「L」を付けます。 `L"MyColumn"`

*wType*<br/>
[in]データ型。

*n精密*<br/>
[in]データと*wType*を取得するときに使用する最大`DBTYPE_NUMERIC`精度は です。 それ以外の場合、このパラメーターは無視されます。

*nスケール*<br/>
[in]データを取得するときに使用するスケールと*wType*は、`DBTYPE_NUMERIC`または`DBTYPE_DECIMAL`です。

*データ*<br/>
[in]ユーザー レコード内の対応するデータ メンバー。

#### <a name="remarks"></a>解説

COLUMN_NAME_* マクロの使用場所については[、COLUMN_NAME](../../data/oledb/column-name.md)を参照してください。

### <a name="column_name_type_size"></a><a name="column_name_type_size"></a>COLUMN_NAME_TYPE_SIZE

行セットの特定の列への行セットのバインドを表します。 [COLUMN_NAME](../../data/oledb/column-name.md)と同様ですが、このマクロはデータ型とサイズも取ります。

#### <a name="syntax"></a>構文

```cpp
COLUMN_NAME_TYPE_SIZE(pszName, wType, nLength, data)
```

#### <a name="parameters"></a>パラメーター

*名前*<br/>
[in]列名へのポインター。 名前は Unicode 文字列である必要があります。 これを実現するには、名前の前に「L」を付けます。 `L"MyColumn"`

*wType*<br/>
[in]データ型。

*nレングス*<br/>
[in]データ サイズ (バイト単位)。

*データ*<br/>
[in]ユーザー レコード内の対応するデータ メンバー。

#### <a name="remarks"></a>解説

COLUMN_NAME_* マクロの使用場所については[、COLUMN_NAME](../../data/oledb/column-name.md)を参照してください。

### <a name="column_name_type_status"></a><a name="column_name_type_status"></a>COLUMN_NAME_TYPE_STATUS

行セットの特定の列への行セットのバインドを表します。 [COLUMN_NAME](../../data/oledb/column-name.md)と同様ですが、このマクロはデータ型と列の状態も受け取ります。

#### <a name="syntax"></a>構文

```cpp
COLUMN_NAME_TYPE_STATUS(pszName, wType, status, data)
```

#### <a name="parameters"></a>パラメーター

*名前*<br/>
[in]列名へのポインター。 名前は Unicode 文字列である必要があります。 これを実現するには、名前の前に「L」を付けます。 `L"MyColumn"`

*wType*<br/>
[in]データ型。

*status*<br/>
[in]列の状態にバインドされる変数。

*データ*<br/>
[in]ユーザー レコード内の対応するデータ メンバー。

#### <a name="remarks"></a>解説

COLUMN_NAME_* マクロの使用場所については[、COLUMN_NAME](../../data/oledb/column-name.md)を参照してください。

### <a name="end_column_map"></a><a name="end_column_map"></a>END_COLUMN_MAP

列マップエントリの終わりを示します。

#### <a name="syntax"></a>構文

```cpp
END_COLUMN_MAP()
```

#### <a name="remarks"></a>解説

これは、行セットの 1 つのアクセサーで使用されます。 BEGIN_COLUMN_MAP マクロは、END_COLUMN_MAP マクロで完了します。

#### <a name="example"></a>例

BEGIN_COLUMN_MAP[を](../../data/oledb/begin-column-map.md)参照してください。

### <a name="define_command"></a><a name="define_command"></a>DEFINE_COMMAND

[CCommand](../../data/oledb/ccommand-class.md)クラスを使用するときに行セットを作成するために使用するコマンドを指定します。 指定したアプリケーションの種類 (ANSI または Unicode) に一致する文字列型のみを受け入れます。

> [!NOTE]
> DEFINE_COMMANDの代わりに[DEFINE_COMMAND_EX](../../data/oledb/define-command-ex.md)を使用することをお勧めします。

#### <a name="syntax"></a>構文

```cpp
DEFINE_COMMAND(x, szCommand)
```

#### <a name="parameters"></a>パラメーター

*X*<br/>
[in]ユーザー・レコード (コマンド) クラスの名前。

*コマンド*<br/>
[in][CCommand](../../data/oledb/ccommand-class.md)を使用するときに行セットを作成するために使用されるコマンド文字列。

#### <a name="remarks"></a>解説

[CCommand::Open](../../data/oledb/ccommand-open.md)メソッドでコマンド テキストを指定しない場合、指定したコマンド文字列が既定として使用されます。

このマクロは、アプリケーションを ANSI としてビルドする場合は ANSI 文字列を受け取り、Unicode としてアプリケーションをビルドする場合は Unicode 文字列を受け入れます。 前者は、ANSI または Unicode アプリケーションの種類に関係なく、Unicode 文字列を受け入れるため、DEFINE_COMMANDではなく[DEFINE_COMMAND_EX](../../data/oledb/define-command-ex.md)を使用することをお勧めします。

#### <a name="example"></a>例

[BOOKMARK_ENTRY](../../data/oledb/bookmark-entry.md)を参照してください。

### <a name="define_command_ex"></a><a name="define_command_ex"></a>DEFINE_COMMAND_EX

[CCommand](../../data/oledb/ccommand-class.md)クラスを使用するときに行セットを作成するために使用するコマンドを指定します。 ユニコードおよび ANSI アプリケーションをサポートします。

#### <a name="syntax"></a>構文

```cpp
DEFINE_COMMAND_EX(x, wszCommand)
```

#### <a name="parameters"></a>パラメーター

*X*<br/>
[in]ユーザー・レコード (コマンド) クラスの名前。

*コマンド*<br/>
[in][CCommand](../../data/oledb/ccommand-class.md)を使用するときに行セットを作成するために使用されるコマンド文字列。

#### <a name="remarks"></a>解説

[CCommand::Open](../../data/oledb/ccommand-open.md)メソッドでコマンド テキストを指定しない場合、指定したコマンド文字列が既定として使用されます。

このマクロは、アプリケーションの種類に関係なく、Unicode 文字列を受け取ります。 このマクロは、UNIcode と ANSI アプリケーションをサポートしているため[、DEFINE_COMMAND](../../data/oledb/define-command.md)よりも優先されます。

#### <a name="example"></a>例

[BOOKMARK_ENTRY](../../data/oledb/bookmark-entry.md)を参照してください。

### <a name="begin_param_map"></a><a name="begin_param_map"></a>BEGIN_PARAM_MAP

パラメーター マップ エントリの先頭を示します。

#### <a name="syntax"></a>構文

```cpp
BEGIN_PARAM_MAP(x)
```

#### <a name="parameters"></a>パラメーター

*X*<br/>
[入力] ユーザー レコード クラスの名前。

#### <a name="remarks"></a>解説

パラメータは[コマンド](/previous-versions/windows/desktop/ms724608(v=vs.85))によって使用されます。

#### <a name="example"></a>例

[BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md)マクロの例を参照してください。

### <a name="end_param_map"></a><a name="end_param_map"></a>END_PARAM_MAP

パラメーター マップ エントリの末尾をマークします。

#### <a name="syntax"></a>構文

```cpp
END_PARAM_MAP()
```

#### <a name="example"></a>例

[BEGIN_PARAM_MAP](../../data/oledb/begin-param-map.md)マクロの例を参照してください。

### <a name="set_param_type"></a><a name="set_param_type"></a>SET_PARAM_TYPE

マクロCOLUMN_ENTRY入力、出力、または入出力SET_PARAM_TYPEに続くマクロを指定します。

#### <a name="syntax"></a>構文

```cpp
SET_PARAM_TYPE(type)
```

#### <a name="parameters"></a>パラメーター

*type*<br/>
[入力] 設定するパラメーターの種類。

#### <a name="remarks"></a>解説

プロバイダーは、基になるデータ ソースによってサポートされているパラメーター入出力タイプだけをサポートします。 この型は、1 つ以上`DBPARAMIO`の値の組み合わせです *(OLE DB プログラマ リファレンス*の[DBBINDING 構造体](/previous-versions/windows/desktop/ms716845(v=vs.85))を参照)。

- `DBPARAMIO_NOTPARAM`アクセサーにパラメーターがありません。 通常、パラメーターが`eParamIO`無視されることをユーザーに通知するために、行アクセサーでこの値を設定します。

- `DBPARAMIO_INPUT`入力パラメーター。

- `DBPARAMIO_OUTPUT`出力パラメーター。

- `DBPARAMIO_INPUT | DBPARAMIO_OUTPUT`このパラメーターは、入力パラメーターと出力パラメーターの両方です。

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

## <a name="requirements"></a>必要条件

**ヘッダー:** atldbcli.h

## <a name="see-also"></a>関連項目

[OLE DB コンシューマー テンプレートのマクロとグローバル関数](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)<br/>
[OLE DB コンシューマー テンプレート](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB コンシューマー テンプレート リファレンス](../../data/oledb/ole-db-consumer-templates-reference.md)
