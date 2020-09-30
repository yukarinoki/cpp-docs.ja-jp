---
title: Windows ランタイム C++ テンプレート ライブラリ (WRL)
ms.date: 11/04/2016
ms.topic: overview
ms.assetid: b915afce-553b-44a7-b8dc-0ab601758eb0
ms.openlocfilehash: 12bda00d6687340fbddfb8f81bbb83b6c2bd98a6
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/29/2020
ms.locfileid: "91509799"
---
# <a name="windows-runtime-c-template-library-wrl"></a>Windows ランタイム C++ テンプレート ライブラリ (WRL)

Windows ランタイム C++ テンプレート ライブラリ (WRL) は、Windows ランタイム コンポーネントを作成および使用するための低レベルの手段を提供するテンプレート ライブラリです。

> [!NOTE]
> WRL は、C++/WinRT で置き換えられました。これは Windows ランタイム Api 向けの標準 C++ 17 言語の射影です。 C++/WinRT は、Windows 10 SDK のバージョン 1803 以降で使用できます。 C++/WinRT は、完全にヘッダーファイルに実装され、最新の Windows API へのファーストクラスのアクセスを提供するように設計されています。
>
> C++/WinRT では、標準に準拠した C++ 17 コンパイラを使用して Windows ランタイム Api を使用し、作成することができます。 C++/WinRT は通常、より優れたパフォーマンスを発揮し、Windows ランタイムの他の言語オプションよりも小さなバイナリを生成します。 C++/CX と WRL は引き続きサポートされますが、新しいアプリケーションでは C++/WinRT を使用することを強くお勧めします。 詳細については、「[C++/WinRT](/windows/uwp/cpp-and-winrt-apis/index)」を参照してください。

## <a name="benefits"></a>メリット

Windows ランタイム C++ テンプレートライブラリを使用すると、コンポーネントオブジェクトモデル (COM) コンポーネントの実装と使用をより簡単に行うことができます。 オブジェクトの有効期間を管理するための参照カウントや、操作が成功したか失敗したかを判断するための HRESULT 値のテストなどのハウスキーピング手法が用意されています。 Windows ランタイム C++ テンプレートライブラリを正常に使用するには、次の規則と手法に注意する必要があります。

C++/CX は、Windows ランタイムコンポーネントを使用するための高度な言語ベースの方法です。 Windows ランタイム C++ テンプレートライブラリと C++/CX の両方で、自動的にハウスキーピングタスクを自動的に実行することによって、Windows ランタイムのコードを簡単に記述できます。

Windows ランタイム C++ テンプレートライブラリと C++/CX では、さまざまな利点があります。 ここでは、C++/CX ではなく Windows ランタイム C++ テンプレートライブラリを使用することが必要になる可能性がある理由をいくつか示します。

- Windows ランタイム C++ テンプレートライブラリでは、Windows ランタイムアプリケーションバイナリインターフェイス (ABI) に対する抽象化がほとんど追加されていないため、基になるコードを制御して Windows ランタイム Api をより適切に作成または使用することができます。

- C++/CX は、COM HRESULT 値を例外として表します。 COM を使用するコードベース、または例外を使用しないコードベースを継承した場合は、例外を使用する必要がないため、Windows ランタイム C++ テンプレートライブラリが Windows ランタイムを操作するより自然な方法であることがわかります。

   > [!NOTE]
   > Windows ランタイム C++ テンプレートライブラリでは HRESULT 値が使用され、例外はスローされません。 さらに、Windows ランタイム C++ テンプレートライブラリでは、スマートポインターと RAII パターンを使用して、アプリケーションコードが例外をスローしたときにオブジェクトが正しく破棄されることを保証します。 スマートポインターと RAII の詳細については、「 [スマートポインター](../../cpp/smart-pointers-modern-cpp.md) と [オブジェクトのリソース (RAII)](../../cpp/object-lifetime-and-resource-management-modern-cpp.md)」を参照してください。

- Windows ランタイム C++ テンプレートライブラリの目的と設計は、COM オブジェクトのプログラミングを簡略化する、テンプレートベースの C++ クラスのセットである Active Template Library (ATL) によって作成されています。 Windows ランタイム C++ テンプレートライブラリは標準 C++ を使用して Windows ランタイムをラップするため、ATL で記述された多くの既存の COM コンポーネントを Windows ランタイムに簡単に移植して操作できます。 ATL が既にわかっている場合は、Windows ランタイム C++ テンプレートライブラリのプログラミングが簡単であることがわかります。

## <a name="getting-started"></a>作業の開始

ここでは、Windows ランタイム C++ テンプレートライブラリをすぐに使用するために役立つリソースをいくつか紹介します。

[Windows ランタイム ライブラリ (WRL)](https://channel9.msdn.com/Events/Windows-Camp/Developing-Windows-8-Metro-style-apps-in-Cpp/The-Windows-Runtime-Library-WRL-)<br/>
この Channel 9 のビデオでは、Windows ランタイム C++ テンプレートライブラリを使用してユニバーサル Windows プラットフォーム (UWP) アプリを記述する方法と、Windows ランタイムコンポーネントを作成および使用する方法について説明します。

[方法: Windows ランタイム コンポーネントをアクティブ化し使用する](how-to-activate-and-use-a-windows-runtime-component-using-wrl.md)<br/>
Windows ランタイム C++ テンプレートライブラリを使用して Windows ランタイムを初期化し、Windows ランタイムコンポーネントをアクティブ化して使用する方法について説明します。

[方法: 非同期操作を完了する](how-to-complete-asynchronous-operations-using-wrl.md)<br/>
Windows ランタイム C++ テンプレートライブラリを使用して非同期操作を開始し、操作の完了時に処理を実行する方法について説明します。

[方法: イベントを処理する](how-to-handle-events-using-wrl.md)<br/>
Windows ランタイム C++ テンプレートライブラリを使用して、Windows ランタイムオブジェクトのイベントをサブスクライブおよび処理する方法について説明します。

[チュートリアル: WRL および Media Foundation を使用した UWP アプリの作成](walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation.md)<br/>
[Microsoft メディアファンデーション](/windows/win32/medfound/microsoft-media-foundation-sdk)を使用する UWP アプリを作成する方法について説明します。

[方法: 従来の COM コンポーネントを作成する](how-to-create-a-classic-com-component-using-wrl.md)<br/>
Windows ランタイム C++ テンプレートライブラリを使用して基本的な COM コンポーネントを作成する方法と、デスクトップアプリから COM コンポーネントを登録して使用する基本的な方法について説明します。

[方法: WRL コンポーネントを直接インスタンス化する](how-to-instantiate-wrl-components-directly.md)<br/>
[Microsoft::WRL::Make](make-function.md) と [Microsoft::WRL::Details::MakeAndInitialize](makeandinitialize-function.md) 関数を使用して、コンポーネントを定義するモジュールからそのコンポーネントをインスタンス化する方法について説明します。

[方法: winmdidl.exe と midlrt.exe を使用して、Windows メタデータから .h ファイルを作成する](use-winmdidl-and-midlrt-to-create-h-files-from-windows-metadata.md)<br/>
.winmd メタデータから IDL ファイルを作成して、WRL からカスタム Windows ランタイム コンポーネントを使用する方法を示します。

[チュートリアル: タスクと XML HTTP 要求を使用した接続](../../parallel/concrt/walkthrough-connecting-using-tasks-and-xml-http-requests.md)<br/>
[IXMLHTTPRequest2](/windows/win32/api/msxml6/nn-msxml6-ixmlhttprequest2)インターフェイスと[IXMLHTTPRequest2Callback](/windows/win32/api/msxml6/nn-msxml6-ixmlhttprequest2callback)インターフェイスをタスクと共に使用して、UWP アプリで HTTP GET 要求と POST 要求を web サービスに送信する方法について説明します。

[Bing マップ トリップ オプティマイザーのサンプル](https://github.com/Microsoft/VCSamples/tree/master/VC2012Samples/Windows%208%20samples/C%2B%2B/Windows%208%20app%20samples)<br/>
`HttpRequest`「チュートリアル: 完全な UWP アプリのコンテキストでの[タスクと XML HTTP 要求を使用した接続](../../parallel/concrt/walkthrough-connecting-using-tasks-and-xml-http-requests.md)」で定義されているクラスを使用します。

[C++ サンプルを使用した Windows ランタイム DLL コンポーネントの作成](https://github.com/Microsoft/VCSamples/tree/master/VC2012Samples/Windows%208%20samples/C%2B%2B/Windows%208%20app%20samples)<br/>
Windows ランタイム C++ テンプレートライブラリを使用してインプロセス DLL コンポーネントを作成し、C++/CX、JavaScript、および C# から使用する方法について説明します。

[DirectX マーブル メイズ ゲームのサンプル](/samples/microsoft/windows-appsample-marble-maze/directx-marble-maze-game-sample/)<br/>
Windows ランタイム C++ テンプレートライブラリを使用して、完全な3-d ゲームのコンテキストで DirectX やメディアファンデーションなどの COM コンポーネントの有効期間を管理する方法を示します。

[デスクトップアプリからのトースト通知](/windows/uwp/design/shell/tiles-and-notifications/toast-desktop-apps)<br/>
デスクトップアプリからトースト通知を送信する方法について説明します。

## <a name="windows-runtime-c-template-library-compared-to-atl"></a>Windows ランタイム C++ テンプレートライブラリと ATL の比較

Windows ランタイム C++ テンプレートライブラリは、小規模で高速な COM オブジェクトを作成するために使用できるため、Active Template Library (ATL) に似ています。 Windows ランタイム C++ テンプレートライブラリと ATL には、モジュール内のオブジェクトの定義、インターフェイスの明示的な登録、およびファクトリを使用したオブジェクトのオープン作成などの概念も共通しています。 ATL に慣れている場合は、Windows ランタイム C++ テンプレートライブラリを使用することをお勧めします。

Windows ランタイム C++ テンプレートライブラリでは、UWP アプリに必要な COM 機能がサポートされています。 したがって、以下のような COM 機能の直接サポートを省略した ATL とは異なっています。

- aggregation

- ストックの実装

- デュアル インターフェイス (`IDispatch`)

- 標準的な列挙子インターフェイス

- 接続ポイント

- ティアオフ インターフェイス

- OLE 埋め込み

- ActiveX コントロール

- COM+

## <a name="concepts"></a>概念

Windows ランタイム C++ テンプレートライブラリには、いくつかの基本的な概念を表す型が用意されています。 以下のセクションでは、これらの型について説明します。

### <a name="comptr"></a>ComPtr

[ComPtr](comptr-class.md) は、テンプレート パラメーターで指定されたインターフェイスを表す *スマート ポインター* 型です。 インターフェイスから派生したオブジェクトのメンバーにアクセスできる変数を宣言するには、 `ComPtr` を使用します。 `ComPtr` は、基になるインターフェイス ポインターの参照カウントを維持し、参照カウントがゼロになるとそのインターフェイスを自動的に解放します。

### <a name="runtimeclass"></a>RuntimeClass

[RuntimeClass](runtimeclass-class.md) は、指定したインターフェイスのセットを継承する、インスタンス化されたクラスを表します。 `RuntimeClass`オブジェクトは、1つまたは複数の WINDOWS ランタイム COM インターフェイスのサポートと、コンポーネントへの弱い参照の組み合わせを提供できます。

### <a name="module"></a>モジュール

[Module](module-class.md) は、関連するオブジェクトから成るコレクションを表します。 `Module` オブジェクトは、オブジェクトを作成するクラス ファクトリと、他のアプリケーションからオブジェクトを使用できるようにする登録を管理します。

### <a name="callback"></a>コールバック

["Callback (コールバック)"](callback-function-wrl.md) 関数は、メンバー関数がイベント ハンドラー (コールバック メソッド) であるオブジェクトを作成します。 非同期操作を書き込むには、 `Callback` 関数を使用します。

### <a name="eventsource"></a>EventSource

[EventSource](eventsource-class.md) は、 *デリゲート* イベント ハンドラーを管理するために使用します。 Windows ランタイム C++ テンプレートライブラリを使用してデリゲートを実装し、を使用して `EventSource` デリゲートを追加、削除、および呼び出します。

### <a name="asyncbase"></a>AsyncBase

[Asyncbase](asyncbase-class.md) は、Windows ランタイムの非同期プログラミングモデルを表す仮想メソッドを提供します。 非同期操作の進行状況を開始、停止、または確認するカスタム クラスを作成するには、このクラス内のメンバーをオーバーライドします。

### <a name="ftmbase"></a>FtmBase

[FtmBase](ftmbase-class.md) は、フリー スレッドのマーシャラー オブジェクトを表します。 `FtmBase` は、グローバル インターフェイス テーブル (GIT) を作成し、マーシャリングとプロキシ オブジェクトの管理を支援します。

### <a name="weakref"></a>WeakRef

[WeakRef](weakref-class.md) は、アクセス可能またはアクセス不可能のオブジェクトを参照する *弱い参照*を表すスマート ポインター型です。 オブジェクトは、 `WeakRef` 従来の COM ではなく、Windows ランタイムによってのみ使用できます。

`WeakRef` オブジェクトは通常、外部スレッドまたは外部アプリケーションによって存在が制御されるオブジェクトを表します。 たとえば、 `WeakRef` オブジェクトを使用して、ファイル オブジェクトを参照できます。 そのファイルが開いている場合は、 `WeakRef` が有効になり、参照先ファイルにアクセスできます。 一方、そのファイルが閉じている場合は、 `WeakRef` が無効になり、そのファイルにアクセスできません。

## <a name="related-topics"></a>関連トピック

[カテゴリ別のキー Api](key-wrl-apis-by-category.md)\
プライマリ Windows ランタイム C++ テンプレートライブラリの型、関数、およびマクロについて取り上げます。

[「](wrl-reference.md)\
Windows ランタイム C++ テンプレートライブラリのリファレンス情報が含まれています。

[クイックリファレンス (C++/CX)](../../cppcx/quick-reference-c-cx.md)\
Windows ランタイムをサポートする C++/CX 機能について簡単に説明します。

[Visual C++ での Windows ランタイムコンポーネントの使用](/windows/uwp/winrt-components/walkthrough-creating-a-basic-windows-runtime-component-in-cpp-and-calling-it-from-javascript-or-csharp)\
C++/CX を使用して基本的な Windows ランタイムコンポーネントを作成する方法について説明します。
