---
title: パラメーター クエリの実行
ms.date: 10/19/2018
helpviewer_keywords:
- parameter queries, running using CCommand class
ms.assetid: aedb0fce-52a4-4c97-a5c9-b2114be6c3b0
ms.openlocfilehash: bb8b879d08595150b2db61f4840131e3ccc500a2
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80210172"
---
# <a name="issuing-a-parameterized-query"></a>パラメーター クエリの実行

次の例では、Microsoft Access データベースのテーブルから age フィールド (30 を超える) のレコードを取得する単純なパラメーター化クエリを発行します。 パラメーターをサポートするには、ユーザーレコードにマップが追加されている必要があります。 次のコードでは、ATL プロジェクトで、[単純な行セットを走査する](../../data/oledb/traversing-a-simple-rowset.md)前の例で使用した `CTable` クラスではなく、`CCommand` クラスを使用しています。

```cpp
#include <atldbcli.h>
#include <iostream>

using namespace std;

int main()
{
    CDataSource connection;
    CSession session;
    CCommand<CAccessor<CArtists>> artists;
    LPCSTR clsid; // Initialize CLSID_MSDASQL here
    LPCTSTR pName = L"NWind";

    // Open the connection, session, and table, specifying authentication
    // using Windows NT integrated security. Hard-coding a password is a major
    // security weakness.
    connection.Open(clsid, pName, NULL, NULL, DBPROP_AUTH_INTEGRATED);

    session.Open(connection);

    // Set the parameter for the query
    artists.m_nAge = 30;
    artists.Open(session, "select * from artists where age > ?");

    // Get data from the rowset
    while (artists.MoveNext() == S_OK)
    {
        cout << artists.m_szFirstName;
        cout << artists.m_szLastName;
    }

    return 0;
}
```

ユーザーレコード `CArtists`は、次の例のようになります。

```cpp
class CArtists
{
public:
// Data Elements
   CHAR m_szFirstName[20];
   CHAR m_szLastName[30];
   short m_nAge;

// Column binding map
BEGIN_COLUMN_MAP(CArtists)
   COLUMN_ENTRY(1, m_szFirstName)
   COLUMN_ENTRY(2, m_szLastName)
   COLUMN_ENTRY(3, m_nAge)
END_COLUMN_MAP()

// Parameter binding map
BEGIN_PARAM_MAP(CArtists)
   SET_PARAM_TYPE(DBPARAMIO_INPUT)
   COLUMN_ENTRY(1, m_nAge)
END_PARAM_MAP()
};
```

## <a name="see-also"></a>参照

[OLE DB コンシューマー テンプレートの操作](../../data/oledb/working-with-ole-db-consumer-templates.md)
