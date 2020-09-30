---
title: 行セットでの複数アクセサーの使用
ms.date: 10/24/2018
helpviewer_keywords:
- BEGIN_ACCESSOR macro
- BEGIN_ACCESSOR macro, multiple accessors
- rowsets [C++], multiple accessors
- accessors [C++], rowsets
ms.assetid: 80d4dc5d-4940-4a28-a4ee-d8602f71d2a6
ms.openlocfilehash: 48772539b4dda9262a244506a36932d1e752949e
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/29/2020
ms.locfileid: "91509402"
---
# <a name="using-multiple-accessors-on-a-rowset"></a>行セットでの複数アクセサーの使用

複数のアクセサーを使用する必要がある基本的なシナリオには、次の3つがあります。

- **複数の読み取り/書き込み行セット。** このシナリオでは、主キーを持つテーブルがあります。 主キーを含む、行内のすべての列を読み取ることができるようにする場合。 また、主キー以外のすべての列にデータを書き込むこともできます (主キー列に書き込むことはできません)。 この場合は、次の2つのアクセサーを設定します。

  - アクセサー0にはすべての列が含まれます。

  - アクセサー1には、主キー以外のすべての列が含まれます。

- **パフォーマンス。** このシナリオでは、1つまたは複数の列に大量のデータ (グラフィックス、サウンド、ビデオファイルなど) が含まれています。 行に移動するたびに、大規模なデータファイルを含む列を取得するのは望ましくありません。これにより、アプリケーションのパフォーマンスが低下する可能性があるためです。

  1つ目のアクセサーに大規模なデータを含むすべての列を格納する個別のアクセサーを設定し、これらの列からデータを自動的に取得することができます。最初のアクセサーは、自動アクセサーです。 2番目のアクセサーは、大きなデータを保持している列のみを取得しますが、この列からデータを自動的に取得することはありません。 他のメソッドを使用して、必要に応じて大規模なデータを更新またはフェッチすることができます。

  - アクセサー0は自動アクセサーです。このメソッドは、大きなデータを含むすべての列を取得します。

  - アクセサー1は自動アクセサーではありません。大きなデータを含む列を取得します。

  アクセサーが自動アクセサーであるかどうかを指定するには、auto 引数を使用します。

- **複数の ISequentialStream 列。** このシナリオでは、データを保持している列が複数 `ISequentialStream` あります。 ただし、各アクセサーは1つのデータストリームに制限され `ISequentialStream` ます。 この問題を解決するには、それぞれが1つのポインターを持つ複数のアクセサーを設定し `ISequentialStream` ます。

通常は、 [BEGIN_ACCESSOR](./macros-and-global-functions-for-ole-db-consumer-templates.md#begin_accessor) と [END_ACCESSOR](./macros-and-global-functions-for-ole-db-consumer-templates.md#end_accessor) マクロを使用してアクセサーを作成します。 [Db_accessor](../../windows/attributes/db-accessor.md)属性を使用することもできます。 (アクセサーの詳細については、「 [ユーザーレコード](../../data/oledb/user-records.md)」を参照してください)。マクロまたは属性は、アクセサーが自動アクセサーと非自動アクセサーのどちらであるかを指定します。

- 自動アクセサーでは、、、、などのメソッドを移動 `MoveFirst` `MoveLast` し、 `MoveNext` `MovePrev` 指定されたすべての列のデータを自動的に取得します。 アクセサー0は自動アクセサーである必要があります。

- 非自動アクセサーでは、、、、などのメソッドを明示的に呼び出すまで、取得は行われません `Update` `Insert` `Fetch` `Delete` 。 上記のシナリオでは、すべての移動ですべての列を取得する必要がない場合があります。 次に示すように、1つまたは複数の列を別のアクセサーに配置し、非自動アクセサーに設定できます。

次の例では、複数のアクセサーを使用して、複数のアクセサーを使用して SQL Server pubs データベースのジョブテーブルの読み取りと書き込みを行います。 この例は、複数のアクセサーを使用する最も一般的な方法です。上記の「複数の読み取り/書き込み行セット」シナリオを参照してください。

ユーザーレコードクラスは次のとおりです。 2つのアクセサーを設定します。アクセサー0には主キー列 (ID) のみが含まれ、アクセサー1には他の列が含まれます。

```cpp
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

主要なコードは次のとおりです。 を呼び出す `MoveNext` と、アクセサー0を使用して主キー列 ID からデータが自動的に取得されます。 End 付近のメソッドでは、 `Insert` 主キー列への書き込みを避けるために、アクセサー1を使用する方法に注意してください。

```cpp
int main(int argc, char* argv[])
{
    // Initialize COM
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

[アクセサーの使用](../../data/oledb/using-accessors.md)<br/>
[ユーザーレコード](../../data/oledb/user-records.md)
