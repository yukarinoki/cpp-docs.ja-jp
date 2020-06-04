---
title: クラス
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
ms.openlocfilehash: adc31ccbf2be34aa1df1fa56111d1990701a6329
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754691"
---
# <a name="cdaotabledef-class"></a>クラス

ベース テーブル、またはアタッチ テーブルの格納された定義を表現します。

## <a name="syntax"></a>構文

```
class CDaoTableDef : public CObject
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[次の表の定義を表します。](#cdaotabledef)|`CDaoTableDef` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[次の表の定義::追加](#append)|新しいテーブルをデータベースに追加します。|
|[次の表の定義::缶詰](#canupdate)|テーブルを更新できる場合は、0 以外を返します (フィールドの定義またはテーブル プロパティを変更できます)。|
|[テーブル定義::閉じる](#close)|開いているテーブル定義を閉じます。|
|[次の表の定義::作成](#create)|[Append](#append)を使用してデータベースに追加できるテーブルを作成します。|
|[次のフィールドを作成します。](#createfield)|テーブルのフィールドを作成するために呼び出されます。|
|[次の表に従います。](#createindex)|テーブルのインデックスを作成するために呼び出されます。|
|[:Dエレテフィールド](#deletefield)|テーブルからフィールドを削除するために呼び出されます。|
|[:Dエテーゼインデックス](#deleteindex)|テーブルからインデックスを削除するために呼び出されます。|
|[次の表の定義を取得します。](#getattributes)|オブジェクトの 1 つ以上の特性を示`CDaoTableDef`す値を返します。|
|[コダリンクフ::ゲットコネクト](#getconnect)|テーブルのソースに関する情報を提供する値を返します。|
|[次の表の定義::作成された取得](#getdatecreated)|オブジェクトの基になるベース テーブルが作成された`CDaoTableDef`日時を返します。|
|[を更新します。](#getdatelastupdated)|ベース テーブルのデザインに対して行われた最新の変更の日時を返します。|
|[次の項目を取得します。](#getfieldcount)|テーブル内のフィールドの数を表す値を返します。|
|[次の項目を取得します。](#getfieldinfo)|テーブル内のフィールドに関する特定の種類の情報を返します。|
|[次の表に値します。](#getindexcount)|テーブルのインデックスの数を返します。|
|[次の表に従って定義します。](#getindexinfo)|テーブルのインデックスに関する特定の種類の情報を返します。|
|[次の表の定義::名前を取得します。](#getname)|テーブルのユーザー定義名を返します。|
|[次の表数を取得します。](#getrecordcount)|テーブル内のレコード数を返します。|
|[テーブル名を取得します。](#getsourcetablename)|ソース データベース内のアタッチ テーブルの名前を指定する値を返します。|
|[次の値を取得します。](#getvalidationrule)|フィールドが変更またはテーブルに追加されるときに、フィールド内のデータを検証する値を返します。|
|[次の値を取得します。](#getvalidationtext)|Field オブジェクトの値が指定された検証規則を満たさない場合に、アプリケーションが表示するメッセージのテキストを指定する値を返します。|
|[テーブル定義::IsOpen](#isopen)|テーブルが開いている場合は、0 以外を返します。|
|[テーブル定義::オープン](#open)|データベースの TableDef コレクションに格納されている既存のテーブル定義を開きます。|
|[次の表の定義::リフレッシュリンク](#refreshlink)|アタッチ テーブルの接続情報を更新します。|
|[次の表の定義::属性の設定](#setattributes)|オブジェクトの 1 つ以上の特性を示`CDaoTableDef`す値を設定します。|
|[コダリンクフ::セットコネクト](#setconnect)|テーブルのソースに関する情報を提供する値を設定します。|
|[を設定します。](#setname)|テーブルの名前を設定します。|
|[テーブル名を設定します。](#setsourcetablename)|ソース データベース内のアタッチ テーブルの名前を指定する値を設定します。|
|[次の値を指定します。](#setvalidationrule)|フィールドのデータが変更またはテーブルに追加される場合に、そのデータを検証する値を設定します。|
|[をクリックします。](#setvalidationtext)|Field オブジェクトの値が指定された検証規則を満たさない場合に、アプリケーションが表示するメッセージのテキストを指定する値を設定します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[テーブル定義::m_pDAOTableDef](#m_pdaotabledef)|テーブル定義オブジェクトの基になる DAO インターフェイスへのポインター。|
|[カオブアテーブルデフ::m_pDatabase](#m_pdatabase)|このテーブルのソース データベース。|

## <a name="remarks"></a>解説

各 DAO データベース オブジェクトは、保存されているすべての DAO テーブル定義オブジェクトを含む TableDefs というコレクションを保持します。

オブジェクトを使用してテーブル定義を`CDaoTableDef`操作します。 たとえば、次のように操作できます。

- データベース内のローカル テーブル、アタッチ テーブル、または外部テーブルのフィールドとインデックス構造を調べます。

- アタッチ`SetConnect`テーブル`SetSourceTableName`の メンバー関数と メンバー関数を`RefreshLink`呼び出し、メンバー関数を使用して、接続テーブルへの接続を更新します。

- テーブル内`CanUpdate`のフィールド定義を編集できるかどうかを調べるには、メンバー関数を呼び出します。

- `GetValidationRule`および および メンバー関数 および`SetValidationRule`を使用して、検証条件を`GetValidationText``SetValidationText`取得または設定します。

- このメンバー`Open`関数を使用して、テーブル、ダイナセット、またはスナップショットの種類のオブジェクト`CDaoRecordset`を作成します。

    > [!NOTE]
    >  DAO データベース クラスは、オープン データベース接続 (ODBC) に基づく MFC データベース クラスとは異なります。 DAO データベースクラス名には、すべて "CDao" というプレフィックスが付いています。 DAO クラスを使用して ODBC データ ソースにアクセスすることはできます。DAO クラスは、通常、Jet データベース エンジンに固有の優れた機能を提供します。

### <a name="to-use-tabledef-objects-either-to-work-with-an-existing-table-or-to-create-a-new-table"></a>テーブル定義オブジェクトを使用して既存のテーブルを操作するか、新しいテーブルを作成するには

1. すべての場合において、まず、テーブル`CDaoTableDef`が属する[CDaoDatabase](../../mfc/reference/cdaodatabase-class.md)オブジェクトへのポインタを指定して、オブジェクトを構築します。

1. 次に、必要に応じて次の操作を行います。

   - 既存の保存済みテーブルを使用するには、テーブル定義オブジェクトの[Open](#open)メンバー関数を呼び出して、保存されたテーブルの名前を指定します。

   - 新しいテーブルを作成するには、テーブルの名前を指定して、tabledef オブジェクトの[Create](#create)メンバー関数を呼び出します。 フィールドとインデックスをテーブルに追加するには[、CreateField](#createfield)と[CreateIndex](#createindex)を呼び出します。

   - データベースの TableDefs コレクションにテーブルを追加してテーブルを保存する呼び出し[Append](#append)します。 `Create`テーブル定義をオープン状態にするため、呼び出した`Create`後は 呼`Open`び出しません。

        > [!TIP]
        >  保存したテーブルを作成する最も簡単な方法は、Access を使用してテーブルを作成してデータベースに格納することです。 次に、MFC コードで開いて使用できます。

開いたテーブル定義オブジェクトを使用するには、オブジェクトを`CDaoRecordset`作成して開き`dbOpenTable`*、nOpenType*パラメータに値を指定します。

tabledef オブジェクトを使用して`CDaoRecordset`オブジェクトを作成するには、通常、上記の説明に従ってテーブル定義を作成または開き[、CDaoRecordset::Open](../../mfc/reference/cdaorecordset-class.md#open)を呼び出すときにテーブル定義オブジェクトへのポインタを渡してレコードセット オブジェクトを作成します。 渡すテーブル定義は、オープン状態である必要があります。 詳細については、「クラス[CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)」を参照してください。

テーブル定義オブジェクトの使用が終了したら[、Close](../../mfc/reference/cdaorecordset-class.md#close)メンバー関数を呼び出します。その後、テーブル定義オブジェクトを破棄します。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

`CDaoTableDef`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxdao.h

## <a name="cdaotabledefappend"></a><a name="append"></a>次の表の定義::追加

[Create](#create)を呼び出して新しいテーブル定義オブジェクトを作成し、テーブル定義をデータベースに保存した後に、このメンバー関数を呼び出します。

```
virtual void Append();
```

### <a name="remarks"></a>解説

この関数は、オブジェクトをデータベースの TableDefs コレクションに追加します。 テーブル定義を追加しないことで定義するときに、一時オブジェクトとして使用できますが、保存して使用する場合は、 を呼び出す`Append`必要があります。

> [!NOTE]
> 名前のないテーブル定義 (null または空の文字列を含む) を追加しようとすると、MFC は例外をスローします。

関連情報については、DAO ヘルプの「メソッドの追加」を参照してください。

## <a name="cdaotabledefcanupdate"></a><a name="canupdate"></a>次の表の定義::缶詰

`CDaoTableDef`オブジェクトの基になるテーブルの定義を変更できるかどうかを調べます。

```
BOOL CanUpdate();
```

### <a name="return-value"></a>戻り値

テーブル構造 (スキーマ) を変更できる場合は 0 以外の値を指定します (フィールドとインデックスの追加または削除、または 0 の場合)。

### <a name="remarks"></a>解説

デフォルトでは、オブジェクトの基になる新しく`CDaoTableDef`作成されたテーブルを更新でき、オブジェクトの基になる`CDaoTableDef`アタッチテーブルは更新できません。 結果`CDaoTableDef`のレコードセットが更新可能でない場合でも、オブジェクトは更新可能です。

関連情報については、DAO ヘルプの「更新可能なプロパティ」を参照してください。

## <a name="cdaotabledefcdaotabledef"></a><a name="cdaotabledef"></a>次の表の定義を表します。

`CDaoTableDef` オブジェクトを構築します。

```
CDaoTableDef(CDaoDatabase* pDatabase);
```

### <a name="parameters"></a>パラメーター

*データベース*<br/>
[オブジェクトへの](../../mfc/reference/cdaodatabase-class.md)ポインター。

### <a name="remarks"></a>解説

オブジェクトを作成した後[、Create](#create)または[Open](#open)メンバー関数を呼び出す必要があります。 オブジェクトの使用を終了したら[、Close](#close)メンバー関数を呼び出してオブジェクト`CDaoTableDef`を破棄する必要があります。

## <a name="cdaotabledefclose"></a><a name="close"></a>テーブル定義::閉じる

このメンバー関数を呼び出して、テーブル定義オブジェクトを閉じて解放します。

```
virtual void Close();
```

### <a name="remarks"></a>解説

通常、`Close`を呼び出した後に、tabledef オブジェクトが**new**で割り当てられた場合は削除します。

呼び出し後に、`Close`もう一度[Open](#open)を呼び出すことができます。 これにより、テーブル定義オブジェクトを再利用できます。

関連情報については、DAO ヘルプの「メソッドを閉じる」を参照してください。

## <a name="cdaotabledefcreate"></a><a name="create"></a>次の表の定義::作成

このメンバー関数を呼び出して、新しい保存済みテーブルを作成します。

```
virtual void Create(
    LPCTSTR lpszName,
    long lAttributes = 0,
    LPCTSTR lpszSrcTable = NULL,
    LPCTSTR lpszConnect = NULL);
```

### <a name="parameters"></a>パラメーター

*名前を指定します。*<br/>
テーブルの名前を含む文字列へのポインター。

*l属性*<br/>
tabledef オブジェクトによって表されるテーブルの特性に対応する値。 ビット単位 OR を使用して、次の定数のいずれかを組み合わせることができます。

|定数|説明|
|--------------|-----------------|
|`dbAttachExclusive`|Microsoft Jet データベース エンジンを使用するデータベースの場合、テーブルが専用に開かれたアタッチ テーブルであることを示します。|
|`dbAttachSavePWD`|Microsoft Jet データベース エンジンを使用するデータベースの場合、接続テーブルのユーザー ID とパスワードが接続情報と共に保存されることを示します。|
|`dbSystemObject`|テーブルが Jet データベース エンジンによって提供されるシステム テーブルであることを示します。|
|`dbHiddenObject`|テーブルが、Jet データベース エンジンによって提供される非表示のテーブルであることを示します。|

*テーブル*<br/>
ソース テーブル名を含む文字列へのポインター。 デフォルトでは、この値は NULL として初期化されます。

*lpszConnect*<br/>
既定の接続文字列を含む文字列へのポインター。 デフォルトでは、この値は NULL として初期化されます。

### <a name="remarks"></a>解説

テーブル定義に名前を付けたら、[追加](#append)を呼び出して、データベースの TableDefs コレクションにテーブル定義を保存できます。 を呼`Append`び出した後、テーブル定義は開いた状態になり、それを使用して[CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)オブジェクトを作成できます。

関連情報については、DAO ヘルプのトピック「テーブル定義メソッドの作成」を参照してください。

## <a name="cdaotabledefcreatefield"></a><a name="createfield"></a>次のフィールドを作成します。

テーブルにフィールドを追加するには、このメンバー関数を呼び出します。

```cpp
void CreateField(
    LPCTSTR lpszName,
    short nType,
    long lSize,
    long lAttributes = 0);

void CreateField(CDaoFieldInfo& fieldinfo);
```

### <a name="parameters"></a>パラメーター

*名前を指定します。*<br/>
このフィールドの名前を指定する文字列式へのポインター。

*nType*<br/>
フィールドのデータ型を示す値。 設定は、次のいずれかの値になります。

|Type|サイズ (バイト)|説明|
|----------|--------------------|-----------------|
|`dbBoolean`|1 バイト|BOOL|
|`dbByte`|BYTE|
|`dbInteger`|2|INT|
|`dbLong`|4|long|
|`dbCurrency`|8|通貨 ([コレ通貨](../../mfc/reference/colecurrency-class.md))|
|`dbSingle`|4|float|
|`dbDouble`|8|double|
|`dbDate`|8|日付/時刻 ( [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md))|
|`dbText`|1 - 255|テキスト ( [C文字列](../../atl-mfc-shared/reference/cstringt-class.md))|
|`dbLongBinary`|0|ロング バイナリ (OLE オブジェクト[)、CLong バイナリ](../../mfc/reference/clongbinary-class.md)または[C バイト配列](../../mfc/reference/cbytearray-class.md)|
|`dbMemo`|0|メモ ( [CString](../../atl-mfc-shared/reference/cstringt-class.md))|

*lサイズ*<br/>
テキストを含むフィールドの最大サイズ (バイト単位) またはテキストまたは数値を含むフィールドの固定サイズを示す値。 *lSize*パラメーターは、テキスト フィールド以外のすべてのフィールドでは無視されます。

*l属性*<br/>
フィールドの特性に対応する値で、ビット単位の OR を使用して組み合わせることができます。

|定数|説明|
|--------------|-----------------|
|`dbFixedField`|フィールドサイズは固定です (数値フィールドの場合はデフォルト)。|
|`dbVariableField`|フィールドサイズは可変です (テキストフィールドのみ)。|
|`dbAutoIncrField`|新しいレコードのフィールド値は、変更できない一意の長整数に自動的にインクリメントされます。 Jet データベース テーブルでのみサポートされます。|
|`dbUpdatableField`|フィールド値は変更できます。|
|`dbDescending`|フィールドは降順 (Z - A または 100 - 0) の順序で並べ替えられます (Index オブジェクトの Fields コレクションの Field オブジェクトにのみ適用されます)。 この定数を省略すると、フィールドは昇順 (A - Z または 0 - 100) で並べ替えられます (デフォルト)。|

*Fieldinfo*<br/>
[構造体への](../../mfc/reference/cdaofieldinfo-structure.md)参照。

### <a name="remarks"></a>解説

`DAOField` (OLE) オブジェクトが作成され、(OLE) オブジェクトの`DAOTableDef`Fields コレクションに追加されます。 オブジェクトプロパティの検査に使用する以外`CDaoFieldInfo`に、tabledef で新しいフィールドを作成するための入力パラメータを作成することもできます。 の最初の`CreateField`バージョンは使いやすいですが、より細かいコントロールが必要な場合は、`CreateField``CDaoFieldInfo`パラメータを受け取る 2 番目のバージョンの を使用できます。

のバージョンを使用`CreateField`する場合は、パラメーター`CDaoFieldInfo`を受け取る構造体の次のメンバーのそれぞれを`CDaoFieldInfo`慎重に設定する必要があります。

- `m_strName`

- `m_nType`

- `m_lSize`

- `m_lAttributes`

- `m_bAllowZeroLength`

残りのメンバーは`CDaoFieldInfo`**、0、FALSE、** または空の文字列に設定する必要`CDaoException`があります。

関連情報については、DAO ヘルプの「フィールド メソッドの作成」を参照してください。

## <a name="cdaotabledefcreateindex"></a><a name="createindex"></a>次の表に従います。

テーブルにインデックスを追加します。

```cpp
void CreateIndex(CDaoIndexInfo& indexinfo);
```

### <a name="parameters"></a>パラメーター

*インデックス情報*<br/>
[構造体への](../../mfc/reference/cdaoindexinfo-structure.md)参照。

### <a name="remarks"></a>解説

インデックスは、データベース テーブルからアクセスされるレコードの順序と、重複レコードを受け入れるかどうかを指定します。 インデックスを使用すると、データへの効率的なアクセスも可能になります。

テーブルのインデックスを作成する必要はありませんが、インデックスのない大きなテーブルでは、特定のレコードへのアクセスやレコードセットの作成に時間がかかる場合があります。 一方、インデックスを作成すると、すべてのインデックスが自動的に更新されるため、更新、追加、および削除の操作が遅くなります。 作成するインデックスを決定する際には、これらの要因を考慮してください。

構造体の次のメンバー`CDaoIndexInfo`を設定する必要があります。

- `m_strName`名前を指定する必要があります。

- `m_pFieldInfos`構造体の`CDaoIndexFieldInfo`配列を指す必要があります。

- `m_nFields``CDaoFieldInfo`構造体の配列内のフィールドの数を指定する必要があります。

FALSE に設定されている場合、残りのメンバーは無視されます。 また、インデックスの`m_lDistinctCount`作成時にメンバーは無視されます。

## <a name="cdaotabledefdeletefield"></a><a name="deletefield"></a>:Dエレテフィールド

フィールドを削除してアクセスできないようにするには、このメンバー関数を呼び出します。

```cpp
void DeleteField(LPCTSTR lpszName);
void DeleteField(int nIndex);
```

### <a name="parameters"></a>パラメーター

*名前を指定します。*<br/>
既存のフィールドの名前を表す文字列式へのポインター。

*nIndex*<br/>
インデックスによる検索用の、テーブルの 0 から始まる Fields コレクション内のフィールドのインデックス。

### <a name="remarks"></a>解説

このメンバー関数は、データベースに追加されていない新しいオブジェクト、または[CanUpdate](#canupdate)が 0 以外を返す場合に使用できます。

関連情報については、DAO ヘルプの「メソッドの削除」を参照してください。

## <a name="cdaotabledefdeleteindex"></a><a name="deleteindex"></a>:Dエテーゼインデックス

基になるテーブルのインデックスを削除します。

```cpp
void DeleteIndex(LPCTSTR lpszName);
void DeleteIndex(int nIndex);
```

### <a name="parameters"></a>パラメーター

*名前を指定します。*<br/>
既存のインデックスの名前である文字列式へのポインター。

*nIndex*<br/>
インデックスによる検索用の、データベースの 0 から始まる TableDefs コレクション内のインデックス オブジェクトの配列インデックス。

### <a name="remarks"></a>解説

このメンバー関数は、データベースに追加されていない新しいオブジェクト、または[CanUpdate](#canupdate)が 0 以外を返す場合に使用できます。

関連情報については、DAO ヘルプの「メソッドの削除」を参照してください。

## <a name="cdaotabledefgetattributes"></a><a name="getattributes"></a>次の表の定義を取得します。

オブジェクトの`CDaoTableDef`場合、戻り値はオブジェクトによって表されるテーブルの特性`CDaoTableDef`を指定し、これらの定数の合計を指定できます。

```
long GetAttributes();
```

### <a name="return-value"></a>戻り値

オブジェクトの 1 つ以上の特性を示`CDaoTableDef`す値を返します。

### <a name="remarks"></a>解説

|定数|説明|
|--------------|-----------------|
|`dbAttachExclusive`|Microsoft Jet データベース エンジンを使用するデータベースの場合、テーブルが専用に開かれたアタッチ テーブルであることを示します。|
|`dbAttachSavePWD`|Microsoft Jet データベース エンジンを使用するデータベースの場合、接続テーブルのユーザー ID とパスワードが接続情報と共に保存されることを示します。|
|`dbSystemObject`|テーブルが Jet データベース エンジンによって提供されるシステム テーブルであることを示します。|
|`dbHiddenObject`|テーブルが、Jet データベース エンジンによって提供される非表示のテーブルであることを示します。|
|`dbAttachedTable`|テーブルが、Paradox データベースなどの ODBC 以外のデータベースから接続されたテーブルであることを示します。|
|`dbAttachedODBC`|テーブルが ODBC データベース (SQL Server など) から接続されたテーブルであることを示します。|

システム テーブルは、Microsoft Jet データベース エンジンによって作成されたテーブルで、さまざまな内部情報を格納します。

非表示テーブルは、Jet データベース エンジンによって一時的に使用するために作成されたテーブルです。

関連情報については、DAO ヘルプの「属性プロパティ」を参照してください。

## <a name="cdaotabledefgetconnect"></a><a name="getconnect"></a>コダリンクフ::ゲットコネクト

データ ソースの接続文字列を取得します。

```
CString GetConnect();
```

### <a name="return-value"></a>戻り値

テーブル`CString`のパスとデータベースの種類を含むオブジェクト。

### <a name="remarks"></a>解説

アタッチされた`CDaoTableDef`テーブルを表すオブジェクトの`CString`場合、オブジェクトは 1 つまたは 2 つの部分 (データベース型指定子とデータベースへのパス) で構成されます。

以下の表に示すパスは、データベースファイルを含むディレクトリの絶対パスであり、識別子"DATABASE="の前に置く必要があります。 場合によっては 、(Microsoft Jet データベースや Excel データベースと同様に)、特定のファイル名がデータベース パス引数に含まれます。

[CDaoTableDef::SetConnect](#setconnect)のテーブルには、考えられるデータベースの種類と、対応するデータベース指定子とパスが示されています。

Jet データベースベース テーブルの場合、指定子は空の文字列 ("") です。

パスワードが必要でなくても指定されていない場合、ODBC ドライバは、テーブルに最初にアクセスした場合にログイン ダイアログ ボックスを表示し、接続が閉じて再度開かれた場合に再度表示されます。 アタッチされたテーブルに属性がある`dbAttachSavePWD`場合、テーブルを再度開いたときにログイン プロンプトは表示されません。

関連情報については、DAO ヘルプの「プロパティの接続」を参照してください。

## <a name="cdaotabledefgetdatecreated"></a><a name="getdatecreated"></a>次の表の定義::作成された取得

オブジェクトの基になるテーブルが作成された日時を`CDaoTableDef`調べます。

```
COleDateTime GetDateCreated();
```

### <a name="return-value"></a>戻り値

オブジェクトの基になるテーブルの作成日時を`CDaoTableDef`含む値。

### <a name="remarks"></a>解説

日付と時刻の設定は、ベース テーブルが作成されたコンピュータまたは最後に更新されたコンピュータから取得されます。 マルチユーザー環境では、ユーザーは、これらの設定をファイル サーバーから直接取得して、不一致を回避する必要があります。つまり、すべてのクライアントは、おそらく 1 つのサーバーから、"標準" のタイム ソースを使用する必要があります。

関連情報については、DAO ヘルプの「日付作成、最後に更新されたプロパティ」を参照してください。

## <a name="cdaotabledefgetdatelastupdated"></a><a name="getdatelastupdated"></a>を更新します。

オブジェクトの基になるテーブルが最後に更新された日時を`CDaoTableDef`調べます。

```
COleDateTime GetDateLastUpdated();
```

### <a name="return-value"></a>戻り値

オブジェクトの基になるテーブルが最後に更新された日時を`CDaoTableDef`含む値。

### <a name="remarks"></a>解説

日付と時刻の設定は、ベース テーブルが作成されたコンピュータまたは最後に更新されたコンピュータから取得されます。 マルチユーザー環境では、ユーザーは、これらの設定をファイル サーバーから直接取得して、不一致を回避する必要があります。つまり、すべてのクライアントは、おそらく 1 つのサーバーから、"標準" のタイム ソースを使用する必要があります。

関連情報については、DAO ヘルプの「日付作成、最後に更新されたプロパティ」を参照してください。

## <a name="cdaotabledefgetfieldcount"></a><a name="getfieldcount"></a>次の項目を取得します。

テーブルに定義されているフィールドの数を取得します。

```
short GetFieldCount();
```

### <a name="return-value"></a>戻り値

テーブル内のフィールドの数。

### <a name="remarks"></a>解説

値が 0 の場合、コレクション内にオブジェクトはありません。

関連情報については、DAO ヘルプの「プロパティのカウント」を参照してください。

## <a name="cdaotabledefgetfieldinfo"></a><a name="getfieldinfo"></a>次の項目を取得します。

tabledef で定義されたフィールドに関するさまざまな種類の情報を取得します。

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
インデックスによる検索用の、テーブルの 0 から始まる Fields コレクション内のフィールド オブジェクトのインデックス。

*Fieldinfo*<br/>
[構造体への](../../mfc/reference/cdaofieldinfo-structure.md)参照。

*オプション*<br/>
取得するフィールドに関する情報を指定するオプション。 使用可能なオプションは、関数が返す原因と共に次の一覧に示します。

- `AFX_DAO_PRIMARY_INFO`(デフォルト)名前、種類、サイズ、属性。 このオプションを使用すると、パフォーマンスを最も速くできます。

- `AFX_DAO_SECONDARY_INFO`主な情報、プラス: 順序位置、必須、長さゼロ、照合順序、外部名、ソース フィールド、ソース テーブル

- `AFX_DAO_ALL_INFO`プライマリおよびセカンダリの情報に加えて、検証ルール、検証テキスト、デフォルト値

*名前を指定します。*<br/>
名前による検索用のフィールド オブジェクトの名前へのポインター。 名前は、フィールドに一意の名前を付ける最大 64 文字の文字列です。

### <a name="remarks"></a>解説

関数の 1 つのバージョンでは、インデックスでフィールドを検索できます。 もう 1 つのバージョンでは、フィールドを名前で検索できます。

返される情報の説明については[、CDaoFieldInfo](../../mfc/reference/cdaofieldinfo-structure.md)構造体を参照してください。 この構造体には *、dwInfoOptions*の説明に記載されている情報の項目に対応するメンバがあります。 あるレベルで情報を要求すると、以前のレベルの情報も取得できます。

関連情報については、DAO ヘルプの「属性プロパティ」を参照してください。

## <a name="cdaotabledefgetindexcount"></a><a name="getindexcount"></a>次の表に値します。

テーブルのインデックスの数を取得します。

```
short GetIndexCount();
```

### <a name="return-value"></a>戻り値

テーブルのインデックスの数。

### <a name="remarks"></a>解説

値が 0 の場合、コレクション内にインデックスはありません。

関連情報については、DAO ヘルプの「プロパティのカウント」を参照してください。

## <a name="cdaotabledefgetindexinfo"></a><a name="getindexinfo"></a>次の表に従って定義します。

tabledef で定義されているインデックスに関するさまざまな種類の情報を取得します。

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
コレクション内での位置を基準に検索する、テーブルの 0 から始まる Indexes コレクション内の Index オブジェクトの数値インデックス。

*インデックス情報*<br/>
[構造体への](../../mfc/reference/cdaoindexinfo-structure.md)参照。

*オプション*<br/>
取得するインデックスに関する情報を指定するオプション。 使用可能なオプションは、関数が返す原因と共に次の一覧に示します。

- `AFX_DAO_PRIMARY_INFO`名前、フィールド情報、フィールド。 このオプションを使用すると、パフォーマンスを最も速くできます。

- `AFX_DAO_SECONDARY_INFO`プライマリ情報、および:プライマリ、一意、クラスタ化、無視ヌル、必須、外部

- `AFX_DAO_ALL_INFO`プライマリ情報とセカンダリ情報、および:個別のカウント

*名前を指定します。*<br/>
名前による検索用のインデックス オブジェクトの名前へのポインター。

### <a name="remarks"></a>解説

関数の 1 つのバージョンでは、コレクション内の位置でインデックスを検索できます。 もう 1 つのバージョンでは、インデックスを名前で検索できます。

返される情報の説明については[、CDaoIndexInfo](../../mfc/reference/cdaoindexinfo-structure.md)構造体を参照してください。 この構造体には *、dwInfoOptions*の説明に記載されている情報の項目に対応するメンバがあります。 あるレベルで情報を要求すると、以前のレベルの情報も取得できます。

関連情報については、DAO ヘルプの「属性プロパティ」を参照してください。

## <a name="cdaotabledefgetname"></a><a name="getname"></a>次の表の定義::名前を取得します。

基になるテーブルのユーザー定義名を取得します。

```
CString GetName();
```

### <a name="return-value"></a>戻り値

テーブルのユーザー定義名。

### <a name="remarks"></a>解説

この名前は文字で始まり、最大 64 文字まで使用できます。 数字やアンダースコアの文字を含めることができますが、句読点やスペースを含めることはできません。

関連情報については、DAO ヘルプの「プロパティ名」を参照してください。

## <a name="cdaotabledefgetrecordcount"></a><a name="getrecordcount"></a>次の表数を取得します。

オブジェクト内のレコード数を調べるには、このメンバー関数`CDaoTableDef`を呼び出します。

```
long GetRecordCount();
```

### <a name="return-value"></a>戻り値

テーブル定義オブジェクトでアクセスされたレコードの数。

### <a name="remarks"></a>解説

テーブル`GetRecordCount`型`CDaoTableDef`オブジェクトの呼び出しは、テーブル内のレコードの概数を反映し、テーブルレコードが追加および削除されるとすぐに影響を受けます。 ロールバックされたトランザクションは[、CDaoWorkSpace::コンパクトデータベース](../../mfc/reference/cdaoworkspace-class.md#compactdatabase)を呼び出すまで、レコードカウントの一部として表示されます。 レコード`CDaoTableDef`のないオブジェクトのレコードカウントプロパティの設定は 0 です。 アタッチされたテーブルまたは ODBC データベースを`GetRecordCount`操作する場合は、常に -1 を返します。

関連情報については、DAO ヘルプの「レコード数プロパティ」を参照してください。

## <a name="cdaotabledefgetsourcetablename"></a><a name="getsourcetablename"></a>テーブル名を取得します。

ソース データベース内のアタッチ テーブルの名前を取得します。

```
CString GetSourceTableName();
```

### <a name="return-value"></a>戻り値

アタッチ`CString`されたテーブルのソース名を指定するオブジェクト。またはネイティブ データ テーブルの場合は空の文字列。

### <a name="remarks"></a>解説

アタッチテーブルとは、Jet データベースにリンクされている別のデータベースのテーブルのことです。 アタッチされたテーブルのデータは外部データベースに残り、他のアプリケーションで操作できます。

関連情報については、DAO ヘルプの「ソーステーブル名プロパティ」を参照してください。

## <a name="cdaotabledefgetvalidationrule"></a><a name="getvalidationrule"></a>次の値を取得します。

テーブル定義の検証規則を取得します。

```
CString GetValidationRule();
```

### <a name="return-value"></a>戻り値

フィールド`CString`内のデータが変更またはテーブルに追加される場合に、そのデータを検証するオブジェクト。

### <a name="remarks"></a>解説

検証規則は、更新操作に関連して使用されます。 テーブル定義に入力規則が含まれている場合、そのテーブル定義の更新は、データが変更される前に事前に定義された条件と一致する必要があります。 変更が条件に一致しない場合は、[値](#getvalidationtext)を含む例外がスローされます。 オブジェクトの`CDaoTableDef`場合、これは`CString`アタッチテーブルでは読み取り専用で、ベース テーブルでは読み取り/書き込み可能です。

関連情報については、DAO ヘルプの「検証ルールプロパティ」を参照してください。

## <a name="cdaotabledefgetvalidationtext"></a><a name="getvalidationtext"></a>次の値を取得します。

ユーザーが入力規則に一致しないデータを入力したときに表示する文字列を取得します。

```
CString GetValidationText();
```

### <a name="return-value"></a>戻り値

ユーザー`CString`が入力規則に一致しないデータを入力した場合に表示されるテキストを指定するオブジェクト。

### <a name="remarks"></a>解説

オブジェクトの`CDaoTableDef`場合、これは`CString`アタッチテーブルでは読み取り専用で、ベース テーブルでは読み取り/書き込み可能です。

関連情報については、DAO ヘルプの「検証テキスト プロパティ」を参照してください。

## <a name="cdaotabledefisopen"></a><a name="isopen"></a>テーブル定義::IsOpen

`CDaoTableDef`オブジェクトが現在開いているかどうかを調べます。

```
BOOL IsOpen() const;
```

### <a name="return-value"></a>戻り値

オブジェクトが開いている`CDaoTableDef`場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

## <a name="cdaotabledefm_pdatabase"></a><a name="m_pdatabase"></a>カオブアテーブルデフ::m_pDatabase

このテーブルの[CDaoDatabase](../../mfc/reference/cdaodatabase-class.md)オブジェクトへのポインターを格納します。

### <a name="remarks"></a>解説

## <a name="cdaotabledefm_pdaotabledef"></a><a name="m_pdaotabledef"></a>テーブル定義::m_pDAOTableDef

オブジェクトの基になる DAO テーブル定義オブジェクトの OLE インターフェイス`CDaoTableDef`へのポインターを格納します。

### <a name="remarks"></a>解説

DAO インターフェイスに直接アクセスする必要がある場合は、このポインターを使用します。

## <a name="cdaotabledefopen"></a><a name="open"></a>テーブル定義::オープン

このメンバー関数を呼び出して、データベースの TableDef コレクションに保存されているテーブル定義を開きます。

```
virtual void Open(LPCTSTR lpszName);
```

### <a name="parameters"></a>パラメーター

*名前を指定します。*<br/>
テーブル名を指定する文字列へのポインター。

### <a name="remarks"></a>解説

## <a name="cdaotabledefrefreshlink"></a><a name="refreshlink"></a>次の表の定義::リフレッシュリンク

アタッチテーブルの接続情報を更新します。

```cpp
void RefreshLink();
```

### <a name="remarks"></a>解説

アタッチテーブルの接続情報を変更するには、対応する`CDaoTableDef`オブジェクトで[SetConnect](#setconnect)を呼び出`RefreshLink`し、そのメンバー関数を使用して情報を更新します。 を呼び`RefreshLink`出しても、添付テーブルのプロパティは変更されません。

変更された接続情報を強制的に有効にするには、このテーブル定義に基づいて開いている[すべての CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)オブジェクトを閉じる必要があります。

関連情報については、DAO ヘルプのトピック「更新リンク方法」を参照してください。

## <a name="cdaotabledefsetattributes"></a><a name="setattributes"></a>次の表の定義::属性の設定

オブジェクトの 1 つ以上の特性を示`CDaoTableDef`す値を設定します。

```cpp
void SetAttributes(long lAttributes);
```

### <a name="parameters"></a>パラメーター

*l属性*<br/>
オブジェクトによって表されるテーブルの`CDaoTableDef`特性は、次の定数の合計になります。

|定数|説明|
|--------------|-----------------|
|`dbAttachExclusive`|Microsoft Jet データベース エンジンを使用するデータベースの場合、テーブルが専用に開かれたアタッチ テーブルであることを示します。|
|`dbAttachSavePWD`|Microsoft Jet データベース エンジンを使用するデータベースの場合、接続テーブルのユーザー ID とパスワードが接続情報と共に保存されることを示します。|
|`dbSystemObject`|テーブルが Jet データベース エンジンによって提供されるシステム テーブルであることを示します。|
|`dbHiddenObject`|テーブルが、Jet データベース エンジンによって提供される非表示のテーブルであることを示します。|

### <a name="remarks"></a>解説

複数の属性を設定する場合は、ビット単位の OR 演算子を使用して、適切な定数を合計して結合できます。 非`dbAttachExclusive`アタッチ テーブルに設定すると例外が生成されます。 次の値を組み合わせると、例外も発生します。

- **&#124;エクスクルーシブを含む**

- **&#124;添付テーブル**

関連情報については、DAO ヘルプの「属性プロパティ」を参照してください。

## <a name="cdaotabledefsetconnect"></a><a name="setconnect"></a>コダリンクフ::セットコネクト

アタッチされた`CDaoTableDef`テーブルを表すオブジェクトの場合、文字列オブジェクトは 1 つまたは 2 つの部分 (データベース型指定子とデータベースへのパス) で構成されます。

```cpp
void SetConnect(LPCTSTR lpszConnect);
```

### <a name="parameters"></a>パラメーター

*lpszConnect*<br/>
ODBC またはインストール可能な ISAM ドライバーに渡す追加パラメーターを指定する文字列式へのポインター。

### <a name="remarks"></a>解説

以下の表に示すパスは、データベースファイルを含むディレクトリの絶対パスであり、識別子"DATABASE="の前に置く必要があります。 場合によっては 、(Microsoft Jet データベースや Excel データベースと同様に)、特定のファイル名がデータベース パス引数に含まれます。

> [!NOTE]
> "DATABASE=ドライブ:\\\path" という形式のパス ステートメントに等号の前後に空白を含めないでください。 これにより、例外がスローされ、接続が失敗します。

次の表に、考えられるデータベースの種類と、対応するデータベース指定子とパスを示します。

|データベースの種類|指定子|Path|
|-------------------|---------------|----------|
|Jet データベース エンジンを使用したデータベース|"[ `database`];"|" `drive`\\\ :*パス*\\\ *ファイル名*。MDB"|
|dBASE III|"dBASE III;"|" `drive`\\\ :*パス*"|
|dBASE IV|"dBASE IV;"|" `drive`\\\ :*パス*"|
|dBASE 5|"dBASE 5.0;"|" `drive`\\\ :*パス*"|
|パラドックス 3.x|「パラドックス3.x;」|" `drive`\\\ :*パス*"|
|パラドックス 4.x|「パラドックス4.x;」|" `drive`\\\ :*パス*"|
|パラドックス 5.x|「パラドックス5.x;」|" `drive`\\\ :*パス*"|
|エクセル 3.0|"Excel 3.0;"|" `drive`\\\ :*パス*\\\ *ファイル名*。XLS"|
|エクセル 4.0|"Excel 4.0;"|" `drive`\\\ :*パス*\\\ *ファイル名*。XLS"|
|Excel 5.0 または Excel 95|「エクセル 5.0;」|" `drive`\\\ :*パス*\\\ *ファイル名*。XLS"|
|エクセル 97|"Excel 8.0;"|" `drive`\\\ :*パス*\ *ファイル名*。XLS"|
|HTML インポート|"HTML インポート;"|" `drive`\\\ :*パス*\ *ファイル名*"|
|HTML エクスポート|"HTML エクスポート;"|" `drive`\\\ :*パス*"|
|Text|"テキスト;"|"ドライブ:\\\パス"|
|ODBC|"ODBC;データベース= `database`;UID=*ユーザー*;PWD=*パスワード*;DSN=*データ ソース名。* ログインタイムアウト =*秒;*"(これは、すべてのサーバーの完全な接続文字列ではない可能性があります。 パラメータ間にスペースを入れていないことは非常に重要です。|なし|
|Exchange|「交換;<br /><br /> フォルダ パス 、 フォルダ*パス*、<br /><br /> [テーブルタイプ={ 0 &#124; 1 };<br /><br /> [プロファイル=*プロファイル*;]<br /><br /> [PWD=*パスワード*;]<br /><br /> [データベース= `database`;]」|*"ドライブ*\\\ :*パス*\\\ *ファイル名*。MDB"|

> [!NOTE]
> BTRIEVE は DAO 3.5 以降ではサポートされていません。

接続文字列では、二重円記号\\\\() を使用する必要があります。 を使用して`SetConnect`既存の接続のプロパティを変更した場合は、後で[RefreshLink](#refreshlink)を呼び出す必要があります。 を使用して`SetConnect`接続プロパティを初期化する場合は、 を呼`RefreshLink`び出す必要はありませんが、このオプションを選択する必要があります。

パスワードが必要でなくても指定されていない場合、ODBC ドライバは、テーブルに最初にアクセスした場合にログイン ダイアログ ボックスを表示し、接続が閉じて再度開かれた場合に再度表示されます。

メンバー関数にソース引数を指定することで`CDaoTableDef`、オブジェクトの接続文字列を`Create`設定できます。 データベースのタイプ、パス、ユーザー ID、パスワード、または ODBC データ・ソースを判別するには、この設定を確認します。 詳細については、特定のドライバーのドキュメントを参照してください。

関連情報については、DAO ヘルプの「プロパティの接続」を参照してください。

## <a name="cdaotabledefsetname"></a><a name="setname"></a>を設定します。

テーブルのユーザー定義名を設定します。

```cpp
void SetName(LPCTSTR lpszName);
```

### <a name="parameters"></a>パラメーター

*名前を指定します。*<br/>
テーブルの名前を指定する文字列式へのポインター。

### <a name="remarks"></a>解説

名前は、文字で始まる必要があり、最大 64 文字を含めることができます。 数字やアンダースコアの文字を含めることができますが、句読点やスペースを含めることはできません。

関連情報については、DAO ヘルプの「プロパティ名」を参照してください。

## <a name="cdaotabledefsetsourcetablename"></a><a name="setsourcetablename"></a>テーブル名を設定します。

アタッチされたテーブルの名前、または`CDaoTableDef`オブジェクトの基になるベース テーブルの名前を、データの元のソースに存在するように指定します。

```cpp
void SetSourceTableName(LPCTSTR lpszSrcTableName);
```

### <a name="parameters"></a>パラメーター

*テーブル名*<br/>
外部データベースのテーブル名を指定する文字列式へのポインター。 ベース テーブルの場合、設定は空の文字列 ("") です。

### <a name="remarks"></a>解説

その後[、RefreshLink](#refreshlink)を呼び出す必要があります。 このプロパティの設定は、ベース テーブルの場合は空で、アタッチされたテーブルまたはコレクションに追加されていないオブジェクトの読み取り/書き込みは空です。

関連情報については、DAO ヘルプの「ソーステーブル名プロパティ」を参照してください。

## <a name="cdaotabledefsetvalidationrule"></a><a name="setvalidationrule"></a>次の値を指定します。

テーブル定義の検証規則を設定します。

```cpp
void SetValidationRule(LPCTSTR lpszValidationRule);
```

### <a name="parameters"></a>パラメーター

*チェックルール*<br/>
操作を検証する文字列式へのポインター。

### <a name="remarks"></a>解説

検証規則は、更新操作に関連して使用されます。 テーブル定義に入力規則が含まれている場合、そのテーブル定義の更新は、データが変更される前に事前に定義された条件と一致する必要があります。 変更が条件に一致しない場合は、[テキスト](#getvalidationtext)を含む例外が表示されます。

検証は、Microsoft Jet データベース エンジンを使用するデータベースでのみサポートされます。 式は、ユーザー定義関数、ドメイン集計関数、SQL 集計関数、またはクエリを参照できません。 `CDaoTableDef`オブジェクトの入力規則は、そのオブジェクト内の複数のフィールドを参照できます。

たとえば *、hire_date*と*termination_date*という名前のフィールドの場合、次の入力規則が適用されます。

[!code-cpp[NVC_MFCDatabase#34](../../mfc/codesnippet/cpp/cdaotabledef-class_1.cpp)]

関連情報については、DAO ヘルプの「検証ルールプロパティ」を参照してください。

## <a name="cdaotabledefsetvalidationtext"></a><a name="setvalidationtext"></a>をクリックします。

Microsoft Jet データベース エンジンでサポートされている基になるベース テーブル`CDaoTableDef`を持つオブジェクトの検証規則の例外テキストを設定します。

```cpp
void SetValidationText(LPCTSTR lpszValidationText);
```

### <a name="parameters"></a>パラメーター

*テキスト*<br/>
入力されたデータが無効な場合に表示されるテキストを指定する文字列式へのポインター。

### <a name="remarks"></a>解説

アタッチされたテーブルの検証テキストは設定できません。

関連情報については、DAO ヘルプの「検証テキスト プロパティ」を参照してください。

## <a name="see-also"></a>関連項目

[Cオブジェクトクラス](../../mfc/reference/cobject-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[CDaoDatabase クラス](../../mfc/reference/cdaodatabase-class.md)<br/>
[クラス](../../mfc/reference/cdaorecordset-class.md)
