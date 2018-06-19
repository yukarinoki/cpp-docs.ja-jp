---
title: どちらのクラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ff62b77e6bdec6b796750d27357d12667eb16386
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33378309"
---
# <a name="cdaotabledef-class"></a>どちらのクラス
ベース テーブル、またはアタッチ テーブルの格納された定義を表現します。  
  
## <a name="syntax"></a>構文  
  
```  
class CDaoTableDef : public CObject  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CDaoTableDef::CDaoTableDef](#cdaotabledef)|構築、**どちら**オブジェクト。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CDaoTableDef::Append](#append)|データベースに新しいテーブルを追加します。|  
|[CDaoTableDef::CanUpdate](#canupdate)|テーブルを更新する場合は 0 以外を返します (フィールドやテーブルのプロパティの定義を変更することができます)。|  
|[CDaoTableDef::Close](#close)|開いているテーブル定義を終了します。|  
|[CDaoTableDef::Create](#create)|使用して、データベースに追加できるテーブルを作成[Append](#append)です。|  
|[CDaoTableDef::CreateField](#createfield)|テーブルのフィールドを作成するには、呼び出されます。|  
|[CDaoTableDef::CreateIndex](#createindex)|テーブルのインデックスを作成するには、呼び出されます。|  
|[CDaoTableDef::DeleteField](#deletefield)|テーブルからフィールドを削除するには、呼び出されます。|  
|[CDaoTableDef::DeleteIndex](#deleteindex)|テーブルからインデックスを削除するには、呼び出されます。|  
|[CDaoTableDef::GetAttributes](#getattributes)|1 つまたは複数の特性を示す値を返します、`CDaoTableDef`オブジェクト。|  
|[CDaoTableDef::GetConnect](#getconnect)|テーブルのソースに関する情報を示す値を返します。|  
|[CDaoTableDef::GetDateCreated](#getdatecreated)|基になるベース テーブルの日付と時刻を返します、`CDaoTableDef`オブジェクトが作成されました。|  
|[CDaoTableDef::GetDateLastUpdated](#getdatelastupdated)|ベース テーブルのデザインに加えられた最近の変更日時を返します。|  
|[CDaoTableDef::GetFieldCount](#getfieldcount)|テーブル内のフィールドの数を表す値を返します。|  
|[CDaoTableDef::GetFieldInfo](#getfieldinfo)|テーブルの特定の種類のフィールドに関する情報を返します。|  
|[CDaoTableDef::GetIndexCount](#getindexcount)|テーブルのインデックスの数を返します。|  
|[CDaoTableDef::GetIndexInfo](#getindexinfo)|特定の種類のテーブルのインデックスに関する情報を返します。|  
|[CDaoTableDef::GetName](#getname)|ユーザー定義テーブルの名前を返します。|  
|[CDaoTableDef::GetRecordCount](#getrecordcount)|テーブルのレコードの数を返します。|  
|[CDaoTableDef::GetSourceTableName](#getsourcetablename)|ソース データベースに接続されているテーブルの名前を指定する値を返します。|  
|[CDaoTableDef::GetValidationRule](#getvalidationrule)|変更されたか、テーブルに追加するフィールドのデータを検証する値を返します。|  
|[CDaoTableDef::GetValidationText](#getvalidationtext)|Field オブジェクトの値が指定した検証規則を満たしていない場合に、アプリケーションが表示されるメッセージのテキストを示す値を返します。|  
|[CDaoTableDef::IsOpen](#isopen)|テーブルの場合は 0 以外を返しますが開きます。|  
|[CDaoTableDef::Open](#open)|テーブル定義のコレクションに、データベースに格納されている既存のテーブル定義が表示されます。|  
|[CDaoTableDef::RefreshLink](#refreshlink)|接続されたテーブルの接続情報を更新します。|  
|[CDaoTableDef::SetAttributes](#setattributes)|1 つまたは複数の特性を示す値を設定、`CDaoTableDef`オブジェクト。|  
|[CDaoTableDef::SetConnect](#setconnect)|テーブルのソースに関する情報を提供する値を設定します。|  
|[CDaoTableDef::SetName](#setname)|テーブルの名前を設定します。|  
|[CDaoTableDef::SetSourceTableName](#setsourcetablename)|ソース データベースに接続されているテーブルの名前を指定する値を設定します。|  
|[CDaoTableDef::SetValidationRule](#setvalidationrule)|変更されたか、テーブルに追加するフィールドのデータを検証する値を設定します。|  
|[CDaoTableDef::SetValidationText](#setvalidationtext)|Field オブジェクトの値が指定した検証規則を満たしていない場合に、アプリケーションが表示されるメッセージのテキストを指定する値を設定します。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CDaoTableDef::m_pDAOTableDef](#m_pdaotabledef)|テーブル定義オブジェクトを基になる DAO インターフェイスへのポインター。|  
|[CDaoTableDef::m_pDatabase](#m_pdatabase)|このテーブルのソース データベースです。|  
  
## <a name="remarks"></a>コメント  
 DAO データベースの各オブジェクトは、保存されているすべての DAO tabledef オブジェクトを含むテーブル定義と呼ばれる、コレクションを保持します。  
  
 使用してテーブル定義を操作する、`CDaoTableDef`オブジェクト。 たとえば、次のように操作できます。  
  
-   データベース内の任意のローカル、アタッチ、または外部テーブルのフィールドとインデックス構造を調べます。  
  
-   呼び出す、`SetConnect`と`SetSourceTableName`アタッチ テーブル、および使用するためのメンバー関数、`RefreshLink`メンバー関数への接続を更新するには、テーブルが接続されています。  
  
-   呼び出す、`CanUpdate`かどうかは、テーブル内のフィールド定義を編集することができますを調べます。  
  
-   取得または設定を使用して検証条件、`GetValidationRule`と`SetValidationRule`、および`GetValidationText`と`SetValidationText`メンバー関数。  
  
-   使用して、**開く**、テーブル、ダイナセット、またはスナップショットの種類を作成するメンバー関数`CDaoRecordset`オブジェクト。  
  
    > [!NOTE]
    >  DAO データベース クラスは、MFC データベース クラス ODBC Open Database Connectivity () をベースとは異なります。 DAO データベース クラスの名前では、"CDao"プレフィックスがあります。 DAO クラス; で ODBC データ ソースのアクセスをできます。Microsoft Jet データベース エンジンに固有であるために、DAO クラスは通常、優れた機能を提供します。  
  
### <a name="to-use-tabledef-objects-either-to-work-with-an-existing-table-or-to-create-a-new-table"></a>既存のテーブルを使用するか、新しいテーブルを作成するテーブル定義オブジェクトを使用するには  
  
1.  すべてのケースでは構築最初、`CDaoTableDef`へのポインターを提供するオブジェクト、 [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md)テーブルが所属するオブジェクトします。  
  
2.  目的に応じて、次の操作を行います。  
  
    -   既存のテーブルの名前を使用する呼び出し定義オブジェクトの[開く](#open)保存されているテーブルの名前を指定して、メンバー関数。  
  
    -   新しいテーブルを作成するには、定義オブジェクトを呼び出す[作成](#create)メンバー関数、テーブルの名前を指定します。 呼び出す[CreateField](#createfield)と[CreateIndex](#createindex)フィールドとインデックスをテーブルに追加します。  
  
    -   呼び出す[Append](#append)をデータベースのテーブル定義のコレクションに追加して、テーブルを保存します。 **作成**テーブル定義では、開いている状態を呼び出した後は**作成**呼び出さないでください**開く**です。  
  
        > [!TIP]
        >  保存されているテーブルを作成する最も簡単な方法は、それらを作成し、Microsoft Access を使用して、データベースに保存するのにです。 開き、MFC コードで使用します。  
  
 オブジェクトを使用する、テーブル定義を開くまたは作成した、作成し、開く、`CDaoRecordset`とテーブル定義の名前を指定するオブジェクト、 **dbOpenTable**値で、`nOpenType`パラメーター。  
  
 テーブル定義オブジェクトを使用して作成する、`CDaoRecordset`オブジェクトをする通常の作成または、上記のようにテーブル定義を開き、レコード セット オブジェクトを作成するを呼び出すときに、テーブル定義オブジェクトにポインターを渡す[cdaorecordset::open](../../mfc/reference/cdaorecordset-class.md#open)です。 渡すテーブル定義は、開いている状態にする必要があります。 詳細については、クラスを参照してください。 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)です。  
  
 テーブル定義オブジェクトの使用が終了したらを呼び出す、[閉じる](../../mfc/reference/cdaorecordset-class.md#close)メンバー関数です。 テーブル定義オブジェクトを破棄します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CDaoTableDef`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxdao.h  
  
##  <a name="append"></a>  CDaoTableDef::Append  
 このメンバー関数を呼び出した後[作成](#create)をデータベースにテーブル定義を保存する新しいテーブル定義オブジェクトを作成します。  
  
```  
virtual void Append();
```  
  
### <a name="remarks"></a>コメント  
 関数は、データベースのテーブル定義のコレクションにオブジェクトを追加します。 されませんが、追加することでそれを定義する際に一時オブジェクトとしてテーブル定義を使用することができますが、保存して使用する場合は、呼び出す必要があります**Append**です。  
  
> [!NOTE]
>  (Null または空の文字列を含む)、名前のないテーブルの定義を追加しようとすると、MFC は、例外をスローします。  
  
 関連情報については、「DAO ヘルプの「メソッドの追加」」を参照してください。  
  
##  <a name="canupdate"></a>  CDaoTableDef::CanUpdate  
 決定するには、このメンバー関数を呼び出すかどうか基になるテーブルの定義、`CDaoTableDef`オブジェクトを変更することができます。  
  
```  
BOOL CanUpdate();
```  
  
### <a name="return-value"></a>戻り値  
 テーブルの構造 (スキーマ) を変更する場合は 0 以外 (追加またはフィールドとインデックスを削除)、それ以外の場合に 0 です。  
  
### <a name="remarks"></a>コメント  
 既定では、基になる新しく作成されたテーブル、`CDaoTableDef`オブジェクトを更新することができます、関連付けられているテーブルの基になると、`CDaoTableDef`オブジェクトを更新することはできません。 A`CDaoTableDef`結果のレコード セットは更新可能でない場合でも、オブジェクトが、更新可能な可能性があります。  
  
 関連情報については、DAO ヘルプの「更新可能なプロパティ」を参照してください。  
  
##  <a name="cdaotabledef"></a>  CDaoTableDef::CDaoTableDef  
 構築、**どちら**オブジェクト。  
  
```  
CDaoTableDef(CDaoDatabase* pDatabase);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDatabase`  
 ポインター、 [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md)オブジェクト。  
  
### <a name="remarks"></a>コメント  
 オブジェクトを構築するには、後に呼び出す必要があります、[作成](#create)または[開く](#open)メンバー関数。 オブジェクトが完了したら、ときに呼び出す必要があります、[閉じる](#close)メンバー関数し、破棄、`CDaoTableDef`オブジェクト。  
  
##  <a name="close"></a>  CDaoTableDef::Close  
 このメンバー関数を閉じるし、テーブル定義オブジェクトを解放します。  
  
```  
virtual void Close();
```  
  
### <a name="remarks"></a>コメント  
 呼び出した後に通常**閉じる**で割り当てられた場合、テーブル定義オブジェクトを削除する**新しい**です。  
  
 呼び出すことができます[開く](#open)呼び出した後にもう一度**閉じる**です。 これにより、テーブル定義オブジェクトを再利用できます。  
  
 関連情報については、「Close メソッド」DAO ヘルプのトピックを参照してください。  
  
##  <a name="create"></a>  CDaoTableDef::Create  
 保存されている新しいテーブルを作成するには、このメンバー関数を呼び出します。  
  
```  
virtual void Create(
    LPCTSTR lpszName,  
    long lAttributes = 0,  
    LPCTSTR lpszSrcTable = NULL,  
    LPCTSTR lpszConnect = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszName`  
 テーブルの名前を含む文字列へのポインター。  
  
 `lAttributes`  
 テーブル定義オブジェクトによって表されるテーブルの特性に対応する値。 ビットごとの OR を使用して、次の定数のいずれかを結合できます。  
  
|定数|説明|  
|--------------|-----------------|  
|**dbAttachExclusive**|Microsoft Jet データベース エンジンを使用するデータベース、テーブルは排他的に開かれて、接続されているテーブルを示します。|  
|**dbAttachSavePWD**|Microsoft Jet データベース エンジンを使用してデータベースの場合は、接続情報を使用、ユーザーの ID とパスワード、接続されているテーブルが保存されたことを示します。|  
|**dbSystemObject**|テーブルが、Microsoft Jet データベース エンジンによって提供されるシステム テーブルであることを示します。|  
|**dbHiddenObject**|テーブルが、Microsoft Jet データベース エンジンによって提供される非表示のテーブルであることを示します。|  
  
 *lpszSrcTable*  
 ソース テーブル名を含む文字列へのポインター。 既定ではこの値として初期化**NULL**です。  
  
 `lpszConnect`  
 既定の接続文字列を含む文字列へのポインター。 既定ではこの値として初期化**NULL**です。  
  
### <a name="remarks"></a>コメント  
 呼び出すことができます、テーブル定義をという名前が、いったん[追加](#append)をデータベースのテーブル定義のコレクションに、テーブル定義を保存します。 呼び出した後**Append**、開いている状態では、テーブル定義、および作成を行うこともできます、 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)オブジェクト。  
  
 関連情報については、DAO ヘルプの「CreateTableDef メソッド」を参照してください。  
  
##  <a name="createfield"></a>  CDaoTableDef::CreateField  
 テーブルにフィールドを追加するには、このメンバー関数を呼び出します。  
  
```  
void CreateField(
    LPCTSTR lpszName,  
    short nType,  
    long lSize,  
    long lAttributes = 0);  
  
void CreateField(CDaoFieldInfo& fieldinfo);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszName`  
 このフィールドの名前を指定する文字列式へのポインター。  
  
 `nType`  
 フィールドのデータ型を示す値。 この設定は、これらの値のいずれかになります。  
  
|型|サイズ (バイト)|説明|  
|----------|--------------------|-----------------|  
|**dbBoolean**|1 バイト|BOOL|  
|**dbByte**|1|BYTE|  
|**dbInteger**|2|int|  
|**dbLong**|4|long|  
|**dbCurrency**|8|通貨 ( [COleCurrency](../../mfc/reference/colecurrency-class.md))|  
|**dbSingle**|4|float|  
|**dbDouble**|8|double|  
|**dbDate**|8|日付/時刻 ( [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md))|  
|**dbText**|1 - 255|テキスト ( [CString](../../atl-mfc-shared/reference/cstringt-class.md))|  
|**dbLongBinary**|0|長いバイナリ (OLE オブジェクト)、 [CLongBinary](../../mfc/reference/clongbinary-class.md)または[CByteArray](../../mfc/reference/cbytearray-class.md)|  
|**dbMemo**|0|メモ ( [CString](../../atl-mfc-shared/reference/cstringt-class.md))|  
  
 `lSize`  
 最大サイズ (バイト) のテキストを含むフィールドのまたはテキストまたは数値を格納するフィールドの固定サイズを示す値。 `lSize`テキスト フィールドを除くすべてのパラメーターは無視されます。  
  
 `lAttributes`  
 フィールドの特性に対応する値は、ビットごとの OR を使用して結合できます。  
  
|定数|説明|  
|--------------|-----------------|  
|**dbFixedField**|フィールド サイズには、(数値フィールドの既定値) は固定です。|  
|**dbVariableField**|フィールド サイズは、変数 (テキスト フィールドのみ) です。|  
|**dbAutoIncrField**|新しいレコードのフィールドの値は変更できない一意の長整数を自動的にインクリメントされます。 Microsoft Jet データベースのテーブルのみサポートされます。|  
|**dbUpdatableField**|フィールドの値を変更できます。|  
|**dbDescending**|降順で並べ替えられます (Z、A または 100-0) 順序 (インデックス オブジェクトのフィールド コレクション内のフィールド オブジェクトにのみ適用されます)。 この定数を省略した場合に昇順に並べ替えられます (A ~ Z、または 0 - 100) 順序 (既定値)。|  
  
 `fieldinfo`  
 参照、 [CDaoFieldInfo](../../mfc/reference/cdaofieldinfo-structure.md)構造体。  
  
### <a name="remarks"></a>コメント  
 A **DAOField** (OLE) オブジェクトが作成され、フィールド コレクションに追加、 **DAOTableDef** (OLE) オブジェクト。 オブジェクトのプロパティを確認するための使用だけでなく使用することも`CDaoFieldInfo`テーブル定義内の新しいフィールドを作成するための入力パラメーターを構築するためにします。 最初のバージョン`CreateField`が簡単に使用すると、さらに細かく制御する場合は、第 2 のバージョンを使用することが`CreateField`、受け取り、`CDaoFieldInfo`パラメーター。  
  
 バージョンを使用する場合`CreateField`を受け取る、`CDaoFieldInfo`パラメーター、する必要があります慎重に各設定の次のメンバー、`CDaoFieldInfo`構造体。  
  
- **m_strName**  
  
- `m_nType`  
  
- **m_lSize**  
  
- **m_lAttributes**  
  
- **m_bAllowZeroLength**  
  
 残りのメンバー`CDaoFieldInfo`に設定する必要があります**0**、 **FALSE**、または、メンバーの必要に応じて、空の文字列または`CDaoException`発生する可能性があります。  
  
 関連情報については、DAO ヘルプの「CreateField メソッド」を参照してください。  
  
##  <a name="createindex"></a>  CDaoTableDef::CreateIndex  
 テーブルにインデックスを追加するには、この関数を呼び出します。  
  
```  
void CreateIndex(CDaoIndexInfo& indexinfo);
```  
  
### <a name="parameters"></a>パラメーター  
 `indexinfo`  
 参照、 [CDaoIndexInfo](../../mfc/reference/cdaoindexinfo-structure.md)構造体。  
  
### <a name="remarks"></a>コメント  
 インデックスは、データベースのテーブルと重複するレコードを受け付けるかどうかからアクセスされるレコードの順序を指定します。 インデックスでは、データに効率的にアクセスも提供します。  
  
 テーブルにインデックスを作成する必要はありませんが、大規模なインデックスなしのテーブルで特定のレコードへのアクセスまたはレコード セットを作成することができます、長い時間がかかります。 その一方で、多くのインデックスを作成する速度が低下し更新、追加、および削除の操作をすべてのインデックスが自動的に更新します。 作成するインデックスを決定するときに、これらの要因を考慮します。  
  
 次のメンバー、`CDaoIndexInfo`構造を設定する必要があります。  
  
- **m_strName**名前を指定する必要があります。  
  
- `m_pFieldInfos` 型の配列を指す必要があります`CDaoIndexFieldInfo`構造体。  
  
- `m_nFields` 配列内のフィールドの数を指定する必要があります`CDaoFieldInfo`構造体。  
  
 残りのメンバーは無視される場合に設定されます**FALSE**です。 さらに、 **m_lDistinctCount**メンバーは、インデックスの作成時に無視されます。  
  
##  <a name="deletefield"></a>  CDaoTableDef::DeleteField  
 フィールドを削除し、アクセスできないようにするには、このメンバー関数を呼び出します。  
  
```  
void DeleteField(LPCTSTR lpszName);  
void DeleteField(int nIndex);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszName`  
 既存のフィールドの名前を指定する文字列式へのポインター。  
  
 `nIndex`  
 インデックスで検索する場合のテーブルの 0 から始まるフィールド コレクション内のフィールドのインデックス。  
  
### <a name="remarks"></a>コメント  
 データベースに追加されていない新しいオブジェクトでこのメンバー関数を使用する場合や[CanUpdate](#canupdate) 0 以外を返します。  
  
 関連情報については、「Delete メソッド」DAO ヘルプのトピックを参照してください。  
  
##  <a name="deleteindex"></a>  CDaoTableDef::DeleteIndex  
 基になるテーブルのインデックスを削除するには、このメンバー関数を呼び出します。  
  
```  
void DeleteIndex(LPCTSTR lpszName);  
void DeleteIndex(int nIndex);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszName`  
 既存のインデックスの名前を指定する文字列式へのポインター。  
  
 `nIndex`  
 インデックスで検索する場合のデータベースの 0 から始まる TableDefs コレクション内のインデックス オブジェクトの配列インデックス。  
  
### <a name="remarks"></a>コメント  
 データベースに追加されていない新しいオブジェクトでこのメンバー関数を使用する場合や[CanUpdate](#canupdate) 0 以外を返します。  
  
 関連情報については、「Delete メソッド」DAO ヘルプのトピックを参照してください。  
  
##  <a name="getattributes"></a>  CDaoTableDef::GetAttributes  
 `CDaoTableDef`オブジェクトによって表されるテーブルの特性を指定する、戻り値、`CDaoTableDef`オブジェクトし、これらの定数の合計を指定できます。  
  
```  
long GetAttributes();
```  
  
### <a name="return-value"></a>戻り値  
 1 つまたは複数の特性を示す値を返します、`CDaoTableDef`オブジェクト。  
  
### <a name="remarks"></a>コメント  
  
|定数|説明|  
|--------------|-----------------|  
|**dbAttachExclusive**|Microsoft Jet データベース エンジンを使用するデータベース、テーブルは排他的に開かれて、接続されているテーブルを示します。|  
|**dbAttachSavePWD**|Microsoft Jet データベース エンジンを使用してデータベースの場合は、接続情報を使用、ユーザーの ID とパスワード、接続されているテーブルが保存されたことを示します。|  
|**dbSystemObject**|テーブルが、Microsoft Jet データベース エンジンによって提供されるシステム テーブルであることを示します。|  
|**dbHiddenObject**|テーブルが、Microsoft Jet データベース エンジンによって提供される非表示のテーブルであることを示します。|  
|**dbAttachedTable**|テーブルが Paradox データベースなどの非 ODBC データベースからのアタッチのテーブルであることを示します。|  
|**dbAttachedODBC**|テーブルが Microsoft SQL Server などの ODBC データベースからのアタッチのテーブルであることを示します。|  
  
 システム テーブルは、さまざまな内部情報を格納する Microsoft Jet データベース エンジンによって作成されるテーブルです。  
  
 非表示の表は、一時的に使用、Microsoft Jet データベース エンジンによって作成されたテーブルです。  
  
 関連情報については、DAO ヘルプの「属性プロパティ」を参照してください。  
  
##  <a name="getconnect"></a>  CDaoTableDef::GetConnect  
 データ ソースの接続文字列を取得するには、このメンバー関数を呼び出します。  
  
```  
CString GetConnect();
```  
  
### <a name="return-value"></a>戻り値  
 A`CString`テーブルのパスとデータベースの種類を含むオブジェクト。  
  
### <a name="remarks"></a>コメント  
 `CDaoTableDef` 、接続されているテーブルを表すオブジェクト、`CString`オブジェクトは、1 つまたは 2 つの部分 (データベースの型指定子およびデータベースへのパス) で構成されます。  
  
 次の表に示すようにパスが、データベース ファイルを含むディレクトリの完全なパスし、識別子の前にする必要があります"DATABASE ="です。 場合によっては (Microsoft Jet や Microsoft Excel で次のようにデータベース) として、データベース パス引数で特定のファイル名が含まれています。  
  
 内のテーブル[CDaoTableDef::SetConnect](#setconnect)可能なデータベースの種類とその対応するデータベースの指定子とパスを示しています。  
  
 Microsoft Jet データベースのベース テーブルでは、指定子は空の文字列 ("") です。  
  
 ODBC ドライバーが、テーブルにアクセス ログイン ダイアログ ボックス最初の時刻を表示する場合は、パスワードが必要な指定されていませんし、もう一度接続を閉じて、再び開く場合。 接続されているテーブルがある場合、 **dbAttachSavePWD**属性で、ログイン プロンプトは表示されません、テーブルを再び開くときにします。  
  
 関連情報については、"接続 Property"DAO ヘルプのトピックを参照してください。  
  
##  <a name="getdatecreated"></a>  CDaoTableDef::GetDateCreated  
 テーブルの基になる日付と時刻を判断するには、この関数を呼び出して、`CDaoTableDef`オブジェクトが作成されました。  
  
```  
COleDateTime GetDateCreated();
```  
  
### <a name="return-value"></a>戻り値  
 基になるテーブルの作成日時を含む値、`CDaoTableDef`オブジェクト。  
  
### <a name="remarks"></a>コメント  
 日付と時刻の設定は、ベース テーブルが作成または最後に更新されたコンピューターから派生します。 マルチ ユーザー環境の場合は、ユーザーは、矛盾を避けるため、ファイル サーバーから直接これらの設定を取得する必要があります。つまり、すべてのクライアントが「標準」タイム ソースを使用する必要があります: 1 台のサーバーからです。  
  
 関連情報については、DAO ヘルプのトピックの「作成日時、LastUpdated プロパティ」を参照してください。  
  
##  <a name="getdatelastupdated"></a>  CDaoTableDef::GetDateLastUpdated  
 テーブルの基になる日付と時刻を判断するには、この関数を呼び出して、**どちら**オブジェクトが最後に更新されました。  
  
```  
COleDateTime GetDateLastUpdated();
```  
  
### <a name="return-value"></a>戻り値  
 基になるテーブルの日付と時刻を格納する値、**どちら**オブジェクトが最後に更新されました。  
  
### <a name="remarks"></a>コメント  
 日付と時刻の設定は、ベース テーブルが作成または最後に更新されたコンピューターから派生します。 マルチ ユーザー環境の場合は、ユーザーは、矛盾を避けるため、ファイル サーバーから直接これらの設定を取得する必要があります。つまり、すべてのクライアントが「標準」タイム ソースを使用する必要があります: 1 台のサーバーからです。  
  
 関連情報については、DAO ヘルプのトピックの「作成日時、LastUpdated プロパティ」を参照してください。  
  
##  <a name="getfieldcount"></a>  CDaoTableDef::GetFieldCount  
 テーブルで定義されたフィールドの数を取得するには、このメンバー関数を呼び出します。  
  
```  
short GetFieldCount();
```  
  
### <a name="return-value"></a>戻り値  
 テーブル内のフィールドの数。  
  
### <a name="remarks"></a>コメント  
 その値が 0 の場合に含まれないオブジェクト コレクションです。  
  
 関連情報については、「Count プロパティ」DAO ヘルプのトピックを参照してください。  
  
##  <a name="getfieldinfo"></a>  CDaoTableDef::GetFieldInfo  
 さまざまなテーブル定義で定義されているフィールドに関する情報を取得するには、このメンバー関数を呼び出します。  
  
```  
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
 `nIndex`  
 インデックスで検索する場合のテーブルの 0 から始まるフィールド コレクション内のフィールド オブジェクトのインデックス。  
  
 `fieldinfo`  
 参照、 [CDaoFieldInfo](../../mfc/reference/cdaofieldinfo-structure.md)構造体。  
  
 `dwInfoOptions`  
 取得するフィールドに関する情報を指定するオプション。 使用可能なオプションを返す関数が何もここで表示されます。  
  
- `AFX_DAO_PRIMARY_INFO` (既定値)名前、種類、サイズ、属性です。 最も高速なパフォーマンスを得るには、このオプションを使用します。  
  
- `AFX_DAO_SECONDARY_INFO` プライマリについては、プラス: 必要に応じて、序数位置 0 長、照合順序、外部名、ソース フィールド、ソース テーブルを許可します。  
  
- `AFX_DAO_ALL_INFO` プライマリとセカンダリの情報と: 検証規則、入力テキストの場合は、既定値  
  
 `lpszName`  
 名前で検索のフィールド オブジェクトの名前へのポインター。 名前は、フィールドの一意名で、最大 64 文字の文字列です。  
  
### <a name="remarks"></a>コメント  
 関数の 1 つのバージョンでは、インデックスを使用してフィールドを検索することができます。 その他のバージョンでは、名前、フィールドを検索することができます。  
  
 返される情報については、次を参照してください。、 [CDaoFieldInfo](../../mfc/reference/cdaofieldinfo-structure.md)構造体。 この構造体メンバーの説明に上記の情報項目に対応するは`dwInfoOptions`します。 1 つのレベルの情報を要求するときに、同様に、以前のレベルの情報を取得します。  
  
 関連情報については、DAO ヘルプの「属性プロパティ」を参照してください。  
  
##  <a name="getindexcount"></a>  CDaoTableDef::GetIndexCount  
 テーブルのインデックスの数を取得するには、このメンバー関数を呼び出します。  
  
```  
short GetIndexCount();
```  
  
### <a name="return-value"></a>戻り値  
 テーブルのインデックスの数。  
  
### <a name="remarks"></a>コメント  
 その値が 0 の場合に含まれないインデックス コレクションです。  
  
 関連情報については、「Count プロパティ」DAO ヘルプのトピックを参照してください。  
  
##  <a name="getindexinfo"></a>  CDaoTableDef::GetIndexInfo  
 さまざまなテーブル定義で定義されているインデックスに関する情報を取得するには、このメンバー関数を呼び出します。  
  
```  
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
 `nIndex`  
 コレクション内での位置で検索する場合のテーブルの 0 から始まるインデックス コレクション内のインデックス オブジェクトの数値インデックス。  
  
 `indexinfo`  
 参照、 [CDaoIndexInfo](../../mfc/reference/cdaoindexinfo-structure.md)構造体。  
  
 `dwInfoOptions`  
 取得するインデックスに関する情報を指定するオプション。 使用可能なオプションを返す関数が何もここで表示されます。  
  
- `AFX_DAO_PRIMARY_INFO` 名前、フィールドの情報、フィールドです。 最も高速なパフォーマンスを得るには、このオプションを使用します。  
  
- `AFX_DAO_SECONDARY_INFO` プライマリについては、プラス: プライマリ、Unique、クラスター化された、Null を無視、必要に応じて、異形式  
  
- `AFX_DAO_ALL_INFO` プライマリとセカンダリの情報と: 個別のカウント  
  
 `lpszName`  
 名前で検索のインデックス オブジェクトの名前へのポインター。  
  
### <a name="remarks"></a>コメント  
 関数の 1 つのバージョンでは、コレクション内の位置でインデックスを検索することができます。 その他のバージョンでは、名前、インデックスを検索することができます。  
  
 返される情報については、次を参照してください。、 [CDaoIndexInfo](../../mfc/reference/cdaoindexinfo-structure.md)構造体。 この構造体メンバーの説明に上記の情報項目に対応するは`dwInfoOptions`します。 1 つのレベルの情報を要求するときに、同様に、以前のレベルの情報を取得します。  
  
 関連情報については、DAO ヘルプの「属性プロパティ」を参照してください。  
  
##  <a name="getname"></a>  CDaoTableDef::GetName  
 基になるテーブルのユーザー定義名を取得するには、このメンバー関数を呼び出します。  
  
```  
CString GetName();
```  
  
### <a name="return-value"></a>戻り値  
 ユーザー定義テーブルの名前。  
  
### <a name="remarks"></a>コメント  
 この名前から始まり、文字と、最大 64 文字を含めることができます。 数字を含めることができ、アンダー スコア文字ですが、区切り記号やスペースを含めることはできません。  
  
 関連情報については、DAO ヘルプの「名前プロパティ」を参照してください。  
  
##  <a name="getrecordcount"></a>  CDaoTableDef::GetRecordCount  
 レコードの数を調べるには、このメンバー関数を呼び出す、`CDaoTableDef`オブジェクト。  
  
```  
long GetRecordCount();
```  
  
### <a name="return-value"></a>戻り値  
 テーブル定義オブジェクトにアクセスするレコードの数。  
  
### <a name="remarks"></a>コメント  
 呼び出す`GetRecordCount`テーブル型に対する`CDaoTableDef`オブジェクトがテーブル内のレコードの概数を反映し、テーブルのレコードが追加または削除されるとすぐに影響を受けるはします。 トランザクションがレコードの数の一部として表示されますが呼び出されるまでロールバック[CDaoWorkSpace::CompactDatabase](../../mfc/reference/cdaoworkspace-class.md#compactdatabase)です。 A`CDaoTableDef`レコードのないオブジェクトが 0 のレコード数プロパティの設定。 アタッチされているテーブルまたは ODBC データベースを使用するときに`GetRecordCount`常に-1 を返します。  
  
 関連情報については、DAO ヘルプの「RecordCount プロパティ」を参照してください。  
  
##  <a name="getsourcetablename"></a>  CDaoTableDef::GetSourceTableName  
 ソース データベースのアタッチ テーブルの名前を取得するには、このメンバー関数を呼び出します。  
  
```  
CString GetSourceTableName();
```  
  
### <a name="return-value"></a>戻り値  
 A`CString`ネイティブ データ テーブルの場合は、接続されたテーブル、または空の文字列のソース名を指定するオブジェクト。  
  
### <a name="remarks"></a>コメント  
 接続されたテーブルは、Microsoft Jet データベースにリンクされている別のデータベースのテーブルです。 アタッチされているテーブルのデータは、他のアプリケーションで操作できる、外部データベースに残ります。  
  
 関連情報については、DAO ヘルプの「SourceTableName プロパティ」を参照してください。  
  
##  <a name="getvalidationrule"></a>  CDaoTableDef::GetValidationRule  
 テーブル定義の検証規則を取得するには、このメンバー関数を呼び出します。  
  
```  
CString GetValidationRule();
```  
  
### <a name="return-value"></a>戻り値  
 A **CString**が変更またはテーブルに追加すると、フィールド内のデータを検証するオブジェクト。  
  
### <a name="remarks"></a>コメント  
 検証規則は、更新操作に関連して使用されます。 テーブル定義に、検証規則が含まれている場合、そのテーブル定義の更新プログラムは、データが変更される前に事前に定義された条件に一致する必要があります。 変更が一致しない場合、条件の値を含む例外[GetValidationText](#getvalidationtext)がスローされます。 `CDaoTableDef`オブジェクトをこの`CString`は、接続されているテーブルと、ベース テーブルの読み取り/書き込みの読み取り専用です。  
  
 関連情報については、"Validationrule"DAO ヘルプのトピックを参照してください。  
  
##  <a name="getvalidationtext"></a>  CDaoTableDef::GetValidationText  
 ユーザーが入力の検証規則に一致しないデータを表示する文字列を取得するには、この関数を呼び出します。  
  
```  
CString GetValidationText();
```  
  
### <a name="return-value"></a>戻り値  
 A`CString`検証規則に一致しないデータを入力した場合に表示されるテキストを指定するオブジェクト。  
  
### <a name="remarks"></a>コメント  
 `CDaoTableDef`オブジェクトをこの`CString`は、接続されているテーブルと、ベース テーブルの読み取り/書き込みの読み取り専用です。  
  
 関連情報については、「プロパティ」DAO ヘルプのトピックを参照してください。  
  
##  <a name="isopen"></a>  CDaoTableDef::IsOpen  
 決定するには、このメンバー関数を呼び出すかどうか、`CDaoTableDef`オブジェクトが現在開いています。  
  
```  
BOOL IsOpen() const;  
```  
  
### <a name="return-value"></a>戻り値  
 0 以外の場合、`CDaoTableDef`オブジェクトが開かれている場合は 0 です。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="m_pdatabase"></a>  CDaoTableDef::m_pDatabase  
 ポインターが含まれています、 [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md)このテーブルのオブジェクト。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="m_pdaotabledef"></a>  CDaoTableDef::m_pDAOTableDef  
 DAO tabledef オブジェクト基になるの OLE インターフェイスへのポインターが含まれています、`CDaoTableDef`オブジェクト。  
  
### <a name="remarks"></a>コメント  
 DAO インターフェイスに直接アクセスする必要がある場合は、このポインターを使用します。  
  
##  <a name="open"></a>  CDaoTableDef::Open  
 開くには、テーブル定義には、このメンバー関数がデータベースに保存した呼び出しはのテーブル定義のコレクションです。  
  
```  
virtual void Open(LPCTSTR lpszName);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszName`  
 テーブル名を指定する文字列へのポインター。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="refreshlink"></a>  CDaoTableDef::RefreshLink  
 接続されたテーブルの接続情報を更新するには、このメンバー関数を呼び出します。  
  
```  
void RefreshLink();
```  
  
### <a name="remarks"></a>コメント  
 呼び出して、接続されているテーブルの接続情報を変更する[SetConnect](#setconnect) 、対応する`CDaoTableDef`オブジェクトとを使用して、`RefreshLink`情報を更新するメンバー関数。 呼び出すと`RefreshLink`、接続されているテーブルのプロパティは変更されません。  
  
 強制的に、変更された接続情報を反映する、すべての開いている[CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)このテーブルの定義に基づくオブジェクトを閉じる必要があります。  
  
 関連情報については、DAO ヘルプの「RefreshLink メソッド」を参照してください。  
  
##  <a name="setattributes"></a>  CDaoTableDef::SetAttributes  
 1 つまたは複数の特性を示す値を設定、`CDaoTableDef`オブジェクト。  
  
```  
void SetAttributes(long lAttributes);
```  
  
### <a name="parameters"></a>パラメーター  
 `lAttributes`  
 によって表されるテーブルの特性、`CDaoTableDef`オブジェクトし、これらの定数の合計を指定できます。  
  
|定数|説明|  
|--------------|-----------------|  
|**dbAttachExclusive**|Microsoft Jet データベース エンジンを使用するデータベース、テーブルは排他的に開かれて、接続されているテーブルを示します。|  
|**dbAttachSavePWD**|Microsoft Jet データベース エンジンを使用してデータベースの場合は、接続情報を使用、ユーザーの ID とパスワード、接続されているテーブルが保存されたことを示します。|  
|**dbSystemObject**|テーブルが、Microsoft Jet データベース エンジンによって提供されるシステム テーブルであることを示します。|  
|**dbHiddenObject**|テーブルが、Microsoft Jet データベース エンジンによって提供される非表示のテーブルであることを示します。|  
  
### <a name="remarks"></a>コメント  
 に複数の属性を設定するときは、ビットごとの OR 演算子を使用して適切な定数を組み合わせることができます。 設定**dbAttachExclusive**非添付テーブルで例外が生成されます。 結合は次の値も、例外が発生します。  
  
- **dbAttachExclusive &#124; dbAttachedODBC**  
  
- **dbAttachSavePWD &#124; dbAttachedTable**  
  
 関連情報については、DAO ヘルプの「属性プロパティ」を参照してください。  
  
##  <a name="setconnect"></a>  CDaoTableDef::SetConnect  
 `CDaoTableDef`アタッチ テーブルの文字列オブジェクトを表すオブジェクトは、1 つまたは 2 つの部分 (データベースの型指定子およびデータベースへのパス) で構成されます。  
  
```  
void SetConnect(LPCTSTR lpszConnect);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszConnect`  
 ODBC、またはインストール可能な ISAM ドライバーに渡す追加のパラメーターを指定する文字列式へのポインター。  
  
### <a name="remarks"></a>コメント  
 次の表に示すようにパスが、データベース ファイルを含むディレクトリの完全なパスし、識別子の前にする必要があります"DATABASE ="です。 場合によっては (Microsoft Jet や Microsoft Excel で次のようにデータベース) として、データベース パス引数で特定のファイル名が含まれています。  
  
> [!NOTE]
>  フォームのパスのステートメントに等号 (=) の前後に空白を含めないでください"データベース ドライブを =:\\\path"です。 スローされた例外と接続の障害が発生したこのが発生します。  
  
 次の表は、可能なデータベースの種類と、対応するデータベースの指定子とパスを示しています。  
  
|データベースの種類|指定子|パス|  
|-------------------|---------------|----------|  
|Jet データベース エンジンを使用して、データベース|"[ `database`];"|" `drive`:\\\ *パス*\\\ *filename*です。MDB"|  
|dBASE III|"dBASE III;"|" `drive`:\\\ *パス*"|  
|dBASE IV|"dBASE IV;"|" `drive`:\\\ *パス*"|  
|dBASE 5|"dBASE 5.0 です。"|" `drive`:\\\ *パス*"|  
|Paradox 3.x|"Paradox 3.x;"|" `drive`:\\\ *パス*"|  
|Paradox 4.x|"Paradox 4.x;"|" `drive`:\\\ *パス*"|  
|Paradox 5.x|"Paradox 5.x;"|" `drive`:\\\ *パス*"|  
|Excel 3.0|「Excel 3.0」です。|" `drive`:\\\ *パス*\\\ *filename*です。XLS"|  
|Excel 4.0|「Excel 4.0;」|" `drive`:\\\ *パス*\\\ *filename*です。XLS"|  
|Excel 5.0 または Excel 95|「Excel 5.0 です。」|" `drive`:\\\ *パス*\\\ *filename*です。XLS"|  
|Excel 97|「Excel 8.0;」|" `drive`:\\\ *パス*\ *filename*です。XLS"|  
|HTML のインポート|「HTML のインポートです。」|" `drive`:\\\ *パス*\ *filename*"|  
|HTML のエクスポート|「HTML エクスポート;」|" `drive`:\\\ *パス*"|  
|テキスト|"Text"です。|"ドライブ:\\\path"|  
|ODBC|"ODBC です。データベース =`database`です。UID =*ユーザー*です。PWD =*パスワード*です。DSN = *%datasourcename;* LOGINTIMEOUT =*秒;*"(すべてのサーバーの完全な接続文字列とは限りません。 これは単なる例。 パラメーター間にスペースが非常に重要です。)|なし|  
|Exchange|"Exchange です。<br /><br /> MAPILEVEL = *folderpath*です。<br /><br /> [TABLETYPE = {0 &AMP;#124; 1} です]。<br /><br /> [プロファイル =*プロファイル*です]。<br /><br /> [PWD =*パスワード*です]。<br /><br /> [データベース = `database`;]"|*"ドライブ*:\\\ *パス*\\\ *filename*です。MDB"|  
  
> [!NOTE]
>  DAO 3.5 の時点では、市販がサポートされていません。  
  
 二重の円記号を使用する必要があります (\\\\)、接続文字列にします。 既存の接続を使用して、プロパティを変更したかどうかは`SetConnect`、後で呼び出す必要があります[RefreshLink](#refreshlink)です。 使用して接続プロパティを初期化する場合`SetConnect`、呼び出しではない必要がある`RefreshLink`、テーブル定義を追加するように選択する必要があります、最初にします。  
  
 ODBC ドライバーが、テーブルにアクセス ログイン ダイアログ ボックス最初の時刻を表示する場合は、パスワードが必要な指定されていませんし、もう一度接続を閉じて、再び開く場合。  
  
 接続文字列を設定することができます、`CDaoTableDef`オブジェクトに元の引数を提供することによって、**作成**メンバー関数。 設定を確認して、型、パス、ユーザー ID、パスワード、またはデータベースの ODBC データ ソースを確認することができます。 詳細については、特定のドライバーのマニュアルを参照してください。  
  
 関連情報については、"接続 Property"DAO ヘルプのトピックを参照してください。  
  
##  <a name="setname"></a>  CDaoTableDef::SetName  
 ユーザー定義テーブルの名前を設定するには、このメンバー関数を呼び出します。  
  
```  
void SetName(LPCTSTR lpszName);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszName`  
 テーブルの名前を指定する文字列式へのポインター。  
  
### <a name="remarks"></a>コメント  
 名前は文字で始める必要があり、最大 64 文字を含めることができます。 数字を含めることができ、アンダー スコア文字ですが、区切り記号やスペースを含めることはできません。  
  
 関連情報については、DAO ヘルプの「名前プロパティ」を参照してください。  
  
##  <a name="setsourcetablename"></a>  CDaoTableDef::SetSourceTableName  
 接続されているテーブルの名前またはベース テーブルの名前を指定するには、このメンバー関数を呼び出す、`CDaoTableDef`オブジェクトが基のデータの元のソースに存在します。  
  
```  
void SetSourceTableName(LPCTSTR lpszSrcTableName);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpszSrcTableName*  
 外部データベースのテーブル名を指定する文字列式へのポインター。 基本テーブルの場合は、設定は、空の文字列 ("") です。  
  
### <a name="remarks"></a>コメント  
 呼び出す必要があります[RefreshLink](#refreshlink)です。 このプロパティの設定は、ベース テーブルと読み取り/書き込みの接続されたテーブルまたはコレクションに追加されていないオブジェクトに対しては空です。  
  
 関連情報については、DAO ヘルプの「SourceTableName プロパティ」を参照してください。  
  
##  <a name="setvalidationrule"></a>  CDaoTableDef::SetValidationRule  
 テーブル定義の検証規則を設定するには、このメンバー関数を呼び出します。  
  
```  
void SetValidationRule(LPCTSTR lpszValidationRule);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpszValidationRule*  
 操作を評価する文字列式へのポインター。  
  
### <a name="remarks"></a>コメント  
 検証規則は、更新操作に関連して使用されます。 テーブル定義に、検証規則が含まれている場合、そのテーブル定義の更新プログラムは、データが変更される前に事前に定義された条件に一致する必要があります。 変更が一致しない場合、条件のテキストを含む例外[GetValidationText](#getvalidationtext)が表示されます。  
  
 検証方法は、Microsoft Jet データベース エンジンを使用するデータベースにのみサポートされます。 式は、ユーザー定義関数、集計関数のドメイン、SQL の集計関数、またはクエリを参照できません。 検証規則を`CDaoTableDef`オブジェクトは、そのオブジェクト内の複数のフィールドを参照できます。  
  
 たとえば、という名前のフィールド`hire_date`と`termination_date`、検証規則があります。  
  
 [!code-cpp[NVC_MFCDatabase#34](../../mfc/codesnippet/cpp/cdaotabledef-class_1.cpp)]  
  
 関連情報については、"Validationrule"DAO ヘルプのトピックを参照してください。  
  
##  <a name="setvalidationtext"></a>  CDaoTableDef::SetValidationText  
 検証規則の例外のテキストを設定するには、このメンバー関数を呼び出す、 `CDaoTableDef` Microsoft Jet データベース エンジンでサポートされている、基になるベース テーブルを持つオブジェクト。  
  
```  
void SetValidationText(LPCTSTR lpszValidationText);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpszValidationText*  
 データを入力した場合に表示されるテキストを指定する文字列式へのポインターが正しくありません。  
  
### <a name="remarks"></a>コメント  
 アタッチ テーブルの検証のテキストを設定することはできません。  
  
 関連情報については、「プロパティ」DAO ヘルプのトピックを参照してください。  
  
## <a name="see-also"></a>関連項目  
 [CObject クラス](../../mfc/reference/cobject-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CDaoDatabase クラス](../../mfc/reference/cdaodatabase-class.md)   
 [CDaoRecordset クラス](../../mfc/reference/cdaorecordset-class.md)
