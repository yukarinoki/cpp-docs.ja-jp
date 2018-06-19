---
title: データのフェッチ |Microsoft ドキュメント
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
ms.openlocfilehash: ab03da7c303552a715c6766af7829e74025866ed
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33101202"
---
# <a name="fetching-data"></a>データのフェッチ
データ ソース、セッション、および行セット オブジェクトを開いた後は、データをフェッチできます。 で使用するアクセサーの種類によっては、列をバインドする必要があります。  
  
### <a name="to-fetch-data"></a>データをフェッチするには  
  
1.  使用して、適切な行セットを開く**開く**コマンド。  
  
2.  使用している場合`CManualAccessor`をまだ行っていない場合は、出力列をバインドします。 列をバインドするには、呼び出す`GetColumnInfo`、し、次の例で示すように、バインディングで、アクセサーを作成します。  
  
    ```  
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
  
3.  書き込み、`while`ループを使用してデータを取得します。 ループで呼び出す`MoveNext`カーソルを進めるし、次の例のように、S_OK に対して戻り値をテストします。  
  
    ```  
    while (rs.MoveNext() == S_OK)  
    {  
        // Add code to fetch data here  
        // If you are not using an auto accessor, call rs.GetData()  
    }  
    ```  
  
4.  内で、`while`ループ、アクセサーの種類に従ってデータをフェッチすることができます。  
  
    -   使用する場合、 [CAccessor](../../data/oledb/caccessor-class.md)クラス、データ メンバーを含んでいるユーザー レコードを持つ必要があります。 次の例で示すように、これらのデータ メンバーを使用して、データにアクセスできます。  
  
        ```  
        while (rs.MoveNext() == S_OK)  
        {  
            // Use the data members directly. In this case, m_nFooID  
            // is declared in a user record that derives from  
            // CAccessor  
            wsprintf_s("%d", rs.m_nFooID);   
        }  
        ```  
  
    -   使用する場合、`CDynamicAccessor`または`CDynamicParameterAccessor`クラスにアクセスする関数を使用してデータをフェッチできます`GetValue`と`GetColumn`次の例で示すように、します。 使用しているデータの種類を決定する場合は、使用して`GetType`です。  
  
        ```  
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
  
    -   使用する場合`CManualAccessor`、独自のデータ メンバーを指定、自分でバインドおよび次の例で示すように直接アクセスする必要があります。  
  
        ```  
        while (rs.MoveNext() == S_OK)  
        {  
            // Use the data members you specified in the calls to  
            // AddBindEntry.  
  
            wsprintf_s("%s", szFoo);  
        }  
        ```  
  
## <a name="see-also"></a>関連項目  
 [OLE DB コンシューマー テンプレートの操作](../../data/oledb/working-with-ole-db-consumer-templates.md)