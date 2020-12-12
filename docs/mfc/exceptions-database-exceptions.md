---
description: '詳細については、「例外: データベース例外」を参照してください。'
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
ms.openlocfilehash: 3e45f887d51b4b81196cd08d11f426f4ee6d4481
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97290649"
---
# <a name="exceptions-database-exceptions"></a>例外処理 : データベースの例外

この記事では、データベースの例外を処理する方法について説明します。 この記事の内容の大部分は、Open Database Connectivity (ODBC) 用の MFC クラス、またはデータアクセスオブジェクト (DAO) 用の MFC クラスを使用している場合に適用されます。 一方または他のモデルに固有の素材が明示的にマークされます。 取り上げるトピックは次のとおりです。

- [例外処理の方法](#_core_approaches_to_exception_handling)

- [データベース例外処理の例](#_core_a_database_exception.2d.handling_example)

## <a name="approaches-to-exception-handling"></a><a name="_core_approaches_to_exception_handling"></a> 例外処理の方法

DAO (obsolete) と ODBC のどちらを使用している場合でも、この方法は同じです。

例外的な条件を処理するには、常に例外ハンドラーを記述する必要があります。

データベースの例外をキャッチする最も実用的な方法は、例外シナリオでアプリケーションをテストすることです。 コード内の操作に対して発生する可能性がある例外を判断し、例外を強制的に発生させます。 次に、トレース出力を調べて、スローされた例外を確認するか、デバッガーで返されたエラー情報を調べます。 これにより、使用している例外のシナリオに対してどのリターンコードが表示されるかを知ることができます。

### <a name="error-codes-used-for-odbc-exceptions"></a>ODBC 例外に使用されるエラーコード

フレームワークによって定義されたリターンコードに加えて、 **AFX_SQL_ERROR_XXX** フォームの名前が付いているため、一部の [CDBExceptions](reference/cdbexception-class.md) は [ODBC](../data/odbc/odbc-basics.md) のリターンコードに基づいています。 このような例外のリターンコードには **SQL_ERROR_XXX** の形式の名前があります。

データベースクラスが返すことができるリターンコード (フレームワーク定義と ODBC 定義の両方) は、クラスの [m_nRetCode](reference/cdbexception-class.md#m_nretcode) データメンバーの下に記載されてい `CDBException` ます。 Odbc で定義されているリターンコードの詳細については、 [Odbc プログラマーズリファレンスを参照](/sql/odbc/reference/odbc-programmer-s-reference)してください。

### <a name="error-codes-used-for-dao-exceptions"></a>DAO 例外に使用されるエラーコード

DAO の例外については、通常、詳細情報を参照してください。 キャッチされた [CDaoException](reference/cdaoexception-class.md) オブジェクトの3つのデータメンバーを通じて、エラー情報にアクセスできます。

- [m_pErrorInfo](reference/cdaoexception-class.md#m_perrorinfo) には、DAO のデータベースに関連付けられているエラーオブジェクトのコレクションにエラー情報をカプセル化する [CDaoErrorInfo](reference/cdaoerrorinfo-structure.md) オブジェクトへのポインターが含まれています。

- [m_nAfxDaoError](reference/cdaoexception-class.md#m_nafxdaoerror) には、MFC DAO クラスの拡張エラーコードが含まれています。 これらのエラーコードには **AFX_DAO_ERROR_XXX** 形式の名前が付いており、のデータメンバーの下に記載されてい `CDaoException` ます。

- 必要に応じて、DAO から OLE **scode** が [m_scode](reference/cdaoexception-class.md#m_scode)に含まれています。 ただし、このエラーコードを使用する必要はほとんどありません。 通常、他の2つのデータメンバーでは、より多くの情報を使用できます。 **SCODE** 値の詳細については、データメンバーを参照してください。

DAO エラー、DAO エラーオブジェクトの種類、DAO エラーのコレクションの詳細については、「 [CDaoException](reference/cdaoexception-class.md)クラス」を参照してください。

## <a name="a-database-exception-handling-example"></a><a name="_core_a_database_exception.2d.handling_example"></a> データベース Exception-Handling の例

次の例では、演算子を使用して、ヒープ上に [CRecordset](reference/crecordset-class.md)から派生したオブジェクトを構築 **`new`** し、そのレコードセット (ODBC データソース用) を開きます。 同様の DAO クラスの例については、以下の「DAO 例外の例」を参照してください。

### <a name="odbc-exception-example"></a>ODBC 例外の例

[Open](reference/crecordset-class.md#open)メンバー関数は、(ODBC クラスの [CDBException](reference/cdbexception-class.md)型の) 例外をスローする可能性があるため、このコードはブロックを使用して呼び出しを角かっこ `Open` で囲み **`try`** ます。 後続の **`catch`** ブロックはをキャッチ `CDBException` します。 という例外オブジェクト自体を調べることもでき `e` ますが、この場合は、レコードセットを作成しようとしたときに失敗したことを把握しておく必要があります。 ブロックは、 **`catch`** メッセージボックスを表示し、レコードセットオブジェクトを削除してクリーンアップします。

[!code-cpp[NVC_MFCDatabase#36](codesnippet/cpp/exceptions-database-exceptions_1.cpp)]

### <a name="dao-exception-example"></a>DAO の例外の例

DAO の例は ODBC の例と似ていますが、通常はさらに多くの種類の情報を取得できます。 次のコードでは、レコードセットも開こうとします。 この試行によって例外がスローされた場合は、例外オブジェクトのデータメンバーにエラー情報があるかどうかを調べることができます。 前の ODBC の例と同様に、レコードセットを作成しようとして失敗したことを把握しておくと十分でしょう。

[!code-cpp[NVC_MFCDatabase#37](codesnippet/cpp/exceptions-database-exceptions_2.cpp)]

このコードは、exception オブジェクトの [m_pErrorInfo](reference/cdaoexception-class.md#m_perrorinfo) メンバーからのエラーメッセージ文字列を取得します。 MFC は、例外をスローするときにこのメンバーを塗りつぶします。

オブジェクトによって返されるエラー情報の詳細につい `CDaoException` ては、「Classes [CDaoException](reference/cdaoexception-class.md) and [CDaoErrorInfo](reference/cdaoerrorinfo-structure.md)」を参照してください。

Microsoft Jet (.mdb) データベースを操作しているときに、ほとんどの場合 ODBC を操作しているときは、エラーオブジェクトは1つだけです。 まれに、ODBC データソースを使用しているときに複数のエラーが発生した場合は、 [CDaoException:: GetErrorCount](reference/cdaoexception-class.md#geterrorcount)から返されたエラーの数に基づいて、DAO の errors コレクションをループすることができます。 ループを実行するたびに、 [CDaoException:: GetErrorInfo](reference/cdaoexception-class.md#geterrorinfo) を呼び出して `m_pErrorInfo` データメンバーを補充します。

## <a name="see-also"></a>関連項目

[例外処理](exception-handling-in-mfc.md)
