---
title: MFC での例外処理 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- DAO [MFC], exceptions
- assertions [MFC], When to use exceptions
- exception handling [MFC], MFC
- resource allocation exception
- resources [MFC], allocating
- keywords [MFC], exception handling
- errors [MFC], detected by assertions
- ODBC exceptions [MFC]
- serialization [MFC], exceptions
- Automation [MFC], exceptions
- exception macros [MFC]
- predefined exceptions [MFC]
- C++ exception handling [MFC], enabling
- C++ exception handling [MFC], MFC applications
- requests for unsupported services [MFC]
- database exceptions [MFC]
- archive exceptions [MFC]
- MFC, exceptions
- C++ exception handling [MFC], types of
- macros [MFC], exception handling
- abnormal program execution [MFC]
- OLE exceptions [MFC], MFC exception handling
- error handling [MFC], exceptions and
- class libraries [MFC], exception support
- exceptions [MFC], MFC macros vs. C++ keywords
- memory [MFC], out-of-memory exceptions
- Windows [MFC], resource allocation exceptions
- macros [MFC], MFC exception macros
- function calls [MFC], results
- out-of-memory exceptions [MFC]
ms.assetid: 0926627d-2ba7-44a6-babe-d851a4a2517c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0792ddf067f6289d612a9adb0c8ffeaf8e554ed6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="exception-handling-in-mfc"></a>例外処理 (MFC)
この記事では、MFC で使用できる例外処理メカニズムについて説明します。 2 つのメカニズムを使用できます。  
  
-   C++ の例外、MFC バージョン 3.0 の使用可能な以降  
  
-   MFC 例外マクロ、MFC バージョン 1.0 で使用できる以降  
  
 MFC を使用して、新しいアプリケーションを作成する場合は、C++ の機構を使用する必要があります。 既存のアプリケーションを既にそのメカニズムを広範囲にわたって使用する場合は、マクロ ベースのメカニズムを使用できます。  
  
 MFC 例外マクロではなく、C++ 例外処理を使用する既存のコードを簡単に変換できます。 コードとこれ教本を変換する利点については、記事[例外: MFC 例外マクロからの変換](../mfc/exceptions-converting-from-mfc-exception-macros.md)です。  
  
 既に MFC 例外マクロを使用してアプリケーションを開発した場合、新しいコードで C++ 例外処理を使用しているときに、既存のコードでこれらのマクロの使用を続行できます。 アーティクル[例外: Version 3.0 での例外処理マクロを変更](../mfc/exceptions-changes-to-exception-macros-in-version-3-0.md)これを行うためのガイドラインを提供します。  
  
> [!NOTE]
>  コードの C++ 例外処理を有効にするコードの生成 ページで、C と C++ のフォルダー、プロジェクトの C++ の例外を有効にするを選択[プロパティ ページ](../ide/property-pages-visual-cpp.md) ダイアログ ボックス、または/GX コンパイラ オプションを使用します。 既定ではでは/GX-、例外処理を無効になります。  
  
 ここでは、次のトピックについて説明します。  
  
-   [例外を使用する場合](#_core_when_to_use_exceptions)  
  
-   [MFC 例外処理のサポート](#_core_mfc_exception_support)  
  
-   [例外についての詳細情報](#_core_further_reading_about_exceptions)  
  
##  <a name="_core_when_to_use_exceptions"></a> 例外を使用する場合  
 結果の 3 つのカテゴリは、プログラムの実行中の関数が呼び出されたときに発生する可能性が: 通常の実行、誤った実行、または異常実行します。 各カテゴリのとおりです。  
  
-   通常の実行  
  
     関数は、正常に実行され、返すことがあります。 一部の関数は、関数の結果を示す、呼び出し元に結果コードを返します。 考えられる結果コードは、厳密には、関数の定義し、関数の考えられる結果の範囲を表すです。 結果コードは、成功または失敗を示すことができます。 または予測の標準の範囲内にあるエラーの特定の種類を示すこともできます。 たとえば、ファイルのステータス関数は、ファイルが存在しないことを示すコードを返すことができます。 結果コードは、多くの予期される結果の 1 つを表すために、「エラー コード」という用語が使用されないことに注意してください。  
  
-   エラー実行  
  
     呼び出し元は、関数に引数を渡すときにいくつかある間違いは、または不適切なコンテキストで関数を呼び出します。 このような状況と、エラーが発生して、プログラムの開発中にアサーションを検出する必要があります。 (詳細については、次を参照してください[c/c++ アサーション](/visualstudio/debugger/c-cpp-assertions)。)。  
  
-   異常な実行  
  
     異常な実行には、低いメモリまたは I/O エラーなど、プログラムの制御外の条件は、関数の結果への影響の状況が含まれています。 異常な場合は、例外のスローとキャッチによって処理する必要があります。  
  
 例外の使用は、異常実行に特に適しています。  
  
##  <a name="_core_mfc_exception_support"></a> MFC 例外処理のサポート  
 使用するか、C++ 例外処理機構を直接使用するか、MFC 例外マクロを使用して、 [CException クラス](../mfc/reference/cexception-class.md)または`CException`-フレームワークによって、またはアプリケーションによってスローされる可能性がありますのあるオブジェクトを派生します。  
  
 次の表は、MFC によって提供される定義済みの例外を示します。  
  
|例外クラス|説明|  
|---------------------|-------------|  
|[CMemoryException クラス](../mfc/reference/cmemoryexception-class.md)|メモリ不足|  
|[CFileException クラス](../mfc/reference/cfileexception-class.md)|ファイルの例外|  
|[CArchiveException クラス](../mfc/reference/carchiveexception-class.md)|アーカイブ/シリアル化例外|  
|[CNotSupportedException クラス](../mfc/reference/cnotsupportedexception-class.md)|サポートされていないサービスの要求への応答|  
|[CResourceException クラス](../mfc/reference/cresourceexception-class.md)|Windows リソース割り当て例外|  
|[CDaoException クラス](../mfc/reference/cdaoexception-class.md)|データベースの例外 (DAO クラス)|  
|[CDBException クラス](../mfc/reference/cdbexception-class.md)|データベースの例外 (ODBC クラス)|  
|[COleException クラス](../mfc/reference/coleexception-class.md)|OLE 例外|  
|[COleDispatchException クラス](../mfc/reference/coledispatchexception-class.md)|ディスパッチ (オートメーション) 例外|  
|[CUserException クラス](../mfc/reference/cuserexception-class.md)|例外は、メッセージ ボックスでユーザーにアラートをし、ジェネリック型をスロー [CException クラス](../mfc/reference/cexception-class.md)|  
  
> [!NOTE]
>  MFC には、C++ 例外と MFC 例外マクロの両方がサポートしています。 MFC によって直接サポートされない構造化された Windows NT 例外ハンドラー (SEH) で説明したよう[構造化例外処理](http://msdn.microsoft.com/library/windows/desktop/ms680657)です。  
  
##  <a name="_core_further_reading_about_exceptions"></a> 例外に関する詳細情報  
 次の記事では、例外処理機構の MFC ライブラリの使用について説明します。  
  
-   [例外処理: 例外のキャッチと削除](../mfc/exceptions-catching-and-deleting-exceptions.md)  
  
-   [例外処理: 例外の内容の調査](../mfc/exceptions-examining-exception-contents.md)  
  
-   [例外処理: 例外処理でのオブジェクトの解放](../mfc/exceptions-freeing-objects-in-exceptions.md)  
  
-   [例外処理: 独自関数からの例外のスロー](../mfc/exceptions-throwing-exceptions-from-your-own-functions.md)  
  
-   [例外処理: データベースの例外](../mfc/exceptions-database-exceptions.md)  
  
-   [例外処理: OLE の例外](../mfc/exceptions-ole-exceptions.md)  
  
 以下の資料では、C++ 例外のキーワードと MFC 例外マクロの比較し、コードを改変する方法について説明します。  
  
-   [例外処理: MFC 3.0 での変更点](../mfc/exceptions-changes-to-exception-macros-in-version-3-0.md)  
  
-   [例外処理: 古いコードの変換](../mfc/exceptions-converting-from-mfc-exception-macros.md)  
  
-   [例外処理: MFC マクロと C++ 例外機構の使用](../mfc/exceptions-using-mfc-macros-and-cpp-exceptions.md)  
  
## <a name="see-also"></a>関連項目  
 [C++ 例外処理](../cpp/cpp-exception-handling.md)   
 [方法: 独自のカスタム例外クラスを作成します。](http://go.microsoft.com/fwlink/p/?linkid=128045)

