---
title: MFC DLL に関してよく寄せられる質問
ms.date: 05/06/2019
helpviewer_keywords:
- troubleshooting [C++], DLLs
- DLLs [C++], frequently asked questions
- FAQs [C++], DLLs
ms.assetid: 09dd068e-fc33-414e-82f7-289c70680256
ms.openlocfilehash: 9108aaf3fcface847b0391455a2aecd4d45658c4
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2020
ms.locfileid: "78856951"
---
# <a name="dll-frequently-asked-questions"></a>DLL に関してよく寄せられる質問

Dll に関してよく寄せられる質問 (FAQ) を次に示します。

- [MFC DLL は複数のスレッドを作成できますか。](#mfc_multithreaded_1)

- [マルチスレッドアプリケーションは、異なるスレッドの MFC DLL にアクセスできますか。](#mfc_multithreaded_2)

- [Mfc DLL で使用できない MFC クラスまたは関数はありますか。](#mfc_prohibited_classes)

- [読み込み時にクライアントアプリケーションのパフォーマンスを向上させるためにどのような最適化手法を使用する必要がありますか。](#mfc_optimization)

- [通常の MFC DLL にはメモリリークがありますが、コードは正常に見えます。メモリリークを検出するにはどうすればよいですか。](#memory_leak)

## <a name="mfc_multithreaded_1"></a>MFC DLL は複数のスレッドを作成できますか。

初期化時以外に、MFC DLL は、 **TlsAlloc**などの Win32 スレッドローカルストレージ (TLS) 関数を使用してスレッドローカルストレージを割り当てることができる限り、複数のスレッドを安全に作成できます。 ただし、MFC DLL が **__declspec (thread)** を使用してスレッドローカルストレージを割り当てる場合、クライアントアプリケーションは、DLL に暗黙的にリンクされている必要があります。 クライアントアプリケーションが DLL に明示的にリンクしている場合は、 **LoadLibrary**を呼び出すと dll が正常に読み込まれません。 Dll のスレッドローカル変数の詳細については、「 [thread](../cpp/thread.md)」を参照してください。

起動時に新しい MFC スレッドを作成する MFC DLL は、アプリケーションによって読み込まれると、応答を停止します。 これには、`AfxBeginThread` または内の `CWinThread::CreateThread` を呼び出してスレッドが作成されるたびに、次のものが含まれます。

- 通常の MFC DLL 内の `CWinApp`派生オブジェクトの `InitInstance`。

- 標準の MFC DLL 内の指定された `DllMain` または**Rawdllmain**関数。

- MFC 拡張 DLL 内の指定された `DllMain` または**Rawdllmain**関数。

## <a name="mfc_multithreaded_2"></a>マルチスレッドアプリケーションは、異なるスレッドの MFC DLL にアクセスできますか。

マルチスレッドアプリケーションは、さまざまなスレッドから MFC および MFC の拡張 Dll に動的にリンクする通常の MFC Dll にアクセスできます。 アプリケーションでは、アプリケーションで作成された複数のスレッドから MFC に静的にリンクする通常の MFC Dll にアクセスできます。

## <a name="mfc_prohibited_classes"></a>Mfc DLL で使用できない MFC クラスまたは関数はありますか。

拡張 Dll は、クライアントアプリケーションの `CWinApp`派生クラスを使用します。 独自の `CWinApp`派生クラスを持つことはできません。

通常の MFC Dll には、MFC アプリケーションと同様に、`CWinApp`派生クラスとそのアプリケーションクラスの1つのオブジェクトが必要です。 アプリケーションの `CWinApp` オブジェクトとは異なり、DLL の `CWinApp` オブジェクトにはメインメッセージポンプがありません。

`CWinApp::Run` メカニズムは DLL には適用されないため、アプリケーションはメインメッセージポンプを所有していることに注意してください。 DLL がモードレスダイアログボックスを開く場合、または独自のメインフレームウィンドウがある場合、アプリケーションのメインメッセージポンプは、dll によってエクスポートされたルーチンを呼び出す必要があります。このルーチンは、dll のアプリケーションオブジェクトの `CWinApp::PreTranslateMessage` メンバー関数を呼び出します。

## <a name="mfc_optimization"></a>読み込み時にクライアントアプリケーション&#39;のパフォーマンスを向上させるためにどのような最適化手法を使用する必要がありますか。

DLL が MFC に静的にリンクされている通常の MFC DLL である場合、MFC に動的にリンクされている通常の mfc DLL に変更すると、ファイルサイズが小さくなります。

DLL にエクスポートされた関数が多数ある場合は、.def ファイルを使用して ( **__declspec (dllexport)** を使用するのではなく) 関数をエクスポートし、エクスポートされた各関数で .def ファイルの "[属性](exporting-functions-from-a-dll-by-ordinal-rather-than-by-name.md)" を使用します。 "/" 属性を指定すると、DLL のエクスポートテーブルに格納される序数値だけでなく、ファイルサイズが小さくなります。

アプリケーションに暗黙的にリンクされる Dll は、アプリケーションの読み込み時に読み込まれます。 読み込み時のパフォーマンスを向上させるには、DLL を別の Dll に分割してみてください。 呼び出し元のアプリケーションが1つの DLL に読み込んだ直後に必要なすべての関数を配置し、呼び出し元のアプリケーションがその DLL に暗黙的にリンクするようにします。 呼び出し元のアプリケーションが必要としない他の関数を別の DLL に配置し、アプリケーションがその DLL に明示的にリンクするようにします。 詳細については、「[実行可能ファイルを DLL にリンクする](linking-an-executable-to-a-dll.md#determining-which-linking-method-to-use)」を参照してください。

## <a name="memory_leak"></a>通常&#39;の MFC DLL にはメモリリークがありますが、コードは問題ありません。 メモリリークを検出するにはどうすればよいですか。

メモリリークの考えられる原因の1つは、メッセージハンドラー関数内で使用される一時オブジェクトを MFC が作成することです。 MFC アプリケーションでは、これらの一時オブジェクトは、メッセージの処理の間に呼び出される `CWinApp::OnIdle()` 関数で自動的にクリーンアップされます。 ただし、MFC ダイナミックリンクライブラリ (Dll) では、`OnIdle()` 関数は自動的には呼び出されません。 その結果、一時オブジェクトは自動的にクリーンアップされません。 一時オブジェクトをクリーンアップするには、DLL が明示的に `OnIdle(1)` を呼び出す必要があります。

## <a name="see-also"></a>参照

[Visual Studio での C/C++ Dll の作成](dlls-in-visual-cpp.md)
