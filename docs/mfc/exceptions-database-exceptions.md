---
title: 例外:データベース例外
ms.date: 11/04/2016
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
ms.openlocfilehash: 2f7f3bff9f28968361ecfa7374a235a727443004
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2019
ms.locfileid: "57285556"
---
# <a name="exceptions-database-exceptions"></a>例外:データベース例外

この記事では、データベースの例外を処理する方法について説明します。 この記事の内容のほとんどには、使用する MFC クラスの Open Database Connectivity (ODBC) または MFC クラスのデータ アクセス オブジェクト (DAO) かどうかが適用されます。 いずれかまたはその他のモデルに固有のマテリアルが明示的にマークします。 ここでは、次の内容について説明します。

- [例外処理](#_core_approaches_to_exception_handling)

- [データベース例外処理の例](#_core_a_database_exception.2d.handling_example)

##  <a name="_core_approaches_to_exception_handling"></a> 例外処理

アプローチは、DAO または ODBC を使用しているかどうかは同じです。

常に、例外的な条件を処理する例外ハンドラーを記述する必要があります。

データベースの例外をキャッチする最も実用的なアプローチでは、例外のシナリオを使用してアプリケーションをテストします。 可能性の高い例外をコード内の操作が発生して、強制的に、例外が発生する可能性がありますを決定します。 どのような例外がスローされると、トレース出力を確認し、またはデバッガーで返されたエラー情報を確認します。 これにより、どのリターン コードを使用している例外状況が表示されますかがわかります。

### <a name="error-codes-used-for-odbc-exceptions"></a>ODBC 例外に対して使用されるエラー コード

リターン コード、フレームワークによって定義されているだけでなく、フォームの名前である**AFX_SQL_ERROR_XXX**、いくつか[CDBExceptions](../mfc/reference/cdbexception-class.md)に基づいて[ODBC](../data/odbc/odbc-basics.md)リターン コード。 このような例外のリターン コードは、フォームの名前を持つ**SQL_ERROR_XXX**します。

リターン コード: フレームワークで定義されたとしていると、ODBC で定義された、ドキュメントを参照しているかをデータベース クラスが返すことができます、 [m_nRetCode](../mfc/reference/cdbexception-class.md#m_nretcode)クラスのデータ メンバー`CDBException`します。 ODBC で定義されたリターン コードの詳細については、ODBC SDK で使用できる*プログラマーズ リファレンス*MSDN ライブラリ。

### <a name="error-codes-used-for-dao-exceptions"></a>DAO 例外に対して使用されるエラー コード

DAO の例外の詳細については、通常使用できます。 エラー情報をアクセスするには、キャッチの 3 つのデータ メンバーを[CDaoException](../mfc/reference/cdaoexception-class.md)オブジェクト。

- [m_pErrorInfo](../mfc/reference/cdaoexception-class.md#m_perrorinfo)へのポインターが含まれています、 [CDaoErrorInfo](../mfc/reference/cdaoerrorinfo-structure.md)データベースに関連付けられたエラー オブジェクトの DAO のコレクション内のエラー情報をカプセル化するオブジェクト。

- [m_nAfxDaoError](../mfc/reference/cdaoexception-class.md#m_nafxdaoerror) MFC DAO クラスから拡張エラー コードが含まれています。 フォームの名前を持つこれらのエラー コード**AFX_DAO_ERROR_XXX**でのデータ メンバーの下に記載されています`CDaoException`します。

- [m_scode](../mfc/reference/cdaoexception-class.md#m_scode) OLE を含む**SCODE**から DAO、該当する場合。 ただしこのエラー コードを使用する必要がありますめったにありません。 通常、詳細については、他の 2 つのデータ メンバーで使用できます。 に関する詳細については、データ メンバーを参照してください**SCODE**値。

DAO エラー、DAO エラー オブジェクトの種類、および DAO Errors コレクションに関する追加情報は、クラスで使用可能な[CDaoException](../mfc/reference/cdaoexception-class.md)します。

##  <a name="_core_a_database_exception.2d.handling_example"></a> データベース例外処理の例

次の例が、構築しようとしています。、 [CRecordset](../mfc/reference/crecordset-class.md)-派生でヒープのオブジェクト、**新しい**演算子、および (ODBC データ ソース) のレコード セットを開きます。 DAO クラスの同様の例は、「DAO 例外次の例」を参照してください。

### <a name="odbc-exception-example"></a>ODBC 例外の例

[オープン](../mfc/reference/crecordset-class.md#open)メンバー関数が例外をスロー (型の[CDBException](../mfc/reference/cdbexception-class.md) ODBC クラス)、そのためこの角かっこをコード、`Open`呼び出しが、**お試しください**ブロック。 それに続く**キャッチ**ブロックがキャッチ、`CDBException`します。 呼ばれる自体には、例外オブジェクトを調べることができます`e`にはここで、レコード セットを作成する試みが失敗したことを知る十分です。 **キャッチ**ブロックがメッセージ ボックスを表示し、レコード セット オブジェクトを削除して、クリーンアップします。

[!code-cpp[NVC_MFCDatabase#36](../mfc/codesnippet/cpp/exceptions-database-exceptions_1.cpp)]

### <a name="dao-exception-example"></a>DAO 例外の例

DAO の例は、ODBC の例に似ていますが、通常多くの種類の情報を取得することができます。 次のコードも、レコード セットを開こうとします。 その試行は、例外をスローする場合は、エラー情報の例外オブジェクトのデータ メンバーを調べることができます。 ODBC の前の例ではおそらく、レコード セットを作成する試みが失敗したことを確認するには不十分です。

[!code-cpp[NVC_MFCDatabase#37](../mfc/codesnippet/cpp/exceptions-database-exceptions_2.cpp)]

このコードからのエラー メッセージ文字列を取得する、 [m_pErrorInfo](../mfc/reference/cdaoexception-class.md#m_perrorinfo)例外オブジェクトのメンバー。 MFC は、このメンバーの例外をスローします。

によって返されるエラー情報の詳細については、`CDaoException`オブジェクト、クラスを参照してください。 [CDaoException](../mfc/reference/cdaoexception-class.md)と[CDaoErrorInfo](../mfc/reference/cdaoerrorinfo-structure.md)します。

Microsoft Jet (.mdb) データベース、およびほとんどの場合は、ODBC を使用するときに作業は、1 つだけのエラー オブジェクトがあります。 まれなケースで、ODBC データ ソースを使用しているし、複数のエラーがあるときにループ処理できます DAO のエラーのコレクションから返されるエラーの数に基づく[もあります](../mfc/reference/cdaoexception-class.md#geterrorcount)します。 ループで毎回呼び出す[CDaoException::GetErrorInfo](../mfc/reference/cdaoexception-class.md#geterrorinfo)を補充する、`m_pErrorInfo`データ メンバー。

## <a name="see-also"></a>関連項目

[例外処理](../mfc/exception-handling-in-mfc.md)
