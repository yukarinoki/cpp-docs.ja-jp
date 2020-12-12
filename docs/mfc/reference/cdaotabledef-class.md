---
description: '詳細情報: CDaoTableDef クラス'
title: CDaoTableDef クラス
ms.date: 11/04/2016
f1_keywords:
- CDaoTableDef
- AFXDAO/CDaoTableDef
- AFXDAO/CDaoTableDef::CDaoTableDef
- AFXDAO/CDaoTableDef::Append
- AFXDAO/CDaoTableDef::CanUpdate
- AFXDAO/CDaoTableDef::Close
- AFXDAO/CDaoTableDef::Create
- AFXDAO/CDaoTableDef::CreateField
- AFXDAO/CDaoTableDef::CreateIndex
- AFXDAO/CDaoTableDef::DeleteField
- AFXDAO/CDaoTableDef::DeleteIndex
- AFXDAO/CDaoTableDef::GetAttributes
- AFXDAO/CDaoTableDef::GetConnect
- AFXDAO/CDaoTableDef::GetDateCreated
- AFXDAO/CDaoTableDef::GetDateLastUpdated
- AFXDAO/CDaoTableDef::GetFieldCount
- AFXDAO/CDaoTableDef::GetFieldInfo
- AFXDAO/CDaoTableDef::GetIndexCount
- AFXDAO/CDaoTableDef::GetIndexInfo
- AFXDAO/CDaoTableDef::GetName
- AFXDAO/CDaoTableDef::GetRecordCount
- AFXDAO/CDaoTableDef::GetSourceTableName
- AFXDAO/CDaoTableDef::GetValidationRule
- AFXDAO/CDaoTableDef::GetValidationText
- AFXDAO/CDaoTableDef::IsOpen
- AFXDAO/CDaoTableDef::Open
- AFXDAO/CDaoTableDef::RefreshLink
- AFXDAO/CDaoTableDef::SetAttributes
- AFXDAO/CDaoTableDef::SetConnect
- AFXDAO/CDaoTableDef::SetName
- AFXDAO/CDaoTableDef::SetSourceTableName
- AFXDAO/CDaoTableDef::SetValidationRule
- AFXDAO/CDaoTableDef::SetValidationText
- AFXDAO/CDaoTableDef::m_pDAOTableDef
- AFXDAO/CDaoTableDef::m_pDatabase
helpviewer_keywords:
- CDaoTableDef [MFC], CDaoTableDef
- CDaoTableDef [MFC], Append
- CDaoTableDef [MFC], CanUpdate
- CDaoTableDef [MFC], Close
- CDaoTableDef [MFC], Create
- CDaoTableDef [MFC], CreateField
- CDaoTableDef [MFC], CreateIndex
- CDaoTableDef [MFC], DeleteField
- CDaoTableDef [MFC], DeleteIndex
- CDaoTableDef [MFC], GetAttributes
- CDaoTableDef [MFC], GetConnect
- CDaoTableDef [MFC], GetDateCreated
- CDaoTableDef [MFC], GetDateLastUpdated
- CDaoTableDef [MFC], GetFieldCount
- CDaoTableDef [MFC], GetFieldInfo
- CDaoTableDef [MFC], GetIndexCount
- CDaoTableDef [MFC], GetIndexInfo
- CDaoTableDef [MFC], GetName
- CDaoTableDef [MFC], GetRecordCount
- CDaoTableDef [MFC], GetSourceTableName
- CDaoTableDef [MFC], GetValidationRule
- CDaoTableDef [MFC], GetValidationText
- CDaoTableDef [MFC], IsOpen
- CDaoTableDef [MFC], Open
- CDaoTableDef [MFC], RefreshLink
- CDaoTableDef [MFC], SetAttributes
- CDaoTableDef [MFC], SetConnect
- CDaoTableDef [MFC], SetName
- CDaoTableDef [MFC], SetSourceTableName
- CDaoTableDef [MFC], SetValidationRule
- CDaoTableDef [MFC], SetValidationText
- CDaoTableDef [MFC], m_pDAOTableDef
- CDaoTableDef [MFC], m_pDatabase
ms.assetid: 7c5d2254-8475-43c4-8a6c-2d32ead194c9
ms.openlocfilehash: ead41d1dae2d248324809690e778e8f623a73caf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97248022"
---
# <a name="cdaotabledef-class"></a>CDaoTableDef クラス

ベース テーブル、またはアタッチ テーブルの格納された定義を表現します。

## <a name="syntax"></a>構文

```
class CDaoTableDef : public CObject
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CDaoTableDef::CDaoTableDef](#cdaotabledef)|`CDaoTableDef` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CDaoTableDef:: Append](#append)|新しいテーブルをデータベースに追加します。|
|[CDaoTableDef:: CanUpdate](#canupdate)|テーブルを更新できる場合は0以外の値を返します (フィールドの定義またはテーブルのプロパティを変更できます)。|
|[CDaoTableDef:: Close](#close)|開いているテーブルを閉じます。|
|[CDaoTableDef:: Create](#create)|[Append](#append)を使用してデータベースに追加できるテーブルを作成します。|
|[CDaoTableDef::CreateField](#createfield)|テーブルのフィールドを作成するために呼び出されます。|
|[CDaoTableDef:: CreateIndex](#createindex)|テーブルのインデックスを作成するために呼び出されます。|
|[CDaoTableDef::D eleteField](#deletefield)|テーブルからフィールドを削除するために呼び出されます。|
|[CDaoTableDef::D eleteIndex](#deleteindex)|テーブルからインデックスを削除するために呼び出されます。|
|[CDaoTableDef:: GetAttributes](#getattributes)|オブジェクトの1つまたは複数の特性を示す値を返し `CDaoTableDef` ます。|
|[CDaoTableDef:: GetConnect](#getconnect)|テーブルのソースに関する情報を提供する値を返します。|
|[CDaoTableDef::GetDateCreated](#getdatecreated)|オブジェクトの基になるベーステーブルが作成された日付と時刻を返し `CDaoTableDef` ます。|
|[CDaoTableDef:: GetDateLastUpdated](#getdatelastupdated)|ベーステーブルのデザインに対して行われた最新の変更の日付と時刻を返します。|
|[CDaoTableDef:: GetFieldCount](#getfieldcount)|テーブル内のフィールドの数を表す値を返します。|
|[CDaoTableDef:: GetFieldInfo](#getfieldinfo)|テーブル内のフィールドに関する特定の種類の情報を返します。|
|[CDaoTableDef:: GetIndexCount](#getindexcount)|テーブルのインデックスの数を返します。|
|[CDaoTableDef:: GetIndexInfo](#getindexinfo)|テーブルのインデックスに関する特定の種類の情報を返します。|
|[CDaoTableDef:: GetName](#getname)|テーブルのユーザー定義名を返します。|
|[CDaoTableDef:: GetRecordCount](#getrecordcount)|テーブル内のレコードの数を返します。|
|[CDaoTableDef:: GetSourceTableName](#getsourcetablename)|ソースデータベース内のアタッチされるテーブルの名前を示す値を返します。|
|[CDaoTableDef:: GetValidationRule](#getvalidationrule)|フィールドが変更されたとき、またはテーブルに追加されたときに、そのデータを検証する値を返します。|
|[CDaoTableDef:: GetValidationText](#getvalidationtext)|フィールドオブジェクトの値が指定された検証規則を満たしていない場合に、アプリケーションが表示するメッセージのテキストを指定する値を返します。|
|[CDaoTableDef:: IsOpen](#isopen)|テーブルが開いている場合は0以外の値を返します。|
|[CDaoTableDef:: Open](#open)|データベースの TableDef's コレクションに格納されている既存のテーブルグループを開きます。|
|[CDaoTableDef:: RefreshLink](#refreshlink)|アタッチされたテーブルの接続情報を更新します。|
|[CDaoTableDef:: SetAttributes](#setattributes)|オブジェクトの1つまたは複数の特性を示す値を設定 `CDaoTableDef` します。|
|[CDaoTableDef:: SetConnect](#setconnect)|テーブルのソースに関する情報を提供する値を設定します。|
|[CDaoTableDef:: SetName](#setname)|テーブルの名前を設定します。|
|[CDaoTableDef:: SetSourceTableName](#setsourcetablename)|ソースデータベース内のアタッチされるテーブルの名前を指定する値を設定します。|
|[CDaoTableDef:: SetValidationRule](#setvalidationrule)|フィールドが変更されたとき、またはテーブルに追加されたときに、そのデータを検証する値を設定します。|
|[CDaoTableDef:: SetValidationText](#setvalidationtext)|フィールドオブジェクトの値が指定した検証規則を満たしていない場合に、アプリケーションが表示するメッセージのテキストを指定する値を設定します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[CDaoTableDef:: m_pDAOTableDef](#m_pdaotabledef)|Tabledef オブジェクトの基になる DAO インターフェイスへのポインター。|
|[CDaoTableDef:: m_pDatabase](#m_pdatabase)|このテーブルのソースデータベース。|

## <a name="remarks"></a>解説

各 DAO データベースオブジェクトは、保存されているすべての DAO テーブルオブジェクトを含む、"テーブルの構成" と呼ばれるコレクションを保持します。

オブジェクトを使用してテーブル定義を操作し `CDaoTableDef` ます。 たとえば、次のように操作できます。

- データベース内のローカル、アタッチ、または外部テーブルのフィールドとインデックス構造を確認します。

- `SetConnect`アタッチされたテーブルに対しておよびのメンバー関数を呼び出し、 `SetSourceTableName` メンバー関数を使用して `RefreshLink` アタッチされたテーブルへの接続を更新します。

- メンバー関数を呼び出して、 `CanUpdate` テーブル内のフィールド定義を編集できるかどうかを判断します。

- および、およびメンバー関数とを使用して、検証条件を取得または設定し `GetValidationRule` `SetValidationRule` `GetValidationText` `SetValidationText` ます。

- メンバー関数を使用して、 `Open` テーブル、ダイナセット、またはスナップショット型のオブジェクトを作成し `CDaoRecordset` ます。

    > [!NOTE]
    >  DAO データベースクラスは、Open Database Connectivity (ODBC) に基づく MFC データベースクラスとは異なります。 すべての DAO データベースクラス名には、"CDao" プレフィックスが付いています。 DAO クラスを使用して ODBC データソースにアクセスすることもできます。DAO クラスは、一般に、Microsoft Jet データベースエンジンに固有のものであるため、優れた機能を提供します。

### <a name="to-use-tabledef-objects-either-to-work-with-an-existing-table-or-to-create-a-new-table"></a>既存のテーブルを操作したり、新しいテーブルを作成したりするために、tabledef オブジェクトを使用するには

1. いずれの場合も、最初にオブジェクトを構築し `CDaoTableDef` 、テーブルが属する [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) オブジェクトへのポインターを提供します。

1. 必要に応じて、次の操作を行います。

   - 既存の保存されたテーブルを使用するには、テーブルの名前を指定して、tabledef オブジェクトの [Open](#open) メンバー関数を呼び出します。

   - 新しいテーブルを作成するには、テーブルの名前を指定して、tabledef オブジェクトの [create](#create) member 関数を呼び出します。 [CreateField](#createfield)と[createindex](#createindex)を呼び出して、テーブルにフィールドとインデックスを追加します。

   - [Append](#append)を呼び出して、データベースのテーブルのコレクションに追加してテーブルを保存します。 `Create` テーブルテーブルをオープン状態にします。そのため、を呼び出した後に `Create` を呼び出さないで `Open` ください。

        > [!TIP]
        >  保存されたテーブルを作成する最も簡単な方法は、これらを作成し、Microsoft Access を使用してデータベースに格納することです。 次に、MFC コードでそれらを開いて使用できます。

開いているまたは作成した tabledef オブジェクトを使用するには、オブジェクトを作成して開き `CDaoRecordset` 、 `dbOpenTable` *noて type* パラメーターの値を持つテーブル名を指定します。

オブジェクトを作成するために tabledef オブジェクトを使用するには、 `CDaoRecordset` 通常、前に説明したように tabledef を作成または開き、次に、レコードセットオブジェクトを構築して、 [CDaoRecordset:: open](../../mfc/reference/cdaorecordset-class.md#open)を呼び出すと、tabledef オブジェクトへのポインターを渡します。 渡すテーブルテーブルは、オープン状態である必要があります。 詳細については、「クラス [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)」を参照してください。

Tabledef オブジェクトの使用が終了したら、 [Close](../../mfc/reference/cdaorecordset-class.md#close) メンバー関数を呼び出します。次に、tabledef オブジェクトを破棄します。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

`CDaoTableDef`

## <a name="requirements"></a>要件

**ヘッダー:** afxdao

## <a name="cdaotabledefappend"></a><a name="append"></a> CDaoTableDef:: Append

[Create](#create)を呼び出した後にこのメンバー関数を呼び出して、データベースにテーブルテーブルを保存するための新しい tabledef オブジェクトを作成します。

```
virtual void Append();
```

### <a name="remarks"></a>解説

関数は、データベースのテーブル定義コレクションにオブジェクトを追加します。 テーブルを追加せずに一時オブジェクトとして使用することができますが、それを保存して使用する場合は、を呼び出す必要があり `Append` ます。

> [!NOTE]
> 名前のない tabledef (null または空の文字列を含む) を追加しようとすると、MFC は例外をスローします。

関連情報については、DAO ヘルプのトピック「Append メソッド」を参照してください。

## <a name="cdaotabledefcanupdate"></a><a name="canupdate"></a> CDaoTableDef:: CanUpdate

オブジェクトの基になるテーブルの定義を変更できるかどうかを判断するには、このメンバー関数を呼び出し `CDaoTableDef` ます。

```
BOOL CanUpdate();
```

### <a name="return-value"></a>戻り値

テーブル構造 (スキーマ) を変更できる場合は0以外 (フィールドとインデックスを追加または削除する場合)、それ以外の場合は0。

### <a name="remarks"></a>解説

既定では、オブジェクトの基になる新しく作成されたテーブルを `CDaoTableDef` 更新できます。また、オブジェクトの基になるアタッチされたテーブルを更新することはでき `CDaoTableDef` ません。 `CDaoTableDef`生成されたレコードセットが更新可能でない場合でも、オブジェクトは更新可能な場合があります。

関連情報については、DAO ヘルプの「更新可能なプロパティ」を参照してください。

## <a name="cdaotabledefcdaotabledef"></a><a name="cdaotabledef"></a> CDaoTableDef::CDaoTableDef

`CDaoTableDef` オブジェクトを構築します。

```
CDaoTableDef(CDaoDatabase* pDatabase);
```

### <a name="parameters"></a>パラメーター

*pDatabase*<br/>
[CDaoDatabase](../../mfc/reference/cdaodatabase-class.md)オブジェクトへのポインター。

### <a name="remarks"></a>解説

オブジェクトを構築した後、 [Create](#create) または [Open](#open) メンバー関数を呼び出す必要があります。 オブジェクトを終了したら、 [Close](#close) メンバー関数を呼び出してオブジェクトを破棄する必要があり `CDaoTableDef` ます。

## <a name="cdaotabledefclose"></a><a name="close"></a> CDaoTableDef:: Close

このメンバー関数を呼び出して、tabledef オブジェクトを閉じて解放します。

```
virtual void Close();
```

### <a name="remarks"></a>解説

通常、を呼び出した後で `Close` 、tabledef オブジェクトがで割り当てられている場合は、そのオブジェクトを削除し **`new`** ます。

を呼び出した後、もう一度 [Open](#open) を呼び出すことができ `Close` ます。 これにより、tabledef オブジェクトを再利用できます。

関連情報については、DAO ヘルプの「Close メソッド」を参照してください。

## <a name="cdaotabledefcreate"></a><a name="create"></a> CDaoTableDef:: Create

新しい保存されたテーブルを作成するには、このメンバー関数を呼び出します。

```
virtual void Create(
    LPCTSTR lpszName,
    long lAttributes = 0,
    LPCTSTR lpszSrcTable = NULL,
    LPCTSTR lpszConnect = NULL);
```

### <a name="parameters"></a>パラメーター

*lpszName*<br/>
テーブルの名前を含む文字列へのポインター。

*lAttributes*<br/>
Tabledef オブジェクトによって表されるテーブルの特性に対応する値。 ビットごとの OR を使用して、次の定数のいずれかを組み合わせることができます。

|定数|説明|
|--------------|-----------------|
|`dbAttachExclusive`|Microsoft Jet データベースエンジンを使用するデータベースの場合、テーブルは、排他的に使用するために開かれた添付テーブルであることを示します。|
|`dbAttachSavePWD`|Microsoft Jet データベースエンジンを使用するデータベースの場合、アタッチされたテーブルのユーザー ID とパスワードが接続情報と共に保存されることを示します。|
|`dbSystemObject`|テーブルが Microsoft Jet データベースエンジンによって提供されるシステムテーブルであることを示します。|
|`dbHiddenObject`|表が Microsoft Jet データベースエンジンによって提供される非表示のテーブルであることを示します。|

*lpszSrcTable*<br/>
ソーステーブル名を格納している文字列へのポインター。 既定では、この値は NULL として初期化されます。

*lpszConnect*<br/>
既定の接続文字列を含む文字列へのポインター。 既定では、この値は NULL として初期化されます。

### <a name="remarks"></a>解説

Tabledef という名前を付けたら、 [Append](#append) を呼び出して、データベースのテーブル定義コレクションにテーブルグループを保存できます。 を呼び出す `Append` と、tabledef がオープン状態になり、それを使用して [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) オブジェクトを作成できるようになります。

関連情報については、DAO ヘルプの「CreateTableDef メソッド」を参照してください。

## <a name="cdaotabledefcreatefield"></a><a name="createfield"></a> CDaoTableDef::CreateField

このメンバー関数を呼び出して、テーブルにフィールドを追加します。

```cpp
void CreateField(
    LPCTSTR lpszName,
    short nType,
    long lSize,
    long lAttributes = 0);

void CreateField(CDaoFieldInfo& fieldinfo);
```

### <a name="parameters"></a>パラメーター

*lpszName*<br/>
このフィールドの名前を指定する文字列式へのポインター。

*nType*<br/>
フィールドのデータ型を示す値です。 設定には、次のいずれかの値を指定できます。

|Type|サイズ (バイト)|説明|
|----------|--------------------|-----------------|
|`dbBoolean`|1 バイト|BOOL|
|`dbByte`|BYTE|
|`dbInteger`|2|INT|
|`dbLong`|4|long|
|`dbCurrency`|8|通貨 ( [COleCurrency](../../mfc/reference/colecurrency-class.md))|
|`dbSingle`|4|float|
|`dbDouble`|8|double|
|`dbDate`|8|日付/時刻 ( [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md))|
|`dbText`|1 - 255|テキスト ( [CString](../../atl-mfc-shared/reference/cstringt-class.md))|
|`dbLongBinary`|0|Long Binary (OLE オブジェクト)、 [CLongBinary](../../mfc/reference/clongbinary-class.md) 、または [CByteArray](../../mfc/reference/cbytearray-class.md)|
|`dbMemo`|0|メモ ( [CString](../../atl-mfc-shared/reference/cstringt-class.md))|

*lSize*<br/>
テキストを格納しているフィールドの最大サイズ (バイト単位)、またはテキストまたは数値を格納するフィールドの固定サイズを示す値。 *Lsize* パラメーターは、すべてのテキストフィールド以外では無視されます。

*lAttributes*<br/>
フィールドの特性に対応する値。ビットごとの OR を使用して組み合わせることができます。

|定数|説明|
|--------------|-----------------|
|`dbFixedField`|フィールドサイズは固定されています (数値フィールドの既定値)。|
|`dbVariableField`|フィールドサイズは変数です (テキストフィールドのみ)。|
|`dbAutoIncrField`|新しいレコードのフィールド値は、変更できない一意の長整数に自動的にインクリメントされます。 Microsoft Jet データベーステーブルでのみサポートされています。|
|`dbUpdatableField`|フィールド値は変更できます。|
|`dbDescending`|フィールドは降順 (Z-A または 100-0) の順序で並べ替えられます (インデックスオブジェクトのフィールドコレクション内のフィールドオブジェクトにのみ適用されます)。 この定数を省略した場合、フィールドは昇順 (A-z または 0-100) の順序 (既定値) で並べ替えられます。|

*fieldinfo*<br/>
[CDaoFieldInfo](../../mfc/reference/cdaofieldinfo-structure.md)構造体への参照。

### <a name="remarks"></a>解説

(Ole `DAOField` ) オブジェクトが作成され、 `DAOTableDef` (ole) オブジェクトの Fields コレクションに追加されます。 オブジェクトのプロパティを調べるために使用するだけでなく、を使用し `CDaoFieldInfo` て、テーブルテーブルに新しいフィールドを作成するための入力パラメーターを作成することもできます。 の最初のバージョン `CreateField` は簡単に使用できますが、さらに細かく制御する場合は、パラメーターを受け取るの2番目のバージョンを使用でき `CreateField` `CDaoFieldInfo` ます。

パラメーターを受け取るのバージョンを使用する場合は、 `CreateField` `CDaoFieldInfo` 構造体の次の各メンバーを慎重に設定する必要があり `CDaoFieldInfo` ます。

- `m_strName`

- `m_nType`

- `m_lSize`

- `m_lAttributes`

- `m_bAllowZeroLength`

の残りのメンバーは、 `CDaoFieldInfo` メンバーに応じて **0**、FALSE、または空の文字列に設定する必要があり `CDaoException` ます。そうでない場合は、が発生することがあります。

関連情報については、DAO ヘルプの「CreateField メソッド」を参照してください。

## <a name="cdaotabledefcreateindex"></a><a name="createindex"></a> CDaoTableDef:: CreateIndex

テーブルにインデックスを追加するには、この関数を呼び出します。

```cpp
void CreateIndex(CDaoIndexInfo& indexinfo);
```

### <a name="parameters"></a>パラメーター

*indexinfo*<br/>
[CDaoIndexInfo](../../mfc/reference/cdaoindexinfo-structure.md)構造体への参照。

### <a name="remarks"></a>解説

インデックスは、データベーステーブルからアクセスされるレコードの順序、および重複するレコードが許容されるかどうかを指定します。 また、インデックスを使用すると、データに効率的にアクセスできます。

テーブルに対してインデックスを作成する必要はありませんが、大きなインデックスのないテーブルでは、特定のレコードへのアクセスやレコードセットの作成に時間がかかることがあります。 一方、インデックスが多すぎると、すべてのインデックスが自動的に更新されるため、更新、追加、および削除の操作速度が低下します。 作成するインデックスを決定する際には、次の要素を考慮してください。

構造体の次のメンバーを `CDaoIndexInfo` 設定する必要があります。

- `m_strName` 名前を指定する必要があります。

- `m_pFieldInfos` 構造体の配列を指す必要があり `CDaoIndexFieldInfo` ます。

- `m_nFields` 構造体の配列内のフィールド数を指定する必要があり `CDaoFieldInfo` ます。

FALSE に設定すると、残りのメンバーは無視されます。 また、 `m_lDistinctCount` インデックスの作成時にメンバーは無視されます。

## <a name="cdaotabledefdeletefield"></a><a name="deletefield"></a> CDaoTableDef::D eleteField

このメンバー関数を呼び出して、フィールドを削除し、アクセスできないようにします。

```cpp
void DeleteField(LPCTSTR lpszName);
void DeleteField(int nIndex);
```

### <a name="parameters"></a>パラメーター

*lpszName*<br/>
既存のフィールドの名前である文字列式へのポインター。

*nIndex*<br/>
インデックスによる検索のための、テーブルの0から始まるフィールドコレクション内のフィールドのインデックス。

### <a name="remarks"></a>解説

このメンバー関数は、データベースに追加されていない新しいオブジェクトに対して使用できます。また、 [CanUpdate](#canupdate) が0以外の値を返した場合にも使用できます。

関連情報については、DAO ヘルプの「Delete メソッド」を参照してください。

## <a name="cdaotabledefdeleteindex"></a><a name="deleteindex"></a> CDaoTableDef::D eleteIndex

基になるテーブルのインデックスを削除するには、このメンバー関数を呼び出します。

```cpp
void DeleteIndex(LPCTSTR lpszName);
void DeleteIndex(int nIndex);
```

### <a name="parameters"></a>パラメーター

*lpszName*<br/>
既存のインデックスの名前を表す文字列式へのポインター。

*nIndex*<br/>
インデックスによる検索のための、データベースの0から始まるインデックス作成コレクション内のインデックスオブジェクトの配列インデックス。

### <a name="remarks"></a>解説

このメンバー関数は、データベースに追加されていない新しいオブジェクトに対して使用できます。また、 [CanUpdate](#canupdate) が0以外の値を返した場合にも使用できます。

関連情報については、DAO ヘルプの「Delete メソッド」を参照してください。

## <a name="cdaotabledefgetattributes"></a><a name="getattributes"></a> CDaoTableDef:: GetAttributes

オブジェクトの場合 `CDaoTableDef` 、戻り値は、オブジェクトによって表されるテーブルの特性を指定し、 `CDaoTableDef` 次の定数の合計にすることができます。

```
long GetAttributes();
```

### <a name="return-value"></a>戻り値

オブジェクトの1つまたは複数の特性を示す値を返し `CDaoTableDef` ます。

### <a name="remarks"></a>解説

|定数|説明|
|--------------|-----------------|
|`dbAttachExclusive`|Microsoft Jet データベースエンジンを使用するデータベースの場合、テーブルは、排他的に使用するために開かれた添付テーブルであることを示します。|
|`dbAttachSavePWD`|Microsoft Jet データベースエンジンを使用するデータベースの場合、アタッチされたテーブルのユーザー ID とパスワードが接続情報と共に保存されることを示します。|
|`dbSystemObject`|テーブルが Microsoft Jet データベースエンジンによって提供されるシステムテーブルであることを示します。|
|`dbHiddenObject`|表が Microsoft Jet データベースエンジンによって提供される非表示のテーブルであることを示します。|
|`dbAttachedTable`|テーブルが、非 ODBC データベース (Paradox データベースなど) からアタッチされたテーブルであることを示します。|
|`dbAttachedODBC`|テーブルが、Microsoft SQL Server などの ODBC データベースからアタッチされたテーブルであることを示します。|

システムテーブルは、Microsoft Jet データベースエンジンによって作成されたテーブルで、さまざまな内部情報を格納します。

非表示テーブルは、Microsoft Jet データベースエンジンによって一時的に使用されるように作成されたテーブルです。

関連情報については、DAO ヘルプの「Attributes プロパティ」を参照してください。

## <a name="cdaotabledefgetconnect"></a><a name="getconnect"></a> CDaoTableDef:: GetConnect

このメンバー関数を呼び出して、データソースの接続文字列を取得します。

```
CString GetConnect();
```

### <a name="return-value"></a>戻り値

`CString`テーブルのパスとデータベースの種類を表すオブジェクトです。

### <a name="remarks"></a>解説

`CDaoTableDef`アタッチされたテーブルを表すオブジェクトの場合、 `CString` オブジェクトは1つまたは2つの部分 (データベース型指定子とデータベースへのパス) で構成されます。

次の表に示すパスは、データベースファイルが格納されているディレクトリの完全なパスです。前に識別子 "DATABASE =" を付ける必要があります。 場合によっては (Microsoft Jet および Microsoft Excel データベースと同様に)、データベースパス引数に特定のファイル名が含まれます。

[CDaoTableDef:: SetConnect](#setconnect)の表は、使用可能なデータベースの種類と、それに対応するデータベースの指定子とパスを示しています。

Microsoft Jet データベースベーステーブルの場合、指定子は空の文字列 ("") です。

パスワードが必要ですが指定されていない場合、ODBC ドライバーでは、最初にテーブルにアクセスしたときにログインダイアログボックスが表示され、接続が閉じられてから再び開かれた場合には再び表示されます。 アタッチされたテーブルに属性がある場合 `dbAttachSavePWD` 、そのテーブルが再度開かれても、ログインプロンプトは表示されません。

関連情報については、DAO ヘルプのトピック「Connect プロパティ」を参照してください。

## <a name="cdaotabledefgetdatecreated"></a><a name="getdatecreated"></a> CDaoTableDef::GetDateCreated

この関数を呼び出して、オブジェクトの基になっているテーブルが作成された日付と時刻を確認し `CDaoTableDef` ます。

```
COleDateTime GetDateCreated();
```

### <a name="return-value"></a>戻り値

オブジェクトの基になるテーブルが作成された日付と時刻を表す値 `CDaoTableDef` です。

### <a name="remarks"></a>解説

日付と時刻の設定は、ベーステーブルが作成されたコンピューター、または最後に更新されたコンピューターから取得されます。 マルチユーザー環境では、ユーザーはこれらの設定をファイルサーバーから直接取得して、不整合を回避する必要があります。つまり、すべてのクライアントが "標準" タイムソースを使用する必要があります。たとえば、1台のサーバーからです。

関連情報については、DAO ヘルプの「DateCreated、LastUpdated Properties」を参照してください。

## <a name="cdaotabledefgetdatelastupdated"></a><a name="getdatelastupdated"></a> CDaoTableDef:: GetDateLastUpdated

オブジェクトの基になっているテーブルが最後に更新された日付と時刻を確認するには、この関数を呼び出し `CDaoTableDef` ます。

```
COleDateTime GetDateLastUpdated();
```

### <a name="return-value"></a>戻り値

オブジェクトの基になっているテーブルが最後に更新された日付と時刻を表す値です `CDaoTableDef` 。

### <a name="remarks"></a>解説

日付と時刻の設定は、ベーステーブルが作成されたコンピューター、または最後に更新されたコンピューターから取得されます。 マルチユーザー環境では、ユーザーはこれらの設定をファイルサーバーから直接取得して、不整合を回避する必要があります。つまり、すべてのクライアントが "標準" タイムソースを使用する必要があります。たとえば、1台のサーバーからです。

関連情報については、DAO ヘルプの「DateCreated、LastUpdated Properties」を参照してください。

## <a name="cdaotabledefgetfieldcount"></a><a name="getfieldcount"></a> CDaoTableDef:: GetFieldCount

このメンバー関数を呼び出して、テーブルで定義されているフィールドの数を取得します。

```
short GetFieldCount();
```

### <a name="return-value"></a>戻り値

テーブル内のフィールドの数。

### <a name="remarks"></a>解説

値が0の場合、コレクションにはオブジェクトが存在しません。

関連情報については、DAO ヘルプのトピック「Count プロパティ」を参照してください。

## <a name="cdaotabledefgetfieldinfo"></a><a name="getfieldinfo"></a> CDaoTableDef:: GetFieldInfo

このメンバー関数を呼び出して、テーブル名に定義されているフィールドに関するさまざまな種類の情報を取得します。

```cpp
void GetFieldInfo(
    int nIndex,
    CDaoFieldInfo& fieldinfo,
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);

void GetFieldInfo(
    LPCTSTR lpszName,
    CDaoFieldInfo& fieldinfo,
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
インデックスによる検索のための、テーブルの0から始まるフィールドコレクション内のフィールドオブジェクトのインデックス。

*fieldinfo*<br/>
[CDaoFieldInfo](../../mfc/reference/cdaofieldinfo-structure.md)構造体への参照。

*オプション*<br/>
取得するフィールドに関する情報を指定するオプション。 使用可能なオプションは、関数が返す原因と共にここに表示されます。

- `AFX_DAO_PRIMARY_INFO` 標準名前、種類、サイズ、属性。 このオプションは、最速のパフォーマンスを実現するために使用します。

- `AFX_DAO_SECONDARY_INFO` 主要な情報 (序数の位置、必須、長さ0の許可、照合順序、外部名、ソースフィールド、ソーステーブル)

- `AFX_DAO_ALL_INFO` プライマリとセカンダリの情報に加え、検証規則、検証テキスト、既定値

*lpszName*<br/>
名前による検索のためのフィールドオブジェクトの名前へのポインター。 名前は、最大64文字の文字列で、フィールドに一意の名前を付けます。

### <a name="remarks"></a>解説

関数の1つのバージョンでは、インデックスを使用してフィールドを検索できます。 もう1つのバージョンでは、名前でフィールドを検索できます。

返される情報の説明については、「 [CDaoFieldInfo](../../mfc/reference/cdaofieldinfo-structure.md) 構造体」を参照してください。 この構造体には、前に説明した情報の項目に対応するメンバーが含まれ *ています。* 1つのレベルで情報を要求すると、以前のレベルについても情報が得られます。

関連情報については、DAO ヘルプの「Attributes プロパティ」を参照してください。

## <a name="cdaotabledefgetindexcount"></a><a name="getindexcount"></a> CDaoTableDef:: GetIndexCount

テーブルのインデックスの数を取得するには、このメンバー関数を呼び出します。

```
short GetIndexCount();
```

### <a name="return-value"></a>戻り値

テーブルのインデックスの数。

### <a name="remarks"></a>解説

値が0の場合、コレクションにはインデックスがありません。

関連情報については、DAO ヘルプのトピック「Count プロパティ」を参照してください。

## <a name="cdaotabledefgetindexinfo"></a><a name="getindexinfo"></a> CDaoTableDef:: GetIndexInfo

このメンバー関数を呼び出して、テーブル定義で定義されているインデックスに関するさまざまな種類の情報を取得します。

```cpp
void GetIndexInfo(
    int nIndex,
    CDaoIndexInfo& indexinfo,
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);

void GetIndexInfo(
    LPCTSTR lpszName,
    CDaoIndexInfo& indexinfo,
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
コレクション内の位置によって検索するための、テーブルの0から始まるインデックスコレクション内のインデックスオブジェクトの数値インデックス。

*indexinfo*<br/>
[CDaoIndexInfo](../../mfc/reference/cdaoindexinfo-structure.md)構造体への参照。

*オプション*<br/>
取得するインデックスに関する情報を指定するオプション。 使用可能なオプションは、関数が返す原因と共にここに表示されます。

- `AFX_DAO_PRIMARY_INFO` 名前、フィールド情報、フィールド。 このオプションは、最速のパフォーマンスを実現するために使用します。

- `AFX_DAO_SECONDARY_INFO` プライマリ情報、プラス: Primary、Unique、Clustered、Ignore Null、Required、Foreign

- `AFX_DAO_ALL_INFO` プライマリとセカンダリの情報、および個別のカウント

*lpszName*<br/>
名前で検索するための、インデックスオブジェクトの名前へのポインター。

### <a name="remarks"></a>解説

関数の1つのバージョンでは、インデックスをコレクション内の位置で検索できます。 もう1つのバージョンでは、インデックスを名前で検索できます。

返される情報の説明については、「 [CDaoIndexInfo](../../mfc/reference/cdaoindexinfo-structure.md) 構造体」を参照してください。 この構造体には、前に説明した情報の項目に対応するメンバーが含まれ *ています。* 1つのレベルで情報を要求すると、以前のレベルについても情報が得られます。

関連情報については、DAO ヘルプの「Attributes プロパティ」を参照してください。

## <a name="cdaotabledefgetname"></a><a name="getname"></a> CDaoTableDef:: GetName

基になるテーブルのユーザー定義の名前を取得するには、このメンバー関数を呼び出します。

```
CString GetName();
```

### <a name="return-value"></a>戻り値

テーブルのユーザー定義の名前。

### <a name="remarks"></a>解説

この名前は文字で始まり、最大64文字まで含めることができます。 数字とアンダースコア文字を含めることはできますが、句読点やスペースは使用できません。

関連情報については、DAO ヘルプの「Name プロパティ」を参照してください。

## <a name="cdaotabledefgetrecordcount"></a><a name="getrecordcount"></a> CDaoTableDef:: GetRecordCount

オブジェクト内のレコードの数を調べるには、このメンバー関数を呼び出し `CDaoTableDef` ます。

```
long GetRecordCount();
```

### <a name="return-value"></a>戻り値

Tabledef オブジェクトでアクセスされたレコードの数。

### <a name="remarks"></a>解説

テーブル型オブジェクトを呼び出すと、テーブル `GetRecordCount` `CDaoTableDef` 内のレコードの概数が反映され、テーブルレコードが追加および削除されるとすぐに影響を受けます。 ロールバックされたトランザクションは、 [CDaoWorkSpace:: CompactDatabase](../../mfc/reference/cdaoworkspace-class.md#compactdatabase)を呼び出すまで、レコード数の一部として表示されます。 `CDaoTableDef`レコードのないオブジェクトのレコードカウントプロパティの設定が0です。 アタッチされたテーブルまたは ODBC データベースを使用する場合、は `GetRecordCount` 常に-1 を返します。

関連情報については、DAO ヘルプの「RecordCount プロパティ」を参照してください。

## <a name="cdaotabledefgetsourcetablename"></a><a name="getsourcetablename"></a> CDaoTableDef:: GetSourceTableName

ソースデータベース内のアタッチされたテーブルの名前を取得するには、このメンバー関数を呼び出します。

```
CString GetSourceTableName();
```

### <a name="return-value"></a>戻り値

`CString`アタッチされたテーブルのソース名を示すオブジェクト、またはネイティブデータテーブルの場合は空の文字列です。

### <a name="remarks"></a>解説

アタッチされたテーブルは、Microsoft Jet データベースにリンクされている別のデータベース内のテーブルです。 アタッチされたテーブルのデータは、他のアプリケーションによって操作できる外部データベースに残ります。

関連情報については、DAO ヘルプの「SourceTableName プロパティ」を参照してください。

## <a name="cdaotabledefgetvalidationrule"></a><a name="getvalidationrule"></a> CDaoTableDef:: GetValidationRule

このメンバー関数を呼び出して、テーブル定義の検証規則を取得します。

```
CString GetValidationRule();
```

### <a name="return-value"></a>戻り値

`CString`テーブルに対して変更または追加されたときに、フィールド内のデータを検証するオブジェクト。

### <a name="remarks"></a>解説

検証規則は、更新操作との接続に使用されます。 テーブルテーブルに検証規則が含まれている場合、そのテーブルテーブルの更新は、データが変更される前に、事前に定義された条件と一致する必要があります。 変更が条件に一致しない場合は、 [Getvalidationtext](#getvalidationtext) の値を含む例外がスローされます。 オブジェクトの場合 `CDaoTableDef` 、この `CString` 値は、アタッチされたテーブルに対しては読み取り専用になり、ベーステーブルに対しては読み取り/書き込みが可能です。

関連情報については、DAO ヘルプのトピック「ValidationRule プロパティ」を参照してください。

## <a name="cdaotabledefgetvalidationtext"></a><a name="getvalidationtext"></a> CDaoTableDef:: GetValidationText

この関数を呼び出して、検証規則に一致しないデータをユーザーが入力したときに表示される文字列を取得します。

```
CString GetValidationText();
```

### <a name="return-value"></a>戻り値

`CString`検証規則に一致しないデータをユーザーが入力した場合に表示されるテキストを指定するオブジェクト。

### <a name="remarks"></a>解説

オブジェクトの場合 `CDaoTableDef` 、この `CString` 値は、アタッチされたテーブルに対しては読み取り専用になり、ベーステーブルに対しては読み取り/書き込みが可能です。

関連情報については、DAO ヘルプのトピック「ValidationText プロパティ」を参照してください。

## <a name="cdaotabledefisopen"></a><a name="isopen"></a> CDaoTableDef:: IsOpen

オブジェクトが現在開いているかどうかを判断するには、このメンバー関数を呼び出し `CDaoTableDef` ます。

```
BOOL IsOpen() const;
```

### <a name="return-value"></a>戻り値

オブジェクトが開いている場合は0以外 `CDaoTableDef` 。それ以外の場合は0。

### <a name="remarks"></a>解説

## <a name="cdaotabledefm_pdatabase"></a><a name="m_pdatabase"></a> CDaoTableDef:: m_pDatabase

このテーブルの [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) オブジェクトへのポインターが含まれています。

### <a name="remarks"></a>解説

## <a name="cdaotabledefm_pdaotabledef"></a><a name="m_pdaotabledef"></a> CDaoTableDef:: m_pDAOTableDef

オブジェクトの基になる DAO テーブルオブジェクトの OLE インターフェイスへのポインターを格納し `CDaoTableDef` ます。

### <a name="remarks"></a>解説

DAO インターフェイスに直接アクセスする必要がある場合は、このポインターを使用します。

## <a name="cdaotabledefopen"></a><a name="open"></a> CDaoTableDef:: Open

このメンバー関数を呼び出して、データベースの TableDef's コレクションに以前に保存したテーブルグループを開きます。

```
virtual void Open(LPCTSTR lpszName);
```

### <a name="parameters"></a>パラメーター

*lpszName*<br/>
テーブル名を指定する文字列へのポインター。

### <a name="remarks"></a>解説

## <a name="cdaotabledefrefreshlink"></a><a name="refreshlink"></a> CDaoTableDef:: RefreshLink

アタッチされたテーブルの接続情報を更新するには、このメンバー関数を呼び出します。

```cpp
void RefreshLink();
```

### <a name="remarks"></a>解説

アタッチされたテーブルの接続情報を変更するには、対応するオブジェクトで [Setconnect](#setconnect) を呼び出し、 `CDaoTableDef` メンバー関数を使用して `RefreshLink` 情報を更新します。 を呼び出すと、アタッチされた `RefreshLink` テーブルのプロパティは変更されません。

変更した接続情報を強制的に適用するには、このテーブルテーブルに基づくすべての開いている [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) オブジェクトを閉じる必要があります。

関連情報については、DAO ヘルプの「RefreshLink メソッド」を参照してください。

## <a name="cdaotabledefsetattributes"></a><a name="setattributes"></a> CDaoTableDef:: SetAttributes

オブジェクトの1つまたは複数の特性を示す値を設定 `CDaoTableDef` します。

```cpp
void SetAttributes(long lAttributes);
```

### <a name="parameters"></a>パラメーター

*lAttributes*<br/>
オブジェクトによって表されるテーブルの特性 `CDaoTableDef` 。これらの定数を合計することができます。

|定数|説明|
|--------------|-----------------|
|`dbAttachExclusive`|Microsoft Jet データベースエンジンを使用するデータベースの場合、テーブルは、排他的に使用するために開かれた添付テーブルであることを示します。|
|`dbAttachSavePWD`|Microsoft Jet データベースエンジンを使用するデータベースの場合、アタッチされたテーブルのユーザー ID とパスワードが接続情報と共に保存されることを示します。|
|`dbSystemObject`|テーブルが Microsoft Jet データベースエンジンによって提供されるシステムテーブルであることを示します。|
|`dbHiddenObject`|表が Microsoft Jet データベースエンジンによって提供される非表示のテーブルであることを示します。|

### <a name="remarks"></a>解説

複数の属性を設定する場合は、ビットごとの OR 演算子を使用して適切な定数を合計することで、複数の属性を組み合わせることができます。 `dbAttachExclusive`非添付テーブルでを設定すると、例外が生成されます。 次の値を組み合わせると、例外も発生します。

- **dbAttachExclusive &#124; dbAttachedODBC**

- **dbAttachSavePWD &#124; dbAttachedTable**

関連情報については、DAO ヘルプの「Attributes プロパティ」を参照してください。

## <a name="cdaotabledefsetconnect"></a><a name="setconnect"></a> CDaoTableDef:: SetConnect

`CDaoTableDef`アタッチされたテーブルを表すオブジェクトの場合、文字列オブジェクトは1つまたは2つの部分 (データベース型指定子とデータベースへのパス) で構成されます。

```cpp
void SetConnect(LPCTSTR lpszConnect);
```

### <a name="parameters"></a>パラメーター

*lpszConnect*<br/>
ODBC またはインストール可能な ISAM ドライバーに渡す追加パラメーターを指定する文字列式へのポインター。

### <a name="remarks"></a>解説

次の表に示すパスは、データベースファイルが格納されているディレクトリの完全なパスです。前に識別子 "DATABASE =" を付ける必要があります。 場合によっては (Microsoft Jet および Microsoft Excel データベースと同様に)、データベースパス引数に特定のファイル名が含まれます。

> [!NOTE]
> "DATABASE = drive: \ path" という形式の等号 in path ステートメントの前後に空白を入れないでください \\ 。 これにより、例外がスローされ、接続が失敗します。

次の表に、使用可能なデータベースの種類と、対応するデータベースの指定子とパスを示します。

|データベースの種類|指定子|パス|
|-------------------|---------------|----------|
|Jet データベースエンジンを使用するデータベース|"[ `database`];"|" `drive` : \\ \  *パス* \\ \  の *ファイル名*。MDB|
|dBASE III|"dBASE III;"|" `drive` : \\ \  *path*"|
|dBASE IV|"dBASE IV;"|" `drive` : \\ \  *path*"|
|dBASE 5|"dBASE 5.0;"|" `drive` : \\ \  *path*"|
|Paradox 3.x|"Paradox 3. x;"|" `drive` : \\ \  *path*"|
|Paradox 4.x|"Paradox 4.x;"|" `drive` : \\ \  *path*"|
|Paradox 5.x|"Paradox 5.x;"|" `drive` : \\ \  *path*"|
|Excel 3.0|"Excel 3.0;"|" `drive` : \\ \  *パス* \\ \  の *ファイル名*。XLS|
|Excel 4.0|"Excel 4.0;"|" `drive` : \\ \  *パス* \\ \  の *ファイル名*。XLS|
|Excel 5.0 または Excel 95|"Excel 5.0;"|" `drive` : \\ \  *パス* \\ \  の *ファイル名*。XLS|
|Excel 97|"Excel 8.0;"|" `drive` : \\ \  *パス* \  の *ファイル名*。XLS|
|HTML のインポート|"HTML インポート;"|" `drive` : \\ \  *path* \  *filename*"|
|HTML エクスポート|"HTML エクスポート;"|" `drive` : \\ \  *path*"|
|Text|"Text;"|"ドライブ: \\ \ パス"|
|ODBC|ドライバーデータベース = `database` ;UID = *user*;PWD = *password*;DSN = *datasourcename;* LOGINTIMEOUT = *seconds;*"(これは、すべてのサーバーに対する完全な接続文字列ではない可能性があります。これは一例にすぎません。 パラメーター間にスペースを入れないことが非常に重要です)。|なし|
|Exchange|エクスチェンジ<br /><br /> MAPILEVEL = *folderpath*;<br /><br /> [TABLETYPE = {0 &#124; 1};]<br /><br /> [PROFILE = *profile*;]<br /><br /> [PWD = *パスワード*;]<br /><br /> [データベース = `database` ;] "|*"ドライブ*: \\ \  *パス* \\ \  の *ファイル名*。MDB|

> [!NOTE]
> DAO 3.5 の時点では、Btrieve はサポートされなくなりました。

接続文字列には、2つの円記号 () を使用する必要があり \\ \\ ます。 を使用して既存の接続のプロパティを変更した場合は `SetConnect` 、その後 [refreshlink](#refreshlink)を呼び出す必要があります。 を使用して接続プロパティを初期化する場合は `SetConnect` 、を呼び出す必要はありませんが、最初にテーブルテーブルを追加することを選択する必要があり `RefreshLink` ます。

パスワードが必要ですが指定されていない場合、ODBC ドライバーでは、最初にテーブルにアクセスしたときにログインダイアログボックスが表示され、接続が閉じられてから再び開かれた場合には再び表示されます。

`CDaoTableDef`メンバー関数に source 引数を指定することにより、オブジェクトの接続文字列を設定でき `Create` ます。 設定を確認して、データベースの種類、パス、ユーザー ID、パスワード、または ODBC データソースを確認できます。 詳細については、特定のドライバーのドキュメントを参照してください。

関連情報については、DAO ヘルプのトピック「Connect プロパティ」を参照してください。

## <a name="cdaotabledefsetname"></a><a name="setname"></a> CDaoTableDef:: SetName

テーブルのユーザー定義名を設定するには、このメンバー関数を呼び出します。

```cpp
void SetName(LPCTSTR lpszName);
```

### <a name="parameters"></a>パラメーター

*lpszName*<br/>
テーブルの名前を指定する文字列式へのポインター。

### <a name="remarks"></a>解説

名前は文字で始める必要があり、最大64文字まで含めることができます。 数字とアンダースコア文字を含めることはできますが、句読点やスペースは使用できません。

関連情報については、DAO ヘルプの「Name プロパティ」を参照してください。

## <a name="cdaotabledefsetsourcetablename"></a><a name="setsourcetablename"></a> CDaoTableDef:: SetSourceTableName

このメンバー関数を呼び出して、アタッチされたテーブルの名前、またはオブジェクトの基になるベーステーブルの名前を指定します。これは、 `CDaoTableDef` データの元のソースに存在するためです。

```cpp
void SetSourceTableName(LPCTSTR lpszSrcTableName);
```

### <a name="parameters"></a>パラメーター

*lpszSrcTableName*<br/>
外部データベース内のテーブル名を指定する文字列式へのポインター。 ベーステーブルの場合、設定は空の文字列 ("") になります。

### <a name="remarks"></a>解説

その後、 [Refreshlink](#refreshlink)を呼び出す必要があります。 このプロパティ設定は、ベーステーブルに対しては空で、アタッチされたテーブルまたはコレクションに追加されていないオブジェクトに対しては読み取り/書き込みが行われます。

関連情報については、DAO ヘルプの「SourceTableName プロパティ」を参照してください。

## <a name="cdaotabledefsetvalidationrule"></a><a name="setvalidationrule"></a> CDaoTableDef:: SetValidationRule

このメンバー関数を呼び出して、テーブル定義の検証規則を設定します。

```cpp
void SetValidationRule(LPCTSTR lpszValidationRule);
```

### <a name="parameters"></a>パラメーター

*lpszValidationRule*<br/>
操作を検証する文字列式へのポインター。

### <a name="remarks"></a>解説

検証規則は、更新操作との接続に使用されます。 テーブルテーブルに検証規則が含まれている場合、そのテーブルテーブルの更新は、データが変更される前に、事前に定義された条件と一致する必要があります。 変更が条件に一致しない場合は、 [Getvalidationtext](#getvalidationtext) のテキストを含む例外が表示されます。

検証は、Microsoft Jet データベースエンジンを使用するデータベースに対してのみサポートされます。 式では、ユーザー定義関数、ドメイン集計関数、SQL 集計関数、またはクエリを参照できません。 オブジェクトの検証規則は、 `CDaoTableDef` そのオブジェクト内の複数のフィールドを参照できます。

たとえば、 *hire_date* および *termination_date* という名前のフィールドの場合、検証規則は次のようになります。

[!code-cpp[NVC_MFCDatabase#34](../../mfc/codesnippet/cpp/cdaotabledef-class_1.cpp)]

関連情報については、DAO ヘルプのトピック「ValidationRule プロパティ」を参照してください。

## <a name="cdaotabledefsetvalidationtext"></a><a name="setvalidationtext"></a> CDaoTableDef:: SetValidationText

`CDaoTableDef`Microsoft Jet データベースエンジンでサポートされている基になるベーステーブルを持つオブジェクトの検証規則の例外テキストを設定するには、このメンバー関数を呼び出します。

```cpp
void SetValidationText(LPCTSTR lpszValidationText);
```

### <a name="parameters"></a>パラメーター

*lpszValidationText*<br/>
入力したデータが無効な場合に表示されるテキストを指定する文字列式へのポインター。

### <a name="remarks"></a>解説

アタッチされたテーブルの検証テキストを設定することはできません。

関連情報については、DAO ヘルプのトピック「ValidationText プロパティ」を参照してください。

## <a name="see-also"></a>関連項目

[CObject クラス](../../mfc/reference/cobject-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CDaoDatabase クラス](../../mfc/reference/cdaodatabase-class.md)<br/>
[CDaoRecordset クラス](../../mfc/reference/cdaorecordset-class.md)
