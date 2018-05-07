---
title: 'レコード セット: レコードの並べ替え (ODBC) |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- sorting data, recordset data
- ODBC recordsets, sorting
- recordsets, sorting
ms.assetid: b40b152e-0a91-452e-be7b-e5bc27f744c7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: ddb92016b7b911fc86f2feab27a698ce7fa55c45
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="recordset-sorting-records-odbc"></a>レコードセット: レコードの並べ替え (ODBC)
このトピックの内容は、MFC ODBC クラスに該当します。  
  
 このトピックでは、レコード セットを並べ替える方法について説明します。 並べ替えには、基になる 1 つまたは複数の列を指定することができ、昇順または降順を指定することができます (`ASC`または**DESC**です。`ASC`は、既定値) の列を指定します。 たとえば、2 つの列を指定する場合、レコードは順で並べ替えてという名前の最初の列でという名前の 2 番目の列に。 SQL **ORDER BY**句は、並べ替えを定義します。 フレームワークを追加すると、 **ORDER BY**句をレコード セットの SQL クエリを選択範囲の並び順句コントロール。  
  
 呼び出す前に、オブジェクトを構築した後は、レコード セットの並べ替え順序を確立する必要があります、**開く**メンバー関数 (を呼び出す前に、または、 **Requery**既存のレコード セット オブジェクトのメンバー関数ある**開く**メンバー関数)。  
  
#### <a name="to-specify-a-sort-order-for-a-recordset-object"></a>レコード セット オブジェクトの並べ替え順序を指定するには  
  
1.  新しいレコード セット オブジェクトを構築 (を呼び出す準備または**Requery**既存の)。  
  
2.  オブジェクトの値を設定[レコード](../../mfc/reference/crecordset-class.md#m_strsort)データ メンバーです。  
  
     並べ替えは、null で終わる文字列です。 内容が含まれている、 **ORDER BY**句がキーワードではなく**ORDER BY**です。 たとえば、次のように使用します。  
  
    ```  
    recordset.m_strSort = "LastName DESC, FirstName DESC";  
    ```  
  
     not  
  
    ```  
    recordset.m_strSort = "ORDER BY LastName DESC, FirstName DESC";  
    ```  
  
3.  たとえば、フィルターやロック モードは、パラメーターなどの必要なその他のオプションを設定します。  
  
4.  呼び出す**開く**に新しいオブジェクト (または**Requery**既存のオブジェクト)。  
  
 選択したレコードは順序付けと指定します。 たとえば、姓、名の降順で学生レコードのセットを並べ替えるに、次のように行います。  
  
```  
// Construct the recordset  
CStudentSet rsStudent( NULL );  
// Set the sort  
rsStudent.m_strSort = "LastName DESC, FirstName DESC";  
// Run the query with the sort in place  
rsStudent.Open( );  
```  
  
 レコード セットには、すべての降順で並べ替えられます (Z A から) last name、によって、最初の名前で、学生レコードが含まれています。  
  
> [!NOTE]
>  独自の SQL 文字列を渡すことによって、レコード セットの既定の SQL 文字列を上書きする場合**開く**、カスタム文字列がある場合は、並べ替えを設定しないでください、 **ORDER BY**句。  
  
## <a name="see-also"></a>関連項目  
 [レコード セット (ODBC)](../../data/odbc/recordset-odbc.md)   
 [レコード セット: レコード セット (ODBC) のパラメーター化](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)   
 [レコードセット: レコードのフィルター処理 (ODBC)](../../data/odbc/recordset-filtering-records-odbc.md)