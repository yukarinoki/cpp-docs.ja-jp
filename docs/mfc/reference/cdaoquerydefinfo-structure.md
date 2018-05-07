---
title: CDaoQueryDefInfo 構造体 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CDaoQueryDefInfo
dev_langs:
- C++
helpviewer_keywords:
- DAO (Data Access Objects), QueryDefs collection
- CDaoQueryDefInfo structure [MFC]
ms.assetid: e20837dc-e78d-4171-a195-1b4075fb5d2a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e0b3e5834aa8b338448c2024603783cedb6f6cae
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="cdaoquerydefinfo-structure"></a>CDaoQueryDefInfo 構造体
`CDaoQueryDefInfo`構造体には、データ アクセス オブジェクト (DAO) に対して定義されているクエリ定義のオブジェクトに関する情報が含まれています。  
  
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
 `m_strName`  
 クエリ定義オブジェクトの一意名です。 詳細については、DAO ヘルプの「名前プロパティ」を参照してください。 呼び出す[CDaoQueryDef::GetName](../../mfc/reference/cdaoquerydef-class.md#getname)を直接このプロパティを取得します。  
  
 `m_nType`  
 クエリ定義オブジェクトの操作の型を示す値です。 値は次のいずれかになります。  
  
- **dbQSelect**選択、クエリを作成します。  
  
- **dbQAction**アクション: クエリは、移動、またはデータの変更レコードは返されません。  
  
- **dbQCrosstab**クロス集計: クエリでは、スプレッドシートのような形式でデータを返します。  
  
- **dbQDelete**削除-クエリが指定された行のセットを削除します。  
  
- **dbQUpdate**更新など、クエリが一連のレコードを変更します。  
  
- **dbQAppend** Append: クエリは、テーブルまたはクエリの末尾に新しいレコードを追加します。  
  
- **dbQMakeTable**テーブルの作成、クエリでは、レコード セットから新しいテーブルを作成します。  
  
- **dbQDDL**データ定義、クエリがテーブルまたはその一部の構造に影響します。  
  
- **dbQSQLPassThrough**パススルー — SQL ステートメントは、中間処理されず、データベース バックエンドに直接渡されます。  
  
- **dbQSetOperation**共用体: クエリは、2 つの指定したすべてのレコードからデータを含むスナップショット タイプのレコード セット オブジェクトを作成または重複するレコードと他のテーブルを削除します。 キーワードを追加含めるには、重複、**すべて**クエリ定義の SQL ステートメントにします。  
  
- **dbQSPTBulk**併用**dbQSQLPassThrough**レコードを返さないクエリを指定します。  
  
> [!NOTE]
>  SQL のパススルー クエリを作成するを設定しない、 **dbQSQLPassThrough**定数。 これは自動的に設定 Microsoft Jet データベース エンジンによってクエリ定義オブジェクトを作成し、接続プロパティを設定します。  
  
 詳細については、DAO ヘルプの「型プロパティ」を参照してください。  
  
 `m_dateCreated`  
 日付とクエリ定義が作成された時刻。 クエリ定義が作成された日付を直接取得する呼び出し、 [GetDateCreated](../../mfc/reference/cdaotabledef-class.md#getdatecreated)のメンバー関数、`CDaoTableDef`テーブルに関連付けられているオブジェクト。 詳細については、下のコメントを参照してください。 DAO のヘルプでは、「作成日時、LastUpdated プロパティ」トピックを参照してください。  
  
 `m_dateLastUpdated`  
 日付とクエリ定義に加えられた最近の変更時刻。 テーブルの最終更新日を直接取得する呼び出し、 [GetDateLastUpdated](../../mfc/reference/cdaoquerydef-class.md#getdatelastupdated)クエリ定義のメンバー関数。 詳細については、下のコメントを参照してください。 DAO ヘルプの「「DateCreated LastUpdated プロパティ」を参照してください。  
  
 `m_bUpdatable`  
 変更をクエリ定義オブジェクトにできるかどうかを示します。 このプロパティは、する場合**TRUE**、クエリ定義が更新可能な場合はありません。 更新可能では、クエリ定義オブジェクトのクエリ定義を変更することができますを意味します。 クエリ定義オブジェクトの更新可能なプロパティに設定**TRUE**かどうか、クエリ定義を更新できる、結果のレコード セットは更新可能でない場合でもです。 このプロパティを直接取得するを呼び出すクエリ定義の[CanUpdate](../../mfc/reference/cdaoquerydef-class.md#canupdate)メンバー関数。 詳細については、DAO ヘルプの「更新可能なプロパティ」を参照してください。  
  
 *m_bReturnsRecords*  
 外部データベースに SQL パススルー クエリがレコードを返すかどうかを示します。 このプロパティは、する場合**TRUE**レコードが返されます。 このプロパティを直接取得するには、する[CDaoQueryDef::GetReturnsRecords](../../mfc/reference/cdaoquerydef-class.md#getreturnsrecords)です。 外部データベースへのすべての SQL パススルー クエリは、レコードを返します。 たとえば、SQL**更新**ステートメントは、SQL の中に、レコードを返さずにレコードを更新**選択**ステートメントはレコードが返されます。 詳細については、DAO のヘルプで「レコード表示プロパティ」を参照してください。  
  
 *m_strSQL*  
 クエリ定義オブジェクトによって実行されるクエリを定義する SQL ステートメント。 SQL プロパティには、どのレコードが選択、グループ化、順序付けられたクエリを実行するときに決定する SQL ステートメントが含まれています。 ダイナセットまたはスナップショット タイプのレコード セット オブジェクトに含めるレコードを選択するのにクエリを使用することができます。 データを変更するレコードを返さずに一括クエリを定義することもできます。 このプロパティの値を取得するには、クエリの定義を呼び出すことによって直接[GetSQL](../../mfc/reference/cdaoquerydef-class.md#getsql)メンバー関数。  
  
 `m_strConnect`  
 パススルー クエリで使用されるデータベースのソースに関する情報を提供します。 この情報は接続文字列の形式になります。 詳細については、文字列を約接続し、このプロパティの値を直接取得する方法の詳細については、次を参照してください。、 [CDaoDatabase::GetConnect](../../mfc/reference/cdaodatabase-class.md#getconnect)メンバー関数。  
  
 *m_nODBCTimeout*  
 Microsoft Jet データベース エンジンがタイムアウト エラーの前に待機する秒数は、ODBC データベースに、クエリの実行時に発生します。 Microsoft SQL Server などの ODBC データベースを使用しているときに遅れることがあります、ODBC のサーバーのネットワーク トラフィックや使用しているためです。 無限に待機するのではなく Microsoft Jet エンジンがエラーを生成するまでに待機する時間を指定することができます。 既定のタイムアウト値は、60 秒です。 このプロパティの値を取得するには、クエリの定義を呼び出すことによって直接[GetODBCTimeout](../../mfc/reference/cdaoquerydef-class.md#getodbctimeout)メンバー関数。 詳細については、DAO ヘルプの「補足プロパティ」を参照してください。  
  
## <a name="remarks"></a>コメント  
 クエリ定義がクラスのオブジェクト[CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md)です。 プライマリ、セカンダリ、および上記のすべての参照は、情報がによって返される方法を示します、 [GetQueryDefInfo](../../mfc/reference/cdaodatabase-class.md#getquerydefinfo)クラスのメンバー関数`CDaoDatabase`です。  
  
 によって取得される情報、 [CDaoDatabase::GetQueryDefInfo](../../mfc/reference/cdaodatabase-class.md#getquerydefinfo)メンバー関数は、`CDaoQueryDefInfo`構造体。 呼び出す`GetQueryDefInfo`QueryDefs コレクションでのクエリ定義オブジェクトが格納されているデータベース オブジェクト用です。 `CDaoQueryDefInfo` 定義、`Dump`デバッグでメンバー関数を作成します。 使用することができます`Dump`の内容をダンプする`CDaoQueryDefInfo`オブジェクト。 クラス`CDaoDatabase`もすべてのプロパティで返されるに直接アクセスするためのメンバー関数を提供、`CDaoQueryDefInfo`オブジェクトを呼び出す必要があります頻度の低い可能性がありますので`GetQueryDefInfo`です。  
  
 クエリ定義オブジェクトのフィールドまたはパラメーターのコレクションに新しいフィールドまたはパラメーター オブジェクトを追加するときに、基になるデータベースが新しいオブジェクトの指定されたデータ型をサポートしていない場合、例外がスローされます。  
  
 日付と時刻の設定は、クエリ定義が作成または最後に更新されたコンピューターから派生します。 マルチ ユーザー環境で、ファイル サーバーを使用して、直接からのこれらの設定を取得する必要があります、**時の net** DateCreated および LastUpdated プロパティの設定の不一致を避けるためコマンド。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxdao.h  
  
## <a name="see-also"></a>関連項目  
 [構造体、スタイル、コールバック、およびメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDaoQueryDef クラス](../../mfc/reference/cdaoquerydef-class.md)   
 [CDaoDatabase クラス](../../mfc/reference/cdaodatabase-class.md)
