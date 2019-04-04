---
title: ウィザードで生成されたアクセサーのフィールド ステータスのデータ メンバー
ms.date: 10/24/2018
helpviewer_keywords:
- OLE DB consumer templates, field status
- field status in OLE DB templates
ms.assetid: 66e4e223-c60c-471e-860d-d23abcdfe371
ms.openlocfilehash: 46cf285e07bffe178874546d13d196b5165cb28b
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/10/2018
ms.locfileid: "51524359"
---
# <a name="field-status-data-members-in-wizard-generated-accessors"></a>ウィザードで生成されたアクセサーのフィールド ステータスのデータ メンバー

使用すると、 **ATL OLE DB コンシューマー ウィザード**コンシューマーを作成するには、ウィザードでは、列のマップで指定したフィールドごとにユーザー レコード クラスのデータ メンバーを生成します。 各データ メンバーが型の`DWORD`該当するフィールドに対応する状態値が含まれています。

たとえば、データ メンバー *m_OwnerID*、ウィザードは、フィールドの状態の追加のデータ メンバーを生成 (*dwOwnerIDStatus*)、フィールド長のもう 1 つ (*dwOwnerIDLength*). COLUMN_ENTRY_LENGTH_STATUS エントリを含む列のマップも生成されます。

これは、次のコードに示します。

```cpp
class CAuthorsAccessor
{
public:
   LONG m_AuID;
   TCHAR m_Author[53];
   LONG m_YearBorn;

   DBSTATUS m_dwAuIDStatus;
   DBSTATUS m_dwAuthorStatus;
   DBSTATUS m_dwYearBornStatus;

   DBLENGTH m_dwAuIDLength;
   DBLENGTH m_dwAuthorLength;
   DBLENGTH m_dwYearBornLength;

    DEFINE_COMMAND_EX(CAuthorsAccessor, L" \
    SELECT \
        AuID, \
        Author, \
        YearBorn \
        FROM dbo.Authors")

    BEGIN_COLUMN_MAP(CAuthorsAccessor)
       COLUMN_ENTRY_LENGTH_STATUS(1, m_AuID, dwAuIDLength, dwAuIDStatus)
       COLUMN_ENTRY_LENGTH_STATUS(2, m_Author, dwAuthorLength, dwAuthorStatus)
       COLUMN_ENTRY_LENGTH_STATUS(3, m_YearBorn, dwYearBornLength, dwYearBornStatus)
    END_COLUMN_MAP()
...
```

> [!NOTE]
> ユーザー レコード クラスを変更するか、独自のコンシューマーを作成する場合、データ変数は、ステータス変数と長さ変数よりも前に記述する必要があります。

状態値は、デバッグ目的で使用できます。 コードを生成している場合、 **ATL OLE DB コンシューマー ウィザード**コンパイル エラーが生成されますなど DB_S_ERRORSOCCURRED または DB_E_ERRORSOCCURRED、する必要があります最初を見てフィールド ステータス データ メンバーの現在の値。 0 以外の値が指定されている問題のある列に対応しています。

特定のフィールドに NULL 値を設定するのに状態の値を使用することもできます。 これにより、フィールドの値を 0 ではなく、NULL として区別する場合に役立ちます。 NULL が有効な値、または特殊な値かどうかを判断し、アプリケーションが処理する方法を決定する責任です。 OLE DB は、ジェネリック、NULL 値を指定する適切な手段として、DBSTATUS_S_ISNULL を定義します。 コンシューマーは、データを読み取るし、値が null、status フィールドは、DBSTATUS_S_ISNULL に設定されます。 コンシューマーは、NULL 値を設定する場合、コンシューマーは、プロバイダーを呼び出す前に DBSTATUS_S_ISNULL にステータス値を設定します。

次に、Oledb.h と DBSTATUSENUM の検索を開きます。 DBSTATUSENUM 列挙値に対して 0 以外の状態を表す数値を適合できます。 列挙型の名前を参照してください、何が問題を通知するだけで十分でない場合、**状態**でトピック、**データ値のバインド**のセクション、 [OLE DB プログラマ ガイド](/sql/connect/oledb/ole-db/oledb-driver-for-sql-server-programming)します。 このトピックには、作業またはデータを設定するときに使用される状態値のテーブルが含まれています。 長さの値については、、**長さ**内の同じセクションのトピックを参照してください。

## <a name="retrieving-the-length-or-status-of-a-column"></a>長さまたは列のステータスを取得します。

可変長列の長さ、または (たとえば、DBSTATUS_S_ISNULL の確認) を列のステータスを取得できます。

- 長さを取得するには、COLUMN_ENTRY_LENGTH マクロを使用します。

- 状態を取得するには、COLUMN_ENTRY_STATUS マクロを使用します。

- 両方を取得するには、ように、COLUMN_ENTRY_LENGTH_STATUS を使用します。

    ```cpp
    class CProducts
    {
    public:
       char      szName[40];
       long      nNameLength;
       DBSTATUS   nNameStatus;

    BEGIN_COLUMN_MAP(CProducts)
    // Bind the column to CProducts.m_ProductName.
    // nOrdinal is zero-based, so the column number of m_ProductName is 1.
       COLUMN_ENTRY_LENGTH_STATUS(1, szName, nNameLength, nNameStatus)
    END_COLUMN_MAP()
    };
    ```

- ように、長さや状態を次に、アクセスします。

    ```cpp
    CTable<CAccessor<CProducts >> product;
    CSession session;

    product.Open(session, "Product");

    while (product.MoveNext() == S_OK)
    {
       // Check the product name isn't NULL before tracing it
       if (product.nNameStatus == DBSTATUS_S_OK)
          ATLTRACE("%s is %d characters\n", product.szName, product.nNameLength);
    }
    ```

使用すると`CDynamicAccessor`長さと状態を自動的に連結します。 長さと状態の値を取得する、`GetLength`と`GetStatus`メンバー関数。

## <a name="see-also"></a>関連項目

[OLE DB コンシューマー テンプレートの操作](../../data/oledb/working-with-ole-db-consumer-templates.md)