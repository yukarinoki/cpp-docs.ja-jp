---
title: 行セットでの複数アクセサーの使用 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- BEGIN_ACCESSOR macro
- BEGIN_ACCESSOR macro, multiple accessors
- rowsets [C++], multiple accessors
- accessors [C++], rowsets
ms.assetid: 80d4dc5d-4940-4a28-a4ee-d8602f71d2a6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: a30108ec344091631094cd55f6a3bd3f0f4a4a54
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="using-multiple-accessors-on-a-rowset"></a>行セットでの複数アクセサーの使用
複数のアクセサーを使用する必要がある 3 つの基本的なシナリオはあります。  
  
-   **複数の読み取り/書き込み行セット。** このシナリオでは、主キーを持つテーブルがあります。 主キーを含め、行内のすべての列を読み取ることができるします。 (主キー列に記述することはできません) ために、主キーを除くすべての列にデータを書き込めるようにするもします。 この場合、2 つのアクセサーを設定します。  
  
    -   アクセサー 0 には、すべての列が含まれています。  
  
    -   アクセサー 1 には、主キーを除くすべての列が含まれています。  
  
-   **パフォーマンス。** このシナリオでは、1 つまたは複数の列には、大量データ、たとえば、グラフィック、サウンド、またはビデオ ファイルにはが含まれます。 行に移動するたびにおそらくたくない大量のデータ ファイルのある列を取得する行うのではパフォーマンスが低下するアプリケーションのためです。  
  
     最初のアクセサーには、大量のデータを 1 つを除くすべての列が含まれています。 し、これらの列からデータを自動的に取得別のアクセサーを設定することができます。これは、自動アクセサーです。 2 番目のアクセサーには、大量のデータを含む列だけが取得されますが、そのデータが取得されないこの列から自動的にします。 その他のメソッドを更新またはオンデマンドで大容量のデータをフェッチすることができます。  
  
    -   アクセサー 0 は自動アクセサーです。大きなデータの 1 つを除くすべての列を取得します。  
  
    -   1 はない自動アクセサーです。大規模なデータを含む列を取得します。  
  
     アクセサーが自動アクセサーであるかどうかを指定するのにには、自動引数を使用します。  
  
-   **複数の ISequentialStream 列です。** このシナリオである 1 つ以上の列を含む`ISequentialStream`データ。 ただし、各アクセサーはいずれかに限定`ISequentialStream`データ ストリーム。 この問題を解決する設定、複数のアクセサーを 1 つを含む各`ISequentialStream`ポインター。  
  
 通常使用するアクセサーを作成する、 [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md)と[END_ACCESSOR](../../data/oledb/end-accessor.md)マクロです。 使用することも、 [db_accessor](../../windows/db-accessor.md)属性。 (アクセサーは詳細に説明[ユーザー レコード](../../data/oledb/user-records.md))。マクロまたは属性は、アクセサーは、自動または非自動アクセサーであるかどうかを指定します。  
  
-   移動方法など、自動のアクセサーで**MoveFirst**、 `MoveLast`、 `MoveNext`、および`MovePrev`列を自動的に指定されたすべてのデータを取得します。 アクセサー 0 は、自動のアクセサーを指定する必要があります。  
  
-   非自動アクセサーで明示的にメソッドを呼び出すようまで取得は発生しません**更新**、**挿入**、**フェッチ**、または**の削除**. 上記のシナリオで、移動するたびにすべての列を取得することがないできます。 別のアクセサーに 1 つまたは複数の列を配置し、されていること、非自動アクセサーでは、次のようにできます。  
  
 次の例では、読み取りと書き込みの複数のアクセサーを使用して、SQL Server pubs データベース ジョブ テーブルに複数のアクセサーを使用します。 これは、複数のアクセサーの最も一般的な使用上記の「複数の読み取り/書き込み行セット」シナリオを参照してください。  
  
 ユーザー レコード クラスは次のとおりです。 2 つのアクセサーを設定する: アクセサー 0 主キー列 (ID) だけを含み、アクセサー 1 には、他の列が含まれています。  
  
```  
class CJobs  
{  
public:  
    enum {  
        sizeOfDescription = 51  
    };  
  
    short nID;  
    char szDescription[ sizeOfDescription ];  
    short nMinLvl;  
    short nMaxLvl;  
  
    DWORD dwID;  
    DWORD dwDescription;  
    DWORD dwMinLvl;  
    DWORD dwMaxLvl;  
  
BEGIN_ACCESSOR_MAP(CJobs, 2)  
    // Accessor 0 is the automatic accessor  
    BEGIN_ACCESSOR(0, true)  
        COLUMN_ENTRY_STATUS(1, nID, dwID)  
    END_ACCESSOR()  
    // Accessor 1 is the non-automatic accessor  
    BEGIN_ACCESSOR(1, true)  
        COLUMN_ENTRY_STATUS(2, szDescription, dwDescription)  
        COLUMN_ENTRY_STATUS(3, nMinLvl, dwMinLvl)  
        COLUMN_ENTRY_STATUS(4, nMaxLvl, dwMaxLvl)  
    END_ACCESSOR()  
END_ACCESSOR_MAP()  
};  
```  
  
 主要なコードは次のとおりです。 呼び出す`MoveNext`アクセサー 0 を使用して主キー列の ID からデータを自動的に取得します。 注方法、**挿入**使用アクセサー 1 には、主キー列に書き込まれないように近くメソッドです。  
  
```  
int main(int argc, char* argv[])  
{  
    // Initalize COM  
    ::CoInitialize(NULL);  
  
    // Create instances of the data source and session  
    CDataSource source;  
    CSession session;  
    HRESULT hr = S_OK;  
  
    // Set initialization properties  
    CDBPropSet dbinit(DBPROPSET_DBINIT);  
    dbinit.AddProperty(DBPROP_AUTH_USERID, OLESTR("my_user_id"));  
    dbinit.AddProperty(DBPROP_INIT_CATALOG, OLESTR("pubs"));  
    dbinit.AddProperty(DBPROP_INIT_DATASOURCE, OLESTR("(local)"));  
  
    hr = source.Open("SQLOLEDB.1", &dbinit);  
    if (hr == S_OK)  
    {  
        hr = session.Open(source);  
        if (hr == S_OK)  
        {  
            // Ready to fetch/access data  
            CTable<CAccessor<CJobs>> jobs;  
  
            // Set properties for making the rowset a read/write cursor  
            CDBPropSet dbRowset(DBPROPSET_ROWSET);  
            dbRowset.AddProperty(DBPROP_CANFETCHBACKWARDS, true);  
            dbRowset.AddProperty(DBPROP_CANSCROLLBACKWARDS, true);  
            dbRowset.AddProperty(DBPROP_IRowsetChange, true);  
            dbRowset.AddProperty(DBPROP_UPDATABILITY,  
                DBPROPVAL_UP_INSERT | DBPROPVAL_UP_CHANGE |  
                DBPROPVAL_UP_DELETE);  
  
            hr = jobs.Open(session, "jobs", &dbRowset);  
            if (hr == S_OK)  
            {  
                // Calling MoveNext automatically retrieves ID  
                // (using accessor 0)  
                while(jobs.MoveNext() == S_OK)  
                   printf_s("Description = %s\n", jobs.szDescription);  
  
                hr = jobs.MoveFirst();  
                if (hr == S_OK)  
                {  
                    jobs.nID = 25;  
                    strcpy_s(&jobs.szDescription[0],  
                             jobs.sizeOfDescription,  
                             "Developer");  
                    jobs.nMinLvl = 10;  
                    jobs.nMaxLvl = 20;  
  
                    jobs.dwDescription = DBSTATUS_S_OK;  
                    jobs.dwID = DBSTATUS_S_OK;  
                    jobs.dwMaxLvl = DBSTATUS_S_OK;  
                    jobs.dwMinLvl = DBSTATUS_S_OK;  
  
                    // Insert method uses accessor 1  
                    // (to avoid writing to the primary key column)  
                    hr = jobs.Insert(1);     
                }  
                jobs.Close();  
            }  
            session.Close();  
        }  
        source.Close();  
    }  
  
    // Uninitialize COM  
    ::CoUninitialize();  
    return 0;  
}  
```  
  
## <a name="see-also"></a>関連項目  
 [アクセサーの使用](../../data/oledb/using-accessors.md)   
 [ユーザー レコード](../../data/oledb/user-records.md)