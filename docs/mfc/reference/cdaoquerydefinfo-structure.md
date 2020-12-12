---
description: '詳細については、次を参照してください: CDaoQueryDefInfo 構造体'
title: CDaoQueryDefInfo 構造体
ms.date: 11/04/2016
f1_keywords:
- CDaoQueryDefInfo
helpviewer_keywords:
- DAO (Data Access Objects), QueryDefs collection
- CDaoQueryDefInfo structure [MFC]
ms.assetid: e20837dc-e78d-4171-a195-1b4075fb5d2a
ms.openlocfilehash: 46b9b49d91d3d005d941eb585663c205fe30b2da
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97271812"
---
# <a name="cdaoquerydefinfo-structure"></a>CDaoQueryDefInfo 構造体

構造体には、 `CDaoQueryDefInfo` データアクセスオブジェクト (DAO) 用に定義されたクエリ定義オブジェクトに関する情報が含まれています。

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
クエリ定義オブジェクトの名前を一意にします。 詳細については、DAO ヘルプの「Name プロパティ」を参照してください。 [CDaoQueryDef:: GetName](../../mfc/reference/cdaoquerydef-class.md#getname)を呼び出して、このプロパティを直接取得します。

*m_nType*<br/>
クエリ定義オブジェクトの操作の種類を示す値です。 値は次のいずれかになります。

- `dbQSelect` Select: クエリによってレコードが選択されます。

- `dbQAction` アクション-クエリはデータを移動または変更しますが、レコードを返しません。

- `dbQCrosstab` [クロス集計-クエリはスプレッドシートに似た形式でデータを返します。

- `dbQDelete` Delete: クエリは、指定された行のセットを削除します。

- `dbQUpdate` Update: クエリは一連のレコードを変更します。

- `dbQAppend` 追加: クエリは、テーブルまたはクエリの末尾に新しいレコードを追加します。

- `dbQMakeTable` テーブルの作成—このクエリでは、レコードセットから新しいテーブルを作成します。

- `dbQDDL` データ定義: クエリは、テーブルまたはその部分の構造に影響を及ぼします。

- `dbQSQLPassThrough` パススルー-SQL ステートメントは、中間処理を行わずに、データベースバックエンドに直接渡されます。

- `dbQSetOperation` Union: クエリは、重複するレコードが削除されている2つ以上のテーブル内の指定されたすべてのレコードのデータを含むスナップショット型のレコードセットオブジェクトを作成します。 重複部分を含めるには、querydef の SQL ステートメントに **ALL** キーワードを追加します。

- `dbQSPTBulk` レコードを `dbQSQLPassThrough` 返さないクエリを指定するために、と共に使用します。

> [!NOTE]
> SQL パススルークエリを作成するには、定数を設定しません `dbQSQLPassThrough` 。 これは、Microsoft Jet データベースエンジンによって、querydef オブジェクトを作成し、Connect プロパティを設定するときに自動的に設定されます。

詳細については、DAO ヘルプの「Type プロパティ」を参照してください。

*m_dateCreated*<br/>
クエリ定義が作成された日付と時刻。 クエリ定義が作成された日付を直接取得する[](../../mfc/reference/cdaotabledef-class.md#getdatecreated)には、 `CDaoTableDef` テーブルに関連付けられているオブジェクトの GetDateCreated メンバー関数を呼び出します。 詳細については、以下のコメントを参照してください。 DAO ヘルプのトピック「DateCreated、LastUpdated Properties」も参照してください。

*m_dateLastUpdated*<br/>
クエリ定義に対して行われた最新の変更の日付と時刻。 テーブルが最後に更新された日付を直接取得するには、クエリ定義の [Getdatelastupdated](../../mfc/reference/cdaoquerydef-class.md#getdatelastupdated) メンバー関数を呼び出します。 詳細については、以下のコメントを参照してください。 DAO ヘルプの「DateCreated、LastUpdated Properties」を参照してください。

*m_bUpdatable*<br/>
Querydef オブジェクトに変更を加えることができるかどうかを示します。 このプロパティが TRUE の場合、クエリ定義は更新可能です。それ以外の場合は、そうではありません。 更新可能とは、querydef オブジェクトのクエリ定義を変更できることを意味します。 クエリ定義を更新できる場合は、結果のレコードセットが更新可能でない場合でも、querydef オブジェクトの更新可能なプロパティは TRUE に設定されます。 このプロパティを直接取得するには、クエリ定義の [CanUpdate](../../mfc/reference/cdaoquerydef-class.md#canupdate) メンバー関数を呼び出します。 詳細については、DAO ヘルプの「更新可能なプロパティ」を参照してください。

*m_bReturnsRecords*<br/>
外部データベースに対する SQL パススルークエリがレコードを返すかどうかを示します。 このプロパティが TRUE の場合、クエリはレコードを返します。 このプロパティを直接取得するには、 [CDaoQueryDef:: GetReturnsRecords](../../mfc/reference/cdaoquerydef-class.md#getreturnsrecords)を呼び出します。 外部データベースに対するすべての SQL パススルークエリがレコードを返すわけではありません。 たとえば、sql **UPDATE** ステートメントは、レコードを返さずにレコードを更新し、sql **SELECT** ステートメントはレコードを返します。 詳細については、DAO ヘルプの「ReturnsRecords プロパティ」を参照してください。

*m_strSQL*<br/>
Querydef オブジェクトによって実行されるクエリを定義する SQL ステートメントです。 SQL プロパティには、クエリの実行時にレコードを選択、グループ化、および順序付けする方法を決定する SQL ステートメントが含まれています。 クエリを使用して、ダイナセットまたはスナップショット型のレコードセットオブジェクトに含めるレコードを選択できます。 また、レコードを返さずにデータを変更するための一括クエリを定義することもできます。 このプロパティの値は、querydef の [GetSQL](../../mfc/reference/cdaoquerydef-class.md#getsql) メンバー関数を呼び出すことによって直接取得できます。

*m_strConnect*<br/>
パススルークエリで使用されるデータベースのソースに関する情報を提供します。 この情報は、接続文字列の形式になります。 接続文字列の詳細、およびこのプロパティの値を直接取得する方法については、「 [CDaoDatabase:: GetConnect](../../mfc/reference/cdaodatabase-class.md#getconnect) メンバー関数」を参照してください。

*m_nODBCTimeout*<br/>
ODBC データベースでクエリが実行されるときに、Microsoft Jet データベースエンジンがタイムアウトエラーが発生するまでに待機する秒数。 Microsoft SQL Server などの ODBC データベースを使用している場合、ネットワークトラフィックまたは ODBC サーバーの使用量が多いために遅延が発生する可能性があります。 無制限に待機するのではなく、Microsoft Jet エンジンがエラーを生成するまでの待機時間を指定できます。 既定のタイムアウト値は60秒です。 このプロパティの値は、querydef の [Getodbctimeout](../../mfc/reference/cdaoquerydef-class.md#getodbctimeout) メンバー関数を呼び出すことによって直接取得できます。 詳細については、DAO ヘルプの「ODBCTimeout プロパティ」を参照してください。

## <a name="remarks"></a>解説

クエリ定義は、 [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md)クラスのオブジェクトです。 上記の Primary、Secondary、および All への参照は、クラスの [Getqueryていぎ fo](../../mfc/reference/cdaodatabase-class.md#getquerydefinfo) メンバー関数によって情報がどのように返されるかを示して `CDaoDatabase` います。

[CDaoDatabase:: Getqueryていぎ fo](../../mfc/reference/cdaodatabase-class.md#getquerydefinfo)メンバー関数によって取得された情報は、構造体に格納され `CDaoQueryDefInfo` ます。 `GetQueryDefInfo`クエリ定義オブジェクトが格納されている、のデータベースオブジェクトに対してを呼び出します。 `CDaoQueryDefInfo` は、 `Dump` デバッグビルドでメンバー関数も定義します。 を使用すると、 `Dump` オブジェクトの内容をダンプでき `CDaoQueryDefInfo` ます。 クラスには、 `CDaoDatabase` オブジェクトで返されるすべてのプロパティに直接アクセスするためのメンバー関数も用意されているので `CDaoQueryDefInfo` 、を呼び出す必要はほとんどあり `GetQueryDefInfo` ません。

新しいフィールドまたはパラメーターオブジェクトを querydef オブジェクトのフィールドまたはパラメーターのコレクションに追加すると、基になるデータベースが新しいオブジェクトに対して指定されたデータ型をサポートしていない場合に、例外がスローされます。

日付と時刻の設定は、クエリが作成されたコンピューター、または最後に更新されたコンピューターから派生します。 マルチユーザー環境では、ユーザーは **net time** コマンドを使用してファイルサーバーからこれらの設定を直接取得し、DateCreated および lastupdated プロパティの設定の不一致を回避する必要があります。

## <a name="requirements"></a>要件

**ヘッダー:** afxdao

## <a name="see-also"></a>関連項目

[構造体、スタイル、コールバック、およびメッセージマップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CDaoQueryDef クラス](../../mfc/reference/cdaoquerydef-class.md)<br/>
[CDaoDatabase クラス](../../mfc/reference/cdaodatabase-class.md)
