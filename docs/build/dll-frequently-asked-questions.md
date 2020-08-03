---
title: MFC DLL に関してよく寄せられる質問
ms.date: 05/06/2019
helpviewer_keywords:
- troubleshooting [C++], DLLs
- DLLs [C++], frequently asked questions
- FAQs [C++], DLLs
ms.assetid: 09dd068e-fc33-414e-82f7-289c70680256
ms.openlocfilehash: e12817e016376d5b76ec67e8bd10fbd3e85dbdda
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87229845"
---
# <a name="dll-frequently-asked-questions"></a>DLL に関してよく寄せられる質問

DLL に関してよく寄せられる質問 (FAQ) を以下に取り上げます。

- [MFC DLL から複数のスレッドを作成できますか。](#mfc_multithreaded_1)

- [マルチスレッド アプリケーションでは異なるスレッドで MFC DLL にアクセスできますか。](#mfc_multithreaded_2)

- [MFC DLL 内で使用できない MFC クラスまたは関数はありますか。](#mfc_prohibited_classes)

- [読み込み時にクライアント アプリケーションのパフォーマンスを向上させるにはどのような最適化手法を使えばよいですか。](#mfc_optimization)

- [標準 MFC DLL でメモリ リークが発生しましたが、自分のコードは正常に見えます。メモリ リークを検出するにはどうすればよいですか。](#memory_leak)

## <a name="can-an-mfc-dll-create-multiple-threads"></a><a name="mfc_multithreaded_1"></a> MFC DLL から複数のスレッドを作成できますか。

初期化中を除き、MFC DLL では、**TlsAlloc** などの Win32 スレッド ローカル ストレージ (TLS) 関数を使用してスレッド ローカル ストレージを割り当てる限り、複数のスレッドを安全に作成できます。 ただし、MFC DLL で **`__declspec(thread)`** を使用してスレッド ローカル ストレージを割り当てる場合、クライアント アプリケーションは暗黙的に DLL にリンクされている必要があります。 クライアント アプリケーションが明示的に DLL にリンクされている場合、**LoadLibrary** を呼び出しても DLL は正常に読み込まれません。 DLL のスレッド ローカル変数の詳細については、「[thread](../cpp/thread.md)」を参照してください。

起動中に新しい MFC スレッドを作成する MFC DLL は、アプリケーションによって読み込まれると応答を停止します。 これには、次の内部で `AfxBeginThread` または `CWinThread::CreateThread` を呼び出してスレッドを作成する場合も含まれます。

- 標準 MFC DLL 内の `CWinApp` 派生オブジェクトの `InitInstance`。

- 標準 MFC DLL 内の指定された `DllMain` または **RawDllMain** 関数。

- MFC 拡張 DLL 内の指定された `DllMain` または **RawDllMain** 関数。

## <a name="can-a-multithreaded-application-access-an-mfc-dll-in-different-threads"></a><a name="mfc_multithreaded_2"></a> マルチスレッド アプリケーションでは異なるスレッドで MFC DLL にアクセスできますか。

マルチスレッド アプリケーションでは、別のスレッドから、MFC および MFC 拡張 DLL に動的にリンクされる標準 MFC DLL にアクセスできます。 アプリケーションでは、そのアプリケーション内で作成された複数のスレッドから、MFC に静的にリンクされた標準 MFC DLL にアクセスできます。

## <a name="are-there-any-mfc-classes-or-functions-that-cannot-be-used-in-an-mfc-dll"></a><a name="mfc_prohibited_classes"></a> MFC DLL 内で使用できない MFC クラスまたは関数はありますか。

拡張 DLL では、クライアント アプリケーションの `CWinApp` 派生クラスが使用されます。 それらが独自の `CWinApp` 派生クラスを持つことはできません。

標準 MFC DLL には、MFC アプリケーションと同様に、`CWinApp` 派生クラスと、そのアプリケーション クラスの 1 つのオブジェクトが必要です。 アプリケーションの `CWinApp` オブジェクトとは異なり、DLL の `CWinApp` オブジェクトにはメイン メッセージ ポンプがありません。

`CWinApp::Run` メカニズムは DLL に適用されないため、アプリケーションにはメイン メッセージ ポンプがあることに注意してください。 DLL がモードレス ダイアログ ボックスを開く場合、または独自のメイン フレーム ウィンドウがある場合、アプリケーションのメイン メッセージ ポンプでは、DLL によってエクスポートされたルーチンを呼び出し、次に DLL のアプリケーション オブジェクトの `CWinApp::PreTranslateMessage` メンバー関数を呼び出す必要があります。

## <a name="what-optimization-techniques-should-i-use-to-improve-the-client-application39s-performance-when-loading"></a><a name="mfc_optimization"></a> 読み込み時にクライアント アプリケーションのパフォーマンスを向上させるにはどのような最適化手法を使えばよいですか。

使用する DLL が MFC に静的にリンクされている標準 MFC DLL である場合、それを MFC に動的にリンクされている標準 MFC DLL に変更すると、ファイル サイズが小さくなります。

DLL にエクスポートされた関数が多数ある場合は、.def ファイルを使用して ( **`__declspec(dllexport)`** を使用するのではなく) 関数をエクスポートし、エクスポートされた各関数に対して .def ファイルの [NONAME 属性](exporting-functions-from-a-dll-by-ordinal-rather-than-by-name.md)を使用します。 NONAME 属性を指定すると、関数名ではなく序数値だけが DLL のエクスポート テーブルに格納され、ファイル サイズが小さくなります。

アプリケーションに暗黙的にリンクされる DLL は、アプリケーションの読み込み時に読み込まれます。 読み込み時のパフォーマンスを向上させるには、その DLL を複数の DLL に分割してみてください。 呼び出し元のアプリケーションが読み込みの直後に必要とするすべての関数を 1 つの DLL に配置し、呼び出し元のアプリケーションがその DLL に暗黙的にリンクするようにします。 呼び出し元のアプリケーションがすぐには必要としないその他の関数を別の DLL に配置し、アプリケーションがその DLL に明示的にリンクするようにします。 詳細については、[実行可能ファイルと DLL のリンク](linking-an-executable-to-a-dll.md#determining-which-linking-method-to-use)に関する記事をご覧ください。

## <a name="there39s-a-memory-leak-in-my-regular-mfc-dll-but-my-code-looks-fine-how-can-i-find-the-memory-leak"></a><a name="memory_leak"></a> 標準 MFC DLL でメモリ リークが発生しましたが、自分のコードは正常に見えます。 メモリ リークを検出するにはどうすればよいですか。

メモリ リークの考えられる原因の 1 つは、メッセージ ハンドラー関数内で使用される一時オブジェクトが MFC によって作成されることです。 MFC アプリケーションでは、メッセージの処理の間に呼び出される `CWinApp::OnIdle()` 関数内で、これらの一時オブジェクトが自動的にクリーンアップされます。 しかし、MFC ダイナミックリンク ライブラリ (DLL) では、`OnIdle()` 関数は自動的には呼び出されません。 その結果、一時オブジェクトが自動的にクリーンアップされません。 一時オブジェクトをクリーンアップするには、DLL で定期的に `OnIdle(1)` を明示的に呼び出す必要があります。

## <a name="see-also"></a>関連項目

[Visual Studio での C/C++ Dll の作成](dlls-in-visual-cpp.md)
