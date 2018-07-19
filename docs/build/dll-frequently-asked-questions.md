---
title: MFC の DLL についてよく寄せられる質問 |Microsoft ドキュメント
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
ms.openlocfilehash: 6f5740989562aea799f3a49adfa464e2c460acb3
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32372511"
---
# <a name="dll-frequently-asked-questions"></a>DLL に関してよく寄せられる質問  
  
次は、Dll に関する質問 (FAQ) をよく寄せられます。  
    
-   [MFC DLL に複数のスレッドを作成できますか。](#mfc_multithreaded_1)  

-   [マルチ スレッド アプリケーションは別のスレッド内の MFC DLL にアクセスできますか。](#mfc_multithreaded_2)  
  
-   [MFC クラスまたは MFC DLL 内で使用できない機能はありますか。](#mfc_prohibited_classes)  
  
-   [どのような最適化の手法を読み込むときに、クライアント アプリケーションのパフォーマンスを向上させるために使用する必要がありますか。](#mfc_optimization)  
  
-   [標準 MFC DLL にメモリ リークが正常に見えるコード。メモリ リークを検出する方法は?](#memory_leak)  

## <a name="mfc_multithreaded_1"></a> MFC DLL に複数のスレッドを作成できますか。  
  
初期化中に、MFC DLL を安全の作成を除く複数のスレッドの Win32 スレッド ローカル ストレージ (TLS) などの関数を使用する限り、 **TlsAlloc**スレッド ローカル ストレージを割り当てることです。 ただし、MFC DLL を使用して場合 **_declspec**をスレッド ローカル ストレージを割り当て、クライアント アプリケーションは暗黙的にリンクされて DLL です。 クライアント アプリケーションが DLL への呼び出しに明示的にリンク**LoadLibrary** DLL は正常に読み込まれません。 MFC Dll 内の複数のスレッドの作成の詳細については、サポート技術情報の記事、"[prb]:: 呼び出し LoadLibrary() に負荷が DLL がする静的 TLS"(Q118816) を参照してください。 Dll 内のスレッド ローカル変数の詳細については、次を参照してください。[スレッド](../cpp/thread.md)です。
  
 起動中に、新しい MFC スレッドを作成する MFC DLL では、アプリケーションによって読み込まれるときの応答を停止します。 これは、スレッドが呼び出すことによって作成されるたびにも含まれます。`AfxBeginThread`または`CWinThread::CreateThread`内。  
  
-   `InitInstance`の`CWinApp`-標準 MFC DLL 内のオブジェクトを派生します。  
  
-   指定された`DllMain`または**まず**正規 MFC DLL 内の関数。  
  
-   指定された`DllMain`または**まず**MFC 拡張 DLL で機能します。  
  
 初期化中にスレッドを作成の詳細については、サポート技術情報の記事、「[prb]:: ことはできませんを作成、MFC スレッド中に DLL の起動」(Q142243) を参照してください。  
  
## <a name="mfc_multithreaded_2"></a> マルチ スレッド アプリケーションは別のスレッド内の MFC DLL にアクセスできますか。
マルチ スレッド アプリケーションでは、MFC と動的にリンクする標準の MFC Dll と MFC 拡張 Dll を異なるスレッドからアクセスできます。 Visual c version 4.2 では、アプリケーションは、アプリケーションで作成された複数のスレッドから MFC と静的にリンクする標準の MFC Dll にアクセスします。  
  
 前のバージョン 4.2、外部スレッドを 1 つだけに MFC と静的にリンクされるレギュラー MFC DLL にアタッチでした。 サポート技術情報の記事を参照してください (Visual C バージョン 4.2) より前の複数のスレッドから MFC と静的にリンクする正規の MFC Dll へのアクセス制限の詳細については、"複数のスレッドおよび MFC にリンクできます"(Q122676)。  
  
 USRDLL という用語は、Visual C のドキュメントでは使用されなくに注意してください。 MFC と静的にリンクされている標準 MFC DLL は、これまでの USRDLL と同じ特性を持ちます。  


## <a name="mfc_prohibited_classes"></a> MFC クラスまたは MFC DLL 内で使用できない機能はありますか。
拡張 Dll を使用して、 `CWinApp`-クライアント アプリケーションのクラスを派生します。 ない独自`CWinApp`-クラスを派生します。  
  
標準の MFC Dll が必要、`CWinApp`の MFC アプリケーションのように、クラスとそのアプリケーション クラスの 1 つのオブジェクトを派生します。 異なり、 `CWinApp` 、アプリケーションのオブジェクト、 `CWinApp` DLL のオブジェクトには、メイン メッセージ ポンプがありません。  
  
 ため、`CWinApp::Run`メカニズムは、DLL には適用されません、アプリケーションはメイン メッセージ ポンプを所有します。 DLL は、モードレス ダイアログ ボックスを開くかは、独自のメイン フレーム ウィンドウがあり場合、アプリケーションのメイン メッセージ ポンプを呼び出して、DLL のエクスポート ルーチンを呼び出す必要があります、 `CWinApp::PreTranslateMessage` DLL のアプリケーション オブジェクトのメンバー関数。  

## <a name="mfc_optimization"></a> どのような最適化の手法を使用するクライアント アプリケーションを向上させるために&#39;秒のパフォーマンスを読み込むときにしますか?
DLL が MFC では、標準への変更に静的にリンクされている標準 MFC DLL の場合は、MFC と動的にリンクする MFC DLL はファイル サイズを減らします。  
  
 DLL のエクスポート関数の数が多い場合は、.def ファイルを使用して関数をエクスポートする (を使用せずに**方式**) .def ファイルを使用して[NONAME 属性](../build/exporting-functions-from-a-dll-by-ordinal-rather-than-by-name.md)ごとに関数をエクスポートします。 NONAME 属性によって、序数値だけと、ファイルのサイズを削減でき、DLL のエクスポート テーブルに格納される関数名ではありません。  
  
 アプリケーションに暗黙的にリンクされている Dll は、アプリケーションの読み込み時に読み込まれます。 読み込むときに、パフォーマンスを向上するには、DLL を異なる Dll に分割してみてください。 1 つの DLL の読み込み後すぐに呼び出し元アプリケーションに必要なすべての機能を配置し、呼び出し元アプリケーションの DLL を暗黙的にリンクします。 呼び出し元のアプリケーションがすぐ必要がないその他の関数を別の DLL に配置しがアプリケーションに明示的にリンクする DLL です。 詳細については、次を参照してください。[リンク方式の使い分け](../build/linking-an-executable-to-a-dll.md#determining-which-linking-method-to-use)です。  

## <a name="memory_leak"></a> ある&#39;s マイ コードでは、標準 MFC DLL 内のメモリ リークは正常です。 メモリ リークを検出する方法は?  
  
メモリ リークの原因の 1 つは、MFC メッセージ ハンドラー関数内部で使用される一時オブジェクトで作成します。 MFC アプリケーションでこれらの一時オブジェクトが自動的にクリーンアップで、`CWinApp::OnIdle()`メッセージの処理の間に呼び出される関数。 ただし、MFC のダイナミック リンク ライブラリ (Dll) では、`OnIdle()`関数は自動的に呼び出されません。 その結果、一時オブジェクトが自動的にクリーンアップされません。 一時オブジェクトをクリーンアップする DLL を呼び出す必要があります明示的に`OnIdle(1)`定期的にします。  
  
## <a name="see-also"></a>関連項目  
 [Visual C++ の DLL](../build/dlls-in-visual-cpp.md)