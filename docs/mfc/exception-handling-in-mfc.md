---
title: 例外処理 (MFC)
ms.date: 11/19/2019
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
ms.openlocfilehash: d339ec98dabc6cb24fc7106c4c7238cd6a14a71b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365529"
---
# <a name="exception-handling-in-mfc"></a>例外処理 (MFC)

この資料では、MFC で使用できる例外処理メカニズムについて説明します。 2 つのメカニズムが使用できます。

- C++ の例外 (MFC バージョン 3.0 以降で利用可能)

- MFC 例外マクロ (MFC バージョン 1.0 以降で利用可能)

MFC を使用して新しいアプリケーションを作成する場合は、C++ のメカニズムを使用する必要があります。 既存のアプリケーションで既にそのメカニズムを使用している場合は、マクロベースのメカニズムを使用できます。

MFC 例外マクロの代わりに、既存のコードを簡単に変換して C++ 例外を使用できます。 コードを変換する利点とガイドラインについては、「[例外 : MFC 例外マクロからの変換](../mfc/exceptions-converting-from-mfc-exception-macros.md)」を参照してください。

MFC 例外マクロを使用してアプリケーションを既に開発している場合は、新しいコードで C++ 例外を使用しながら、既存のコードでこれらのマクロを引き続き使用できます。 「[例外: バージョン 3.0 の例外マクロに対する変更](../mfc/exceptions-changes-to-exception-macros-in-version-3-0.md)点」では、そのガイドラインが示されています。

> [!NOTE]
> コードで C++ 例外処理を有効にするには、プロジェクトの[[プロパティ ページ](../build/reference/property-pages-visual-cpp.md)] ダイアログ ボックスの [C/C++] フォルダーの [コード生成] ページで [C++ 例外を有効にする] を選択するか[、/EHsc](../build/reference/eh-exception-handling-model.md)コンパイラ オプションを使用します。

この記事では、次のトピックについて説明します。

- [例外処理を使う場合](#_core_when_to_use_exceptions)

- [MFC 例外サポート](#_core_mfc_exception_support)

- [例外に関する詳細な説明](#_core_further_reading_about_exceptions)

## <a name="when-to-use-exceptions"></a><a name="_core_when_to_use_exceptions"></a>例外を使用する場合

プログラムの実行中に関数が呼び出されたときに、通常の実行、誤った実行、または異常実行の 3 つのカテゴリが発生する可能性があります。 各カテゴリは以下に説明します。

- 通常の実行

   関数は正常に実行され、戻る場合があります。 一部の関数は、関数の結果を示す結果コードを呼び出し元に返します。 可能な結果コードは、関数に厳密に定義され、関数の可能な結果の範囲を表します。 結果コードは、成功または失敗を示したり、期待の正常範囲内にある特定の種類の失敗を示す場合もあります。 たとえば、ファイル状態関数は、ファイルが存在しないことを示すコードを返すことができます。 結果コードは多くの期待される結果の 1 つを表すため、"エラー コード" という用語は使用されません。

- 誤った実行

   呼び出し元が関数に引数を渡す場合、または不適切なコンテキストで関数を呼び出す場合に、いくつかの誤りがあります。 この状況ではエラーが発生し、プログラム開発中にアサーションによって検出されます。 (アサーションの詳細については[、C/C++ アサーションを](/visualstudio/debugger/c-cpp-assertions)参照してください。

- 異常実行

   異常な実行には、メモリ不足や I/O エラーなど、プログラムの制御外の状態が関数の結果に影響を与えている状況が含まれます。 異常な状況は、例外をキャッチしてスローすることによって処理する必要があります。

例外の使用は、異常実行に特に適しています。

## <a name="mfc-exception-support"></a><a name="_core_mfc_exception_support"></a>MFC 例外サポート

C++ 例外を直接使用する場合でも、MFC 例外マクロを使用する場合でも、フレームワークまたは`CException`アプリケーションによってスローされる[CException クラス](../mfc/reference/cexception-class.md)または派生オブジェクトを使用します。

MFC で提供される定義済みの例外を次の表に示します。

|例外クラス|意味|
|---------------------|-------------|
|[クラス](../mfc/reference/cmemoryexception-class.md)|メモリ不足|
|[CFileException クラス](../mfc/reference/cfileexception-class.md)|ファイルの例外|
|[CArchiveException クラス](../mfc/reference/carchiveexception-class.md)|アーカイブ/シリアル化の例外|
|[クラスをサポートしていません。](../mfc/reference/cnotsupportedexception-class.md)|サポートされていないサービスに対する要求への応答|
|[クラス](../mfc/reference/cresourceexception-class.md)|Windows リソース割り当ての例外|
|[クラスを呼び出す](../mfc/reference/cdaoexception-class.md)|データベースの例外 (DAO クラス)|
|[CDBException クラス](../mfc/reference/cdbexception-class.md)|データベース例外 (ODBC クラス)|
|[クラス](../mfc/reference/coleexception-class.md)|OLE 例外|
|[COleDispatchException クラス](../mfc/reference/coledispatchexception-class.md)|ディスパッチ (自動化) 例外|
|[CUserException クラス](../mfc/reference/cuserexception-class.md)|メッセージ ボックスをユーザーに警告し、汎用[CException クラス](../mfc/reference/cexception-class.md)をスローする例外|

MFC はバージョン 3.0 以降、C++ 例外を使用していますが、フォームの C++ 例外に似た古い例外処理マクロを引き続きサポートします。 これらのマクロは新しいプログラミングで推奨されませんが、下位互換性のために引き続きサポートされます。 既にマクロを使用しているプログラムでは、自由に C++ の例外も使用できます。 マクロは、前処理の間に、Visual C++ バージョン 2.0 の時点で C++ 言語の MSVC 実装で定義されている例外処理キーワードに評価されます。 C++ 例外処理の使用を開始するときは、既存の例外処理マクロをそのまま維持できます。 マクロと C++ 例外処理の混合、および古いコードを変換して新しいメカニズムを使用する方法については、「[例外: MFC マクロと C++ 例外と例外の使用](../mfc/exceptions-using-mfc-macros-and-cpp-exceptions.md): MFC[例外マクロからの変換](../mfc/exceptions-converting-from-mfc-exception-macros.md)」を参照してください。 以前の MFC 例外マクロを使用している場合、これは C++ の例外のキーワードに評価されます。 例外[: バージョン 3.0 の例外マクロの変更](../mfc/exceptions-changes-to-exception-macros-in-version-3-0.md)を参照してください。 MFC は、「 構造化例外処理 」で説明されているように、Windows NT[構造化例外](/windows/win32/debug/structured-exception-handling)ハンドラー (SEH) を直接サポートしていません。

## <a name="further-reading-about-exceptions"></a><a name="_core_further_reading_about_exceptions"></a>例外に関する詳細な説明

次の資料では、例外ハンドリングに MFC ライブラリを使用する方法について説明します。

- [例外処理: 例外のキャッチと削除](../mfc/exceptions-catching-and-deleting-exceptions.md)

- [例外処理: 例外の内容の調査](../mfc/exceptions-examining-exception-contents.md)

- [例外処理 : 例外処理でのオブジェクトの解放](../mfc/exceptions-freeing-objects-in-exceptions.md)

- [例外処理 : 独自関数からの例外のスロー](../mfc/exceptions-throwing-exceptions-from-your-own-functions.md)

- [例外処理 : データベースの例外](../mfc/exceptions-database-exceptions.md)

- [例外処理 : OLE の例外](../mfc/exceptions-ole-exceptions.md)

次の資料では、MFC 例外マクロと C++ 例外キーワードを比較し、コードを調整する方法について説明します。

- [例外処理 : MFC 3.0 での変更点](../mfc/exceptions-changes-to-exception-macros-in-version-3-0.md)

- [例外処理 : 古いコードの変換](../mfc/exceptions-converting-from-mfc-exception-macros.md)

- [例外処理 : MFC マクロと C++ 例外機構の使用](../mfc/exceptions-using-mfc-macros-and-cpp-exceptions.md)

## <a name="see-also"></a>関連項目

[例外とエラー処理に関する最新の C++ のベスト プラクティス](../cpp/errors-and-exception-handling-modern-cpp.md)<br/>
[方法 : 独自のカスタム例外クラスを作成する](https://go.microsoft.com/fwlink/p/?linkid=128045)
