---
title: '例外処理: データベースの例外の |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- DAO [MFC], exceptions
- exceptions [MFC], database
- exception handling [MFC], databases
- ODBC exceptions [MFC]
- ODBC [MFC], exceptions
- database exceptions [MFC]
- databases [MFC], exception handling
- error codes [MFC], database exception handling
ms.assetid: 28daf260-f824-4be6-aecc-1f859e6dec26
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 83b3f4f54f467ca7f4fbd2a179fdbf01d54dfa89
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2018
ms.locfileid: "36930239"
---
# <a name="exceptions-database-exceptions"></a>例外処理 : データベースの例外
この記事では、データベースの例外を処理する方法について説明します。 この記事の内容の大部分には、使用している MFC クラスのオープン データベース コネクティビティ (ODBC) または MFC クラスのデータ アクセス オブジェクト (DAO) かどうかが適用されます。 いずれかまたはその他のモデルに固有の情報が明示的にマークします。 ここでは、次の内容について説明します。  
  
-   [例外処理](#_core_approaches_to_exception_handling)  
  
-   [データベースの例外処理の例](#_core_a_database_exception.2d.handling_example)  
  
##  <a name="_core_approaches_to_exception_handling"></a> 例外処理  
 DAO または ODBC を使用するかどうか、アプローチは、同じです。  
  
 常に、例外的な条件を処理する例外ハンドラーを記述する必要があります。  
  
 データベースの例外をキャッチする最も実用的なアプローチでは、例外のシナリオを使用してアプリケーションをテストします。 可能性の高いな例外は、コード内の操作で発生して強制的に、例外が発生する可能性がありますを決定します。 次して、どのような例外がスローされると、トレース出力を調べるか、デバッガーで返されたエラー情報を確認します。 これにより、戻り値を使用している例外のシナリオを確認するかがわかります。  
  
### <a name="error-codes-used-for-odbc-exceptions"></a>ODBC 例外に使用されるエラー コード  
 形式の名前であるために、フレームワークによって定義されるリターン コード、に加えて**AFX_SQL_ERROR_XXX**、ある程度[CDBExceptions](../mfc/reference/cdbexception-class.md)に基づく[ODBC](../data/odbc/odbc-basics.md)リターン コード。 このような例外のリターン コードは、フォームの名前を持つ**SQL_ERROR_XXX**です。  
  
 これらのリターン コード: フレームワークで定義されているし、ODBC で定義された両方 — ドキュメントを参照しているかをデータベース クラスが返すことができます、 [m_nRetCode](../mfc/reference/cdbexception-class.md#m_nretcode)クラスのデータ メンバー`CDBException`です。 ODBC の定義のリターン コードの詳細については、ODBC SDK で使用できる*プログラマーズ リファレンス*MSDN ライブラリです。  
  
### <a name="error-codes-used-for-dao-exceptions"></a>DAO 例外に使用されるエラー コード  
 DAO の例外の詳細については通常使用できます。 エラー情報は、キャッチの 3 つのデータ メンバーにアクセスできます[CDaoException](../mfc/reference/cdaoexception-class.md)オブジェクト。  
  
-   [m_pErrorInfo](../mfc/reference/cdaoexception-class.md#m_perrorinfo)へのポインターが含まれています、 [CDaoErrorInfo](../mfc/reference/cdaoerrorinfo-structure.md)データベースに関連付けられているエラー オブジェクトの DAO のコレクションにエラー情報をカプセル化するオブジェクト。  
  
-   [m_nAfxDaoError](../mfc/reference/cdaoexception-class.md#m_nafxdaoerror) MFC DAO クラスから拡張エラー コードが含まれています。 フォームの名前を持つこれらのエラー コード**AFX_DAO_ERROR_XXX**、内のデータ メンバーの下に記載されて`CDaoException`です。  
  
-   [m_scode](../mfc/reference/cdaoexception-class.md#m_scode) OLE を含む**SCODE**から DAO、該当する場合。 ただし、このエラー コードを操作する必要があることはほとんどありません。 通常の詳細については、その他の 2 つのデータ メンバーは、使用可能なです。 データ メンバーの詳細を参照してください**SCODE**値。  
  
 DAO エラー、DAO エラー オブジェクトの種類、および DAO Errors コレクションに関する追加情報がクラスで使用可能な[CDaoException](../mfc/reference/cdaoexception-class.md)です。  
  
##  <a name="_core_a_database_exception.2d.handling_example"></a> データベースの例外処理の例  
 次の例が、構築しようとしています。、 [CRecordset](../mfc/reference/crecordset-class.md)-派生、ヒープにオブジェクト、**新しい**演算子、および、レコード セット (ODBC データ ソース) を開きます。 DAO クラスの同様の例では、「DAO 例外次の例」を参照してください。  
  
### <a name="odbc-exception-example"></a>ODBC 例外の例  
 [開く](../mfc/reference/crecordset-class.md#open)メンバー関数が例外をスローできません (型の[CDBException](../mfc/reference/cdbexception-class.md) ODBC クラスの)、したがってこの角かっこをコード、`Open`を呼び出す、**を再試行してください**ブロックします。 後続**キャッチ**ブロックでキャッチする、`CDBException`です。 呼ばれる自体には、例外オブジェクトを調べる`e`がここではレコード セットを作成する試行が失敗したことを確認することができます。 **キャッチ**ブロックがメッセージ ボックスを表示し、レコード セット オブジェクトを削除してクリーンアップします。  
  
 [!code-cpp[NVC_MFCDatabase#36](../mfc/codesnippet/cpp/exceptions-database-exceptions_1.cpp)]  
  
### <a name="dao-exception-example"></a>DAO 例外の例  
 DAO 例は、ODBC の例に似ていますが、通常、複数の種類の情報を取得することができます。 次のコードも、レコード セットを開こうとします。 その試行は、例外をスローする場合は、エラーについては、例外オブジェクトのデータ メンバーを確認できます。 ODBC の前の例ではおそらくをレコード セットを作成する試みが失敗したことを理解するのに十分なです。  
  
 [!code-cpp[NVC_MFCDatabase#37](../mfc/codesnippet/cpp/exceptions-database-exceptions_2.cpp)]  
  
 このコードからのエラー メッセージ文字列を取得する、 [m_pErrorInfo](../mfc/reference/cdaoexception-class.md#m_perrorinfo)例外オブジェクトのメンバーです。 MFC は、このメンバーの例外をスローします。  
  
 によって返されるエラー情報については、`CDaoException`オブジェクト、クラスを参照してください[CDaoException](../mfc/reference/cdaoexception-class.md)と[CDaoErrorInfo](../mfc/reference/cdaoerrorinfo-structure.md)です。  
  
 Microsoft Jet (.mdb) データベースを使用して、ほとんどの場合は、ODBC を使用しているときに、作業している、ときに、1 つだけのエラー オブジェクトがあります。 まれなケースで、ODBC データ ソースを使用しているし、複数のエラーがある場合をループできます DAO のエラーのコレクションから返されるエラーの数に基づいて[もあります](../mfc/reference/cdaoexception-class.md#geterrorcount)です。 ループで毎回呼び出す[CDaoException::GetErrorInfo](../mfc/reference/cdaoexception-class.md#geterrorinfo)を補充する、`m_pErrorInfo`データ メンバーです。  
  
## <a name="see-also"></a>関連項目  
 [例外処理](../mfc/exception-handling-in-mfc.md)

