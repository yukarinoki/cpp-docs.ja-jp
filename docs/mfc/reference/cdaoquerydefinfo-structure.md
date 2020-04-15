---
title: CDaoQueryDefInfo 構造体
ms.date: 11/04/2016
f1_keywords:
- CDaoQueryDefInfo
helpviewer_keywords:
- DAO (Data Access Objects), QueryDefs collection
- CDaoQueryDefInfo structure [MFC]
ms.assetid: e20837dc-e78d-4171-a195-1b4075fb5d2a
ms.openlocfilehash: e2f0325237a30989637821464c63a4d8b8000b1e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368932"
---
# <a name="cdaoquerydefinfo-structure"></a>CDaoQueryDefInfo 構造体

構造体`CDaoQueryDefInfo`には、データ アクセス オブジェクト (DAO) に定義されたクエリ定義オブジェクトに関する情報が含まれています。

## <a name="syntax"></a>構文

```
struct CDaoQueryDefInfo
{
    CString m_strName;               // Primary
    short m_nType;   // Primary
    COleDateTime m_dateCreated;      // Secondary
    COleDateTime m_dateLastUpdated;  // Secondary
    BOOL m_bUpdatable;               // Secondary
    BOOL m_bReturnsRecords;          // Secondary
    CString m_strSQL;                // All
    CString m_strConnect;            // All
    short m_nODBCTimeout;            // All
};
```

#### <a name="parameters"></a>パラメーター

*m_strName*<br/>
クエリ定義オブジェクトに一意の名前を付けます。 詳細については、DAO ヘルプの「プロパティ名」を参照してください。 このプロパティを直接取得するには[、CDaoQueryDef::GetName](../../mfc/reference/cdaoquerydef-class.md#getname)を呼び出します。

*m_nType*<br/>
クエリ定義オブジェクトの操作の種類を示す値。 値は次のいずれかになります。

- `dbQSelect`選択 — クエリでレコードが選択されます。

- `dbQAction`Action — クエリはデータを移動または変更しますが、レコードは返しません。

- `dbQCrosstab`Crosstab — クエリはスプレッドシートのような形式でデータを返します。

- `dbQDelete`Delete — クエリは指定された行のセットを削除します。

- `dbQUpdate`更新 — クエリによって一連のレコードが変更されます。

- `dbQAppend`追加 — クエリは、テーブルまたはクエリの最後に新しいレコードを追加します。

- `dbQMakeTable`テーブル作成 — クエリはレコードセットから新しいテーブルを作成します。

- `dbQDDL`データ定義 - クエリはテーブルまたはその部分の構造に影響します。

- `dbQSQLPassThrough`パススルー - SQL ステートメントは、中間処理なしでデータベース・バックエンドに直接渡されます。

- `dbQSetOperation`Union — クエリは、重複レコードが削除された 2 つ以上のテーブル内の指定されたすべてのレコードのデータを含むスナップショット タイプのレコードセット オブジェクトを作成します。 重複を含めるには、キーワード**ALL**をクエリ定義の SQL ステートメントに追加します。

- `dbQSPTBulk`レコードを`dbQSQLPassThrough`返さないクエリを指定するために使用します。

> [!NOTE]
> SQL パススルー クエリを作成するには、定数を`dbQSQLPassThrough`設定しません。 これは、Querydef オブジェクトを作成し、Connect プロパティを設定するときに、Jet データベース エンジンによって自動的に設定されます。

詳細については、DAO ヘルプの「型プロパティ」を参照してください。

*m_dateCreated*<br/>
クエリ定義が作成された日時。 クエリ定義が作成された日付を直接取得するには、テーブルに関連付けられたオブジェクトの[GetDateCreated](../../mfc/reference/cdaotabledef-class.md#getdatecreated)メンバー関数を`CDaoTableDef`呼び出します。 詳細については、以下のコメントを参照してください。 DAO ヘルプの「日付作成、最終更新のプロパティ」も参照してください。

*m_dateLastUpdated*<br/>
クエリ定義に対して最後に変更された日時。 テーブルが最後に更新された日付を直接取得するには、クエリ定義の[GetDateLastUpdated](../../mfc/reference/cdaoquerydef-class.md#getdatelastupdated)メンバー関数を呼び出します。 詳細については、以下のコメントを参照してください。 DAO ヘルプの「日付作成、最終更新プロパティ」のトピックを参照してください。

*m_bUpdatable*<br/>
クエリ定義オブジェクトに変更を加えられるかどうかを示します。 このプロパティが TRUE の場合、クエリ定義は更新可能です。それ以外の場合は、そうではありません。 更新可能とは、クエリ定義オブジェクトのクエリ定義を変更できることを意味します。 クエリ定義を更新できる場合、結果のレコードセットが更新可能でない場合でも、クエリ定義を更新できる場合、querydef オブジェクトの更新可能なプロパティは TRUE に設定されます。 このプロパティを直接取得するには、クエリ定義の[CanUpdate](../../mfc/reference/cdaoquerydef-class.md#canupdate)メンバー関数を呼び出します。 詳細については、DAO ヘルプの「更新可能なプロパティ」を参照してください。

*m_bReturnsRecords*<br/>
外部データベースへの SQL パススルー クエリがレコードを返すかどうかを示します。 このプロパティが TRUE の場合、クエリはレコードを返します。 このプロパティを直接取得するには、[呼](../../mfc/reference/cdaoquerydef-class.md#getreturnsrecords)び出します。 外部データベースへの SQL パススルー クエリの中には、レコードが返されるわけではありません。 たとえば、SQL **UPDATE**ステートメントはレコードを返さずにレコードを更新し、SQL **SELECT**ステートメントはレコードを返します。 詳細については、DAO ヘルプの「レコードプロパティの返す」を参照してください。

*m_strSQL*<br/>
クエリ定義オブジェクトによって実行されるクエリを定義する SQL ステートメント。 SQL プロパティには、クエリ実行時にレコードを選択、グループ化、および順序付けする方法を決定する SQL ステートメントが含まれます。 このクエリを使用して、ダイナセット タイプまたはスナップショット タイプのレコードセット オブジェクトに含めるレコードを選択できます。 レコードを返さずにデータを変更する一括クエリを定義することもできます。 このプロパティの値は、クエリ定義の[GetSQL](../../mfc/reference/cdaoquerydef-class.md#getsql)メンバー関数を呼び出すことによって直接取得できます。

*m_strConnect*<br/>
パススルー クエリで使用されるデータベースのソースに関する情報を提供します。 この情報は、接続文字列の形式をとります。 接続文字列の詳細と、このプロパティの値を直接取得する方法については、メンバー関数[CDaoDatabase::GetConnect](../../mfc/reference/cdaodatabase-class.md#getconnect)を参照してください。

*m_nODBCTimeout*<br/>
ODBC データベースでクエリが実行されたときにタイムアウト エラーが発生するまでの、Microsoft Jet データベース エンジンが待機する秒数です。 MICROSOFT SQL Server などの ODBC データベースを使用している場合、ネットワーク トラフィックや ODBC サーバーの使用が多いために遅延が発生することがあります。 Microsoft Jet エンジンがエラーを生成するまでの待機時間を無期限に待機するのではなく、これを指定できます。 デフォルトのタイムアウト値は 60 秒です。 このプロパティの値は、クエリ定義の[GetODBCTimeout](../../mfc/reference/cdaoquerydef-class.md#getodbctimeout)メンバー関数を呼び出すことによって直接取得できます。 詳細については、DAO ヘルプの「ODBC タイムアウト プロパティ」を参照してください。

## <a name="remarks"></a>解説

クエリ定義は、[クラス CDaoQueryDef のオブジェクトです](../../mfc/reference/cdaoquerydef-class.md)。 上のプライマリ、セカンダリ、およびすべてへの参照は、クラス`CDaoDatabase`の[GetQueryDefInfo](../../mfc/reference/cdaodatabase-class.md#getquerydefinfo)メンバー関数によって情報がどのように返されるか示しています。

[メンバー関数](../../mfc/reference/cdaodatabase-class.md#getquerydefinfo)によって取得された情報は、`CDaoQueryDefInfo`構造体に格納されます。 QueryDefs コレクション内のデータベース オブジェクトを呼び出`GetQueryDefInfo`し、クエリ定義オブジェクトが格納されます。 `CDaoQueryDefInfo`また、デバッグ`Dump`ビルドでメンバー関数を定義します。 を使用`Dump`して、オブジェクトの内容を`CDaoQueryDefInfo`ダンプできます。 クラス`CDaoDatabase`には、`CDaoQueryDefInfo`オブジェクトに返されるすべてのプロパティに直接アクセスするためのメンバー関数も用意されているので、 を呼び出す`GetQueryDefInfo`必要が生じそうになることはほとんどありません。

Querydef オブジェクトの Fields コレクションまたは Parameters コレクションに新しいフィールドまたはパラメーター オブジェクトを追加すると、基になるデータベースが新しいオブジェクトに指定されたデータ型をサポートしていない場合は、例外がスローされます。

日付と時刻の設定は、クエリ定義が作成されたコンピュータまたは最後に更新されたコンピュータから取得されます。 マルチユーザー環境では、ユーザーは、DateCreated プロパティと LastUpdated プロパティ設定の不一致を避けるために **、net time**コマンドを使用して、ファイル サーバーからこれらの設定を直接取得する必要があります。

## <a name="requirements"></a>必要条件

**ヘッダー:** afxdao.h

## <a name="see-also"></a>関連項目

[構造体、スタイル、コールバック関数とメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[クラス](../../mfc/reference/cdaoquerydef-class.md)<br/>
[CDaoDatabase クラス](../../mfc/reference/cdaodatabase-class.md)
