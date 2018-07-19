---
title: 'ODBC: ODBC API を呼び出す関数を直接 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ODBC API functions [C++], calling
- ODBC [C++], catalog functions
- ODBC API functions [C++]
- APIs [C++], calling
- ODBC classes [C++], vs. ODBC API
- direct ODBC API calls
- catalog functions (ODBC)
- catalog functions (ODBC), calling
- ODBC [C++], API functions
ms.assetid: 4295f1d9-4528-4d2e-bd6a-c7569953c7fa
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 55b95c5dd48631f9c724aebd163ce948c3469850
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33089719"
---
# <a name="odbc-calling-odbc-api-functions-directly"></a>ODBC: ODBC API 関数の直接呼び出し
データベース クラスを提供するシンプルなインターフェイス、[データソース](../../data/odbc/data-source-odbc.md)ODBC よりもします。 その結果、クラスには、すべての ODBC API はカプセル化されません。 クラスの機能の外側にあるすべての機能を直接 ODBC API 関数を呼び出す必要があります。 たとえば、ODBC カタログ関数を呼び出す必要があります (**:: SQLColumns**、 **:: SQLProcedures**、 **:: SQLTables**、およびその他) 直接です。  
  
> [!NOTE]
>  ODBC データ ソースには、ここで説明するように、MFC ODBC クラス経由でアクセスできます。また、MFC DAO (Data Access Object) クラス経由でもアクセスできます。  
  
 ODBC API 関数の呼び出しを直接行う必要がありますフレームワークなしの呼び出しを行っていた場合にとる同じ手順を実行します。 これらの手順します。  
  
-   呼び出しが返された結果の記憶域を割り当てます。  
  
-   ODBC を渡す**HDBC**または**HSTMT**関数のパラメーター シグネチャによって、処理します。 使用して、 [AFXGetHENV](../../mfc/reference/database-macros-and-globals.md#afxgethenv)マクロ ODBC ハンドルを取得します。  
  
     メンバー変数**CDatabase::m_hdbc**と**CRecordset::m_hstmt**を利用できるようにで割り当てるし、自分で初期化する必要はありません。  
  
-   おそらくを準備するか、メインの呼び出しを補足する追加の ODBC 関数を呼び出します。  
  
-   完了したら、記憶域を解放します。  
  
 次の手順の詳細については、次を参照してください。、[オープン データベース コネクティビティ (ODBC)](https://msdn.microsoft.com/en-us/library/ms710252.aspx) SDK MSDN ドキュメントにします。  
  
 この手順に加えて、関数の戻り値を確認して、プログラムが完了するために非同期呼び出しの待機していないことを確認する追加の手順を実行する必要があります。 使用して最後の手順を簡略化できます、`AFX_SQL_ASYNC`と`AFX_SQL_SYNC`マクロです。 詳細については、次を参照してください。[マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)で、 *『 MFC リファレンス*です。  

  
## <a name="see-also"></a>関連項目  
 [ODBC の基礎](../../data/odbc/odbc-basics.md)
