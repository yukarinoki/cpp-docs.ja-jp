---
title: データのフェッチ
ms.date: 10/19/2018
helpviewer_keywords:
- data [C++], fetching
- rowsets [C++], fetching
- fetching
- OLE DB consumer templates [C++], fetching data
ms.assetid: b07f747f-9855-4f27-a03d-b1d5b10fa284
ms.openlocfilehash: 919eb059f5d3f29d491bf7a6598b0c77163bd783
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87184645"
---
# <a name="fetching-data"></a>データのフェッチ

データソース、セッション、および行セットオブジェクトを開いた後、データをフェッチできます。 使用しているアクセサーの種類によっては、列のバインドが必要になる場合があります。

## <a name="to-fetch-data"></a>データをフェッチするには

1. 適切な**open**コマンドを使用して、行セットを開きます。

1. を使用している場合は `CManualAccessor` 、出力列をバインドします (まだ作成していない場合)。 次の例は、 [DBViewer](https://github.com/Microsoft/VCSamples/tree/master/VC2008Samples/ATL/OLEDB/Consumer/dbviewer)サンプルから抜粋したものです。 列をバインドするには、を呼び出し、 `GetColumnInfo` 次の例に示すように、バインディングを使用してアクセサーを作成します。

    ```cpp
    // From the DBViewer Sample CDBTreeView::OnQueryEdit
    // Get the column information
    ULONG ulColumns       = 0;
    DBCOLUMNINFO* pColumnInfo  = NULL;
    LPOLESTR pStrings      = NULL;
    if (rs.GetColumnInfo(&ulColumns, &pColumnInfo, &pStrings) != S_OK)
        ThrowMyOLEDBException(rs.m_pRowset, IID_IColumnsInfo);
    struct MYBIND* pBind = new MYBIND[ulColumns];
    rs.CreateAccessor(ulColumns, &pBind[0], sizeof(MYBIND)*ulColumns);
    for (ULONG l=0; l<ulColumns; l++)
    rs.AddBindEntry(l+1, DBTYPE_STR, sizeof(TCHAR)*40, &pBind[l].szValue, NULL, &pBind[l].dwStatus);
    rs.Bind();
    ```

1. ループを記述し **`while`** てデータを取得します。 次の例に示すように、ループ内でを呼び出して `MoveNext` カーソルを進め、戻り値を S_OK に対してテストします。

    ```cpp
    while (rs.MoveNext() == S_OK)
    {
        // Add code to fetch data here
        // If you are not using an auto accessor, call rs.GetData()
    }
    ```

1. ループ内では、 **`while`** アクセサーの型に応じてデータをフェッチできます。

   - [CAccessor](../../data/oledb/caccessor-class.md)クラスを使用する場合は、データメンバーを含むユーザーレコードが必要です。 次の例に示すように、これらのデータメンバーを使用してデータにアクセスできます。

        ```cpp
        while (rs.MoveNext() == S_OK)
        {
            // Use the data members directly. In this case, m_nFooID
            // is declared in a user record that derives from
            // CAccessor
            wsprintf_s("%d", rs.m_nFooID);
        }
        ```

   - クラスまたはクラスを使用する場合は、 `CDynamicAccessor` `CDynamicParameterAccessor` 次の `GetValue` 例に示すように、アクセスする関数とを使用してデータをフェッチでき `GetColumn` ます。 使用しているデータの種類を確認する場合は、を使用 `GetType` します。

        ```cpp
        while (rs.MoveNext() == S_OK)
        {
            // Use the dynamic accessor functions to retrieve your data.

            ULONG ulColumns = rs.GetColumnCount();
            for (ULONG i=0; i<ulColumns; i++)
            {
                rs.GetValue(i);
            }
        }
        ```

   - を使用する場合は `CManualAccessor` 、次の例に示すように、独自のデータメンバーを指定し、それらを自分でバインドして、直接アクセスする必要があります。

        ```cpp
        while (rs.MoveNext() == S_OK)
        {
            // Use the data members you specified in the calls to
            // AddBindEntry.

            wsprintf_s("%s", szFoo);
        }
        ```

## <a name="see-also"></a>関連項目

[OLE DB コンシューマーテンプレートの使用](../../data/oledb/working-with-ole-db-consumer-templates.md)
