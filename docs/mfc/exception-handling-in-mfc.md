---
title: 例外処理 (mfc) |Microsoft Docs
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
ms.openlocfilehash: 4c19b000c1d7ee5cb1f8480f0e9f384b42937dc9
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46414486"
---
# <a name="exception-handling-in-mfc"></a>例外処理 (MFC)

この記事では、MFC で使用できる例外処理メカニズムについて説明します。 2 つのメカニズムを使用できます。

- MFC バージョン 3.0 で使用でき、後で、C++ 例外

- MFC のバージョン 1.0 で使用でき、後で、MFC 例外マクロ

MFC を使用して新しいアプリケーションを記述している場合は、C++ のメカニズムを使用する必要があります。 既存のアプリケーションが広範囲にわたってそのメカニズムを使用する場合は、マクロに基づくメカニズムを使用できます。

MFC 例外処理マクロではなく、C++ 例外を使用する既存のコードを簡単に変換できます。 これを行うためのガイドライン、コードの変換の利点については、記事[例外: MFC 例外マクロからの変換](../mfc/exceptions-converting-from-mfc-exception-macros.md)します。

MFC 例外処理マクロを使用してアプリケーションを既に開発した場合は、新しいコードで C++ 例外を使用している、既存のコードでこれらのマクロを使用を続行できます。 この記事[例外: Version 3.0 での例外処理マクロを変更](../mfc/exceptions-changes-to-exception-macros-in-version-3-0.md)これを行うためのガイドラインを提供します。

> [!NOTE]
>  コードの C++ 例外処理を有効にするコードの生成] ページで、プロジェクトの [C/C++] フォルダーを有効にする C++ の例外を選択します。[プロパティ ページ](../ide/property-pages-visual-cpp.md)ダイアログ ボックスで、または使用して、 [/EHsc](../build/reference/eh-exception-handling-model.md)コンパイラ オプション。

ここでは、次のトピックについて説明します。

- [例外を使用する場合](#_core_when_to_use_exceptions)

- [MFC 例外処理のサポート](#_core_mfc_exception_support)

- [例外についての詳細情報](#_core_further_reading_about_exceptions)

##  <a name="_core_when_to_use_exceptions"></a> 例外を使用する場合

結果の 3 つのカテゴリは、プログラムの実行中に、関数が呼び出されたときに発生する可能性が。 通常の実行、エラーの実行、または異常な実行します。 各カテゴリを以下に示します。

- 通常の実行

     関数は、正常に実行され、返すことがあります。 一部の関数は、関数の結果を示す呼び出し元に結果コードを返します。 結果コードは、関数は厳密に定義され、関数の考えられる結果の範囲を表します。 結果コードでは、成功または失敗を示すことができますか、期待の通常の範囲内にあるエラーの特定の種類を示すこともできます。 たとえば、ファイルのステータス関数は、ファイルが存在しないことを示すコードを返すことができます。 結果コードは、多くの予期される結果のいずれかを表すために、「エラー コード」という用語が使用されないことに注意してください。

- エラー実行

     呼び出し元は、いくつかの間違いは、関数に引数を渡すことで、または不適切なコンテキストで関数を呼び出します。 このような状況と、エラーが発生して、プログラムの開発中にアサーションでは検出する必要があります。 (アサーションの詳細については、次を参照してください[c/c++ アサーション](/visualstudio/debugger/c-cpp-assertions)。)。

- 異常な実行

     異常な実行には、低いメモリまたは I/O エラーなどのプログラムのコントロールの外部の条件は、関数の結果への影響の状況が含まれています。 異常な状況は、例外のスローとキャッチによって処理する必要があります。

例外処理は、異常な実行に特に適しています。

##  <a name="_core_mfc_exception_support"></a> MFC 例外処理のサポート

使用するか、C++ 例外を直接使用するか、または MFC 例外処理マクロを使用して、 [CException クラス](../mfc/reference/cexception-class.md)または`CException`-フレームワークによって、またはアプリケーションによってスローされる可能性がオブジェクトを派生します。

次の表では、MFC によって提供される定義済みの例外を示します。

|例外クラス|説明|
|---------------------|-------------|
|[CMemoryException クラス](../mfc/reference/cmemoryexception-class.md)|メモリ不足|
|[CFileException クラス](../mfc/reference/cfileexception-class.md)|ファイルの例外|
|[CArchiveException クラス](../mfc/reference/carchiveexception-class.md)|アーカイブ/シリアル化の例外|
|[CNotSupportedException クラス](../mfc/reference/cnotsupportedexception-class.md)|サポートされていないサービスの要求への応答|
|[CResourceException クラス](../mfc/reference/cresourceexception-class.md)|Windows リソース割り当て例外|
|[CDaoException クラス](../mfc/reference/cdaoexception-class.md)|データベースの例外 (DAO クラス)|
|[CDBException クラス](../mfc/reference/cdbexception-class.md)|データベースの例外 (ODBC クラス)|
|[COleException クラス](../mfc/reference/coleexception-class.md)|OLE 例外|
|[COleDispatchException クラス](../mfc/reference/coledispatchexception-class.md)|ディスパッチ (オートメーション) 例外|
|[CUserException クラス](../mfc/reference/cuserexception-class.md)|例外メッセージ ボックスでは、ユーザーに警告をスロー ジェネリック[CException クラス](../mfc/reference/cexception-class.md)|

> [!NOTE]
>  MFC では、C++ 例外と MFC 例外処理マクロの両方をサポートします。 MFC によって直接サポートされない Windows NT 構造化例外ハンドラー (SEH) で説明したよう[構造化例外処理](https://msdn.microsoft.com/library/windows/desktop/ms680657)します。

##  <a name="_core_further_reading_about_exceptions"></a> 例外に関する詳細情報

次の記事では、例外処理の MFC ライブラリの使用について説明します。

- [例外処理: 例外のキャッチと削除](../mfc/exceptions-catching-and-deleting-exceptions.md)

- [例外処理: 例外の内容の調査](../mfc/exceptions-examining-exception-contents.md)

- [例外処理: 例外処理でのオブジェクトの解放](../mfc/exceptions-freeing-objects-in-exceptions.md)

- [例外処理: 独自関数からの例外のスロー](../mfc/exceptions-throwing-exceptions-from-your-own-functions.md)

- [例外処理: データベースの例外](../mfc/exceptions-database-exceptions.md)

- [例外処理: OLE の例外](../mfc/exceptions-ole-exceptions.md)

次の記事では、C++ 例外のキーワードを持つ MFC 例外マクロを比較し、コードを改変する方法について説明します。

- [例外処理: MFC 3.0 での変更点](../mfc/exceptions-changes-to-exception-macros-in-version-3-0.md)

- [例外処理: 古いコードの変換](../mfc/exceptions-converting-from-mfc-exception-macros.md)

- [例外処理: MFC マクロと C++ 例外機構の使用](../mfc/exceptions-using-mfc-macros-and-cpp-exceptions.md)

## <a name="see-also"></a>関連項目

[C++ 例外処理](../cpp/cpp-exception-handling.md)<br/>
[方法: 独自のカスタム例外クラスを作成します。](http://go.microsoft.com/fwlink/p/?linkid=128045)

