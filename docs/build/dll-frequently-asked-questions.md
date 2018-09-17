---
title: MFC DLL についてよく寄せられる質問 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- troubleshooting [C++], DLLs
- DLLs [C++], frequently asked questions
- FAQs [C++], DLLs
ms.assetid: 09dd068e-fc33-414e-82f7-289c70680256
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bc42cd1eab4f19c8184ad500b4a4a1871747d6aa
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45713090"
---
# <a name="dll-frequently-asked-questions"></a>DLL に関してよく寄せられる質問

次はいくつかに関してよく寄せられる質問 (FAQ) の Dll。

- [MFC DLL に複数のスレッドを作成できますか。](#mfc_multithreaded_1)

- [マルチ スレッド アプリケーションは別のスレッド内の MFC DLL にアクセスできますか。](#mfc_multithreaded_2)

- [MFC クラスまたは MFC DLL では使用できません関数はありますか。](#mfc_prohibited_classes)

- [どのような最適化手法を読み込むときに、クライアント アプリケーションのパフォーマンスを向上させるために使用する必要がありますか。](#mfc_optimization)

- [レギュラー MFC DLL でメモリ リークがあるが、正常に見えるコード。メモリ リークを検出する方法はありますか](#memory_leak)

## <a name="mfc_multithreaded_1"></a> MFC DLL に複数のスレッドを作成できますか。

初期化中に、MFC の DLL を安全に作成できます複数のスレッド Win32 スレッド ローカル ストレージ (TLS) などの関数を使用する限り、点を除いて**TlsAlloc**スレッド ローカル ストレージを割り当てる。 ただし、MFC の DLL を使用している場合 **_declspec**スレッド ローカル ストレージを割り当てるにクライアント アプリケーションの暗黙的にリンクする DLL です。 クライアント アプリケーションが DLL への呼び出しに明示的にリンク**LoadLibrary** DLL は正常に読み込まれません。 MFC Dll 内の複数のスレッドを作成する方法の詳細については、サポート技術情報の記事、"PRB:: 呼び出し LoadLibrary() に負荷を DLL ことが静的 TLS"(Q118816) を参照してください。 Dll 内のスレッド ローカル変数の詳細については、次を参照してください。[スレッド](../cpp/thread.md)します。

スタートアップ中に、新しい MFC スレッドを作成する MFC DLL では、アプリケーションによって読み込まれるときの応答を停止します。 これは、スレッドが呼び出すことによって作成されるたびにも含まれます。`AfxBeginThread`または`CWinThread::CreateThread`内。

- `InitInstance`の`CWinApp`-レギュラー MFC DLL 内のオブジェクトを派生します。

- 指定された`DllMain`または**まず**レギュラー MFC DLL の関数。

- 指定された`DllMain`または**まず**MFC 拡張 DLL で機能します。

初期化中にスレッドを作成する方法の詳細については、サポート技術情報の記事、"PRB:: ことはできませんを作成する MFC スレッド中に DLL Startup"(Q142243) を参照してください。

## <a name="mfc_multithreaded_2"></a> マルチ スレッド アプリケーションは別のスレッド内の MFC DLL にアクセスできますか。

マルチ スレッド アプリケーションでは、MFC と動的にリンクされるレギュラー MFC Dll と MFC 拡張 Dll を別のスレッドからアクセスできます。 Visual c バージョン 4.2 では、アプリケーションは、アプリケーションで作成された複数のスレッドから MFC を静的にリンクされるレギュラー MFC Dll にアクセスします。

前のバージョン 4.2 では、外部の 1 つだけのスレッドは、MFC と静的にリンクされるレギュラー MFC DLL を添付できます。 (Visual C version 4.2) より前の複数のスレッドから MFC と静的にリンクされるレギュラー MFC Dll へのアクセスの制限の詳細については、サポート技術情報の記事を参照してください。"複数のスレッドと MFC にリンクできます"(Q122676)。

USRDLL という用語は、Visual C のドキュメントでは使用されなくに注意してください。 MFC と静的にリンクされるレギュラー MFC DLL は、USRDLL と同じ特性を持ちます。

## <a name="mfc_prohibited_classes"></a> MFC クラスまたは MFC DLL では使用できません関数はありますか。

拡張 Dll の使用、 `CWinApp`-クライアント アプリケーションのクラスを派生します。 ない独自`CWinApp`-クラスを派生します。

レギュラー MFC Dll が必要、`CWinApp`の MFC アプリケーションのように、クラスとそのアプリケーション クラスの 1 つのオブジェクトを派生します。 異なり、 `CWinApp` 、アプリケーションのオブジェクト、 `CWinApp` DLL のオブジェクトには、メイン メッセージ ポンプはありません。

ため、`CWinApp::Run`メカニズムは、DLL には適用されません、アプリケーションは、メイン メッセージ ポンプを所有しています。 DLL は、モードレス ダイアログ ボックスが表示されますまたは、独自のメイン フレーム ウィンドウには、アプリケーションのメイン メッセージ ポンプを呼び出して、DLL のエクスポート ルーチンを呼び出す必要があります、 `CWinApp::PreTranslateMessage` DLL のアプリケーション オブジェクトのメンバー関数。

## <a name="mfc_optimization"></a> どのような最適化手法、クライアント アプリケーションを向上させるために使用する必要があります&#39;秒のパフォーマンスを読み込むときにしますか?

DLL が MFC では、標準に変更することに静的にリンクされるレギュラー MFC DLL の場合、MFC と動的にリンクされている MFC DLL は、ファイル サイズを減らします。

DLL のエクスポートされた関数の数が多い場合は、.def ファイルを使用して関数をエクスポートする (を使用してではなく**方式**) .def ファイルを使用して[NONAME 属性](../build/exporting-functions-from-a-dll-by-ordinal-rather-than-by-name.md)各関数をエクスポートします。 NONAME 属性は、序数値のみと、ファイル サイズが縮小 DLL のエクスポート テーブルに格納される関数名ではなくです。

アプリケーションの読み込み時に、アプリケーションに暗黙的にリンクされている Dll が読み込まれます。 読み込むときに、パフォーマンスを向上するには、DLL を異なる Dll に分割することをお試しください。 1 つの DLL の読み込み後すぐに呼び出し元アプリケーションに必要なすべての関数を配置し、呼び出し元のアプリケーションをその DLL を暗黙的にリンクします。 別の DLL を呼び出し元のアプリケーションが直ちに必要はなく、他の関数を追加しがアプリケーションに明示的にリンクする DLL です。 詳細については、次を参照してください。[リンクを使用する方法を決定](../build/linking-an-executable-to-a-dll.md#determining-which-linking-method-to-use)します。

## <a name="memory_leak"></a> ある&#39;s レギュラー MFC DLL が自分のコードでのメモリ リークが問題ないようです。 メモリ リークを検出する方法はありますか

メモリ リークの考えられる原因の 1 つは、MFC メッセージ ハンドラー関数の内部で使用される一時オブジェクトで作成します。 MFC アプリケーションでこれらの一時オブジェクトが自動的にクリーンアップで、`CWinApp::OnIdle()`メッセージの処理の間に呼び出される関数。 ただし、MFC のダイナミック リンク ライブラリ (Dll) で、`OnIdle()`関数は自動的に呼び出されません。 その結果、一時オブジェクトが自動的にクリーンアップされません。 一時オブジェクトをクリーンアップする DLL を呼び出す必要があります明示的に`OnIdle(1)`定期的にします。

## <a name="see-also"></a>関連項目

[Visual C++ の DLL](../build/dlls-in-visual-cpp.md)