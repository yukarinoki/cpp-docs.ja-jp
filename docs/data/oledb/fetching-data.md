---
title: データのフェッチ |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- data [C++], fetching
- rowsets [C++], fetching
- fetching
- OLE DB consumer templates [C++], fetching data
ms.assetid: b07f747f-9855-4f27-a03d-b1d5b10fa284
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 1dca3cc2d51f0e165e9b17d9fe630752a427590f
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2018
ms.locfileid: "39339157"
---
# <a name="fetching-data"></a>データのフェッチ
データ ソース、セッション、および行セット オブジェクトを開いた後は、データをフェッチできます。 で使用するアクセサーの種類によっては、列をバインドする必要があります。  
  
### <a name="to-fetch-data"></a>データをフェッチするには  
  
1.  適切なを使用して行セットを開く**オープン**コマンド。  
  
2.  使用する場合`CManualAccessor`をまだ行っていない場合は、出力列をバインドします。 列をバインドするには、呼び出す`GetColumnInfo`、し、次の例に示すように、バインドでアクセサーを作成します。  
  
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
  
3.  書き込みを`while`ループを使用してデータを取得します。 ループでは、呼び出す`MoveNext`カーソルを進めるし、次の例に示すように、S_OK に対して戻り値をテストします。  
  
    ```cpp  
    while (rs.MoveNext() == S_OK)  
    {  
        // Add code to fetch data here  
        // If you are not using an auto accessor, call rs.GetData()  
    }  
    ```  
  
4.  内で、`while`ループ、アクセサーの型に従ってデータをフェッチできます。  
  
    -   使用する場合、 [CAccessor](../../data/oledb/caccessor-class.md)クラス、データ メンバーを含んでいるユーザー レコードが必要です。 次の例に示すようにそのデータ メンバーを使用してデータにアクセスすることができます。  
  
        ```cpp  
        while (rs.MoveNext() == S_OK)  
        {  
            // Use the data members directly. In this case, m_nFooID  
            // is declared in a user record that derives from  
            // CAccessor  
            wsprintf_s("%d", rs.m_nFooID);   
        }  
        ```  
  
    -   使用する場合、`CDynamicAccessor`または`CDynamicParameterAccessor`クラスにアクセスする関数を使用してデータをフェッチできます`GetValue`と`GetColumn`次の例のようにします。 使用するデータの種類を決定する場合を使用して、`GetType`します。  
  
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
  
    -   使用する場合`CManualAccessor`、独自のデータ メンバーを指定、自分でバインドおよび次の例に示すように、直接アクセスする必要があります。  
  
        ```cpp  
        while (rs.MoveNext() == S_OK)  
        {  
            // Use the data members you specified in the calls to  
            // AddBindEntry.  
  
            wsprintf_s("%s", szFoo);  
        }  
        ```  
  
## <a name="see-also"></a>関連項目  
 [OLE DB コンシューマー テンプレートの操作](../../data/oledb/working-with-ole-db-consumer-templates.md)