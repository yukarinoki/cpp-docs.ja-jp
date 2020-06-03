---
title: '例外処理 : データベースの例外'
ms.date: 09/17/2019
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
ms.openlocfilehash: 894960338a7e8c293054ade00e0cdf3295648bb7
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366622"
---
# <a name="exceptions-database-exceptions"></a>例外処理 : データベースの例外

この資料では、データベースの例外を処理する方法について説明します。 この資料の大部分は、オープン データベース接続 (ODBC) の MFC クラスを使用する場合と、データ アクセス オブジェクト (DAO) の MFC クラスを使用する場合に適用されます。 どちらか一方のモデルに固有の材料は明示的にマークされます。 取り上げるトピックは次のとおりです。

- [例外処理へのアプローチ](#_core_approaches_to_exception_handling)

- [データベース例外処理の例](#_core_a_database_exception.2d.handling_example)

## <a name="approaches-to-exception-handling"></a><a name="_core_approaches_to_exception_handling"></a>例外処理へのアプローチ

この方法は、DAO (廃止) と ODBC のどちらを使用している場合でも同じです。

例外を処理する例外ハンドラーを常に記述する必要があります。

データベースの例外をキャッチする最も実用的なアプローチは、例外シナリオを使用してアプリケーションをテストすることです。 コード内の操作で発生する可能性のある例外を特定し、例外を強制的に発生させます。 次に、トレース出力を調べて、スローされる例外を確認するか、デバッガーで返されたエラー情報を調べます。 これにより、使用している例外シナリオに対して表示されるリターン コードがわかります。

### <a name="error-codes-used-for-odbc-exceptions"></a>ODBC 例外に使用されるエラー コード

フレームワークによって定義された戻りコードに加えて **、AFX_SQL_ERROR_XXX**形式の名前を持つ[CDBException](../mfc/reference/cdbexception-class.md)の一部は[ODBC](../data/odbc/odbc-basics.md)リターン コードに基づいています。 このような例外の戻りコードには、 **SQL_ERROR_XXX**形式の名前が付きます。

データベース クラスが返すことのできるリターン コード (フレームワーク定義と ODBC 定義の両方)[m_nRetCode](../mfc/reference/cdbexception-class.md#m_nretcode)は、 class`CDBException`の m_nRetCode データ メンバの下に記述されています。 ODBC で定義されているリターン コードに関する追加情報については、MSDN ライブラリの ODBC SDK*プログラマ リファレンスを参照*してください。

### <a name="error-codes-used-for-dao-exceptions"></a>DAO 例外に使用されるエラー コード

DAO の例外の場合、通常は詳細情報が表示されます。 捕捉された[CDaoException](../mfc/reference/cdaoexception-class.md)オブジェクトの 3 つのデータ メンバーを通じてエラー情報にアクセスできます。

- [m_pErrorInfo](../mfc/reference/cdaoexception-class.md#m_perrorinfo)は、データベースに関連付けられている DAO のエラー オブジェクトのコレクションにエラー情報をカプセル化する[CDaoErrorInfo](../mfc/reference/cdaoerrorinfo-structure.md)オブジェクトへのポインターを含んでいます。

- [m_nAfxDaoError](../mfc/reference/cdaoexception-class.md#m_nafxdaoerror) MFC DAO クラスの拡張エラー コードが含まれています。 これらのエラー コードは、**のデータ**メンバーの下に AFX_DAO_ERROR_XXX フォームの`CDaoException`名前を持つドキュメントです。

- [m_scode](../mfc/reference/cdaoexception-class.md#m_scode)に DAO からの OLE **SCODE**が含まれています (該当する場合)。 ただし、このエラー コードを使用する必要はめったにありません。 通常、他の 2 つのデータ メンバーでは、より多くの情報を使用できます。 **SCODE**値の詳細については、データ メンバーを参照してください。

DAO エラー、DAO エラー オブジェクトの種類、および DAO エラー コレクションに関する追加情報は、[クラス CDaoException](../mfc/reference/cdaoexception-class.md)の下にあります。

## <a name="a-database-exception-handling-example"></a><a name="_core_a_database_exception.2d.handling_example"></a>データベース例外処理の例

次の使用例は、**新しい**演算子を使用してヒープ上に[CRecordset](../mfc/reference/crecordset-class.md)派生オブジェクトを構築し、(ODBC データ ソースの) レコードセットを開きます。 DAO クラスの同様の例については、以下の「DAO 例外の例」を参照してください。

### <a name="odbc-exception-example"></a>ODBC 例外の例

[Open](../mfc/reference/crecordset-class.md#open)メンバー関数は、(ODBC クラスの[CDBException](../mfc/reference/cdbexception-class.md)型の) 例外をスローする可能性`Open`があるため、このコードは**try**ブロックを使用して呼び出しをかっこで囲みます。 後続の**catch**ブロックは`CDBException`. 例外オブジェクト自体`e`を調べることも可能ですが、この場合、レコードセットの作成に失敗したことを知る必要があります。 **catch**ブロックは、メッセージ ボックスを表示し、レコードセット オブジェクトを削除してクリーンアップします。

[!code-cpp[NVC_MFCDatabase#36](../mfc/codesnippet/cpp/exceptions-database-exceptions_1.cpp)]

### <a name="dao-exception-example"></a>DAO 例外の例

DAO の例は ODBC の例に似ていますが、通常は、より多くの種類の情報を取得できます。 次のコードは、レコードセットを開こうともします。 その試行で例外がスローされた場合は、例外オブジェクトのデータ メンバーでエラー情報を調べることができます。 前の ODBC の例と同様に、レコードセットの作成に失敗したことを知る必要があります。

[!code-cpp[NVC_MFCDatabase#37](../mfc/codesnippet/cpp/exceptions-database-exceptions_2.cpp)]

このコードは、例外オブジェクトの[m_pErrorInfo](../mfc/reference/cdaoexception-class.md#m_perrorinfo)メンバーからエラー メッセージ文字列を取得します。 MFC は、例外をスローするときに、このメンバーを埋めます。

オブジェクトによって返されるエラー情報の詳細については、クラス CDaoException と[CDaoErrorInfo](../mfc/reference/cdaoerrorinfo-structure.md)を参照してください。 [CDaoException](../mfc/reference/cdaoexception-class.md) `CDaoException`

Jet (.mdb) データベースを使用していて、ほとんどの場合 ODBC を使用する場合は、エラー オブジェクトは 1 つだけです。 まれに、ODBC データ ソースを使用していて、複数のエラーがある場合は[、CDaoException::GetErrorCount](../mfc/reference/cdaoexception-class.md#geterrorcount)によって返されるエラーの数に基づいて DAO の Errors コレクションをループできます。 ループを通過するたびに[、CDaoException::GetErrorInfo](../mfc/reference/cdaoexception-class.md#geterrorinfo)を呼び出して`m_pErrorInfo`データ メンバーを再入力します。

## <a name="see-also"></a>関連項目

[例外処理](../mfc/exception-handling-in-mfc.md)
