---
title: Windows ランタイム C++ テンプレート ライブラリ (WRL) |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
ms.assetid: b915afce-553b-44a7-b8dc-0ab601758eb0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: bf101fdb0e93ef206ae61c29b636c973fa58a825
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42593978"
---
# <a name="windows-runtime-c-template-library-wrl"></a>Windows ランタイム C++ テンプレート ライブラリ (WRL)

Windows ランタイム C++ テンプレート ライブラリ (WRL) は、Windows ランタイム コンポーネントを作成および使用するための低レベルの手段を提供するテンプレート ライブラリです。

> [!NOTE]
> WRL は C + によって置き換え今すぐ/cli WinRT、標準 c++ 17 の言語プロジェクションの Windows ランタイム Api です。 C +/cli WinRT はバージョン 1803 以降から Windows 10 SDK で使用できます。 C +/cli WinRT がヘッダー ファイルで完全に実装し、最新の Windows API に最上級アクセスを提供するように設計します。

> C++/cli WinRT、両方を使用して標準に準拠した c++ 17 コンパイラを使用して Windows ランタイム Api を作成します。 C +/cli WinRT は通常、パフォーマンスが向上し、Windows ランタイムの他の言語オプションよりも小さいバイナリを生成します。 C + をサポートするために引き続き/cli CX および WRL、C + 新しいアプリケーションを使用するを強くお勧めしますが、/cli WinRT します。 詳細については、次を参照してください。 [C +/cli WinRT](https://docs.microsoft.com/windows/uwp/cpp-and-winrt-apis/index)します。

## <a name="benefits"></a>利点

Windows ランタイム C++ テンプレート ライブラリを使用するより簡単に実装し、コンポーネント オブジェクト モデル (COM) コンポーネントを使用できます。 参照カウント オブジェクトの有効期間を管理して、操作が成功または失敗するかどうかを判断する HRESULT 値をテストのような管理技法を提供します。 Windows ランタイム C++ テンプレート ライブラリを正常に使用するには、これらの規則や技法を慎重に従う必要があります。

C++/cli CX は Windows ランタイム コンポーネントを使用して、言語ベースの高度な方法です。 両方の Windows ランタイム C++ テンプレート ライブラリおよび C++/cli CX、あなたに代わってハウスキーピング タスクを自動的に実行することによって、Windows ランタイム用のコードの記述を簡略化します。

Windows ランタイム C++ テンプレート ライブラリと C + + CX さまざまな利点があります。 ここではいくつかの理由ではなく C + Windows ランタイム C++ テンプレート ライブラリを使用する/cli CX:

- Windows ランタイム C++ テンプレート ライブラリは経由で Windows ランタイム アプリケーション バイナリ インターフェイス (ABI) のほとんどの抽象化を追加します、向上を基になるコードを制御する機能を提供を作成または Windows ランタイム Api を使用しません。

- C + + CX は例外としての COM HRESULT 値を表します。 COM、または例外を使用しないものを使用してコード ベースを継承する場合、Windows ランタイム C++ テンプレート ライブラリの例外を使用する必要がないため、Windows ランタイムを使用する方法がより自然であることがあります。

   > [!NOTE]
   > Windows ランタイム C++ テンプレート ライブラリでは、HRESULT 値を使用し、例外をスローしません。 さらに、Windows ランタイム C++ テンプレート ライブラリを使用してスマート ポインターと RAII パターン、アプリケーション コードが例外をスローするときにオブジェクトが正しく破棄ことを保証するためです。 スマート ポインターと RAII に関する詳細については、次を参照してください。[スマート ポインター](../cpp/smart-pointers-modern-cpp.md)と[オブジェクト独自のリソース (RAII)](../cpp/objects-own-resources-raii.md)します。

- 目的と Windows ランタイム C++ テンプレート ライブラリの設計インスパイアされた Active Template Library (ATL) で COM オブジェクトのプログラミングを簡略化するテンプレート ベースの C++ クラスのセットです。 Windows ランタイム C++ テンプレート ライブラリでは、Windows ランタイムをラップする標準の C++ を使用するためより簡単にポートし、Windows ランタイムに ATL で記述された既存の多くの COM コンポーネントとの対話します。 ATL を既に知っている場合、Windows ランタイム C++ テンプレート ライブラリのプログラミングが容易でことがあります。

## <a name="getting-started"></a>作業の開始

Windows ランタイム C++ テンプレート ライブラリとすぐに作業を取得するのに役立つリソースを次に示します。

[Windows ランタイム ライブラリ (WRL)](http://channel9.msdn.com/Events/Windows-Camp/Developing-Windows-8-Metro-style-apps-in-Cpp/The-Windows-Runtime-Library-WRL-)  
この Channel 9 ビデオで詳細については、Windows ランタイム C++ テンプレート ライブラリがどのように役立つかを作成および Windows ランタイム コンポーネントを使用する方法とユニバーサル Windows プラットフォーム (UWP) アプリを記述します。

[方法: アクティブ化し、Windows ランタイム コンポーネントの使用](../windows/how-to-activate-and-use-a-windows-runtime-component-using-wrl.md)  
Windows ランタイム C++ テンプレート ライブラリを使用してライセンス認証し、Windows ランタイム コンポーネントを使用して、Windows ランタイムを初期化する方法を示しています。

[方法: 非同期操作を完了](../windows/how-to-complete-asynchronous-operations-using-wrl.md)  
Windows ランタイム C++ テンプレート ライブラリを使用して非同期操作を開始し、操作の完了時に、作業を実行する方法を示しています。

[方法: イベントを処理します。](../windows/how-to-handle-events-using-wrl.md)  
Windows ランタイム C++ テンプレート ライブラリを使用してサブスクライブして、Windows ランタイム オブジェクトのイベントを処理する方法を示しています。

[チュートリアル: WRL および Media Foundation を使用した UWP アプリの作成](../windows/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation.md)  
使用する UWP アプリを作成する方法について説明します[Microsoft メディア ファンデーション](http://msdn.microsoft.com/library/windows/apps/ms694197)します。

[方法: 従来の COM コンポーネントの作成](../windows/how-to-create-a-classic-com-component-using-wrl.md)  
Windows ランタイム C++ テンプレート ライブラリを使用して、基本的な COM コンポーネントと登録してデスクトップ アプリから COM コンポーネントを使用する基本的な方法を作成する方法を示します。

[方法: WRL コンポーネントを直接インスタンス化する](../windows/how-to-instantiate-wrl-components-directly.md)  
使用する方法について説明します、 [Microsoft::WRL::Make](../windows/make-function.md)と[Microsoft::WRL::Details::MakeAndInitialize](../windows/makeandinitialize-function.md)関数を定義しているモジュールからコンポーネントをインスタンス化します。

[方法: winmdidl.exe と midlrt.exe を使用して、Windows メタデータから .h ファイルを作成する](../windows/use-winmdidl-and-midlrt-to-create-h-files-from-windows-metadata.md)  
.winmd メタデータから IDL ファイルを作成して、WRL からカスタム Windows ランタイム コンポーネントを使用する方法を示します。

[チュートリアル: タスクおよび XML HTTP 要求を使用した接続](../parallel/concrt/walkthrough-connecting-using-tasks-and-xml-http-requests.md)  
使用する方法を示しています、 [IXMLHTTPRequest2](/previous-versions/windows/desktop/api/msxml6/nn-msxml6-ixmlhttprequest2)と[IXMLHTTPRequest2Callback](/previous-versions/windows/desktop/api/msxml6/nn-msxml6-ixmlhttprequest2callback) UWP アプリで web サービスに HTTP GET および POST 要求を送信するタスクとのインターフェイス。

[Bing マップ トリップ オプティマイザーのサンプル](http://code.msdn.microsoft.com/Bing-Maps-trip-optimizer-c4e037f7)  
使用して、`HttpRequest`クラスで定義されている[チュートリアル: を使用してタスクの接続および XML HTTP 要求](../parallel/concrt/walkthrough-connecting-using-tasks-and-xml-http-requests.md)完全な UWP アプリのコンテキストでします。

[C++ のサンプルを使用した Windows ランタイム DLL コンポーネントの作成](http://code.msdn.microsoft.com/windowsapps/Creating-a-Windows-Runtime-6c399797)  
Windows ランタイム C++ テンプレート ライブラリを使用してインプロセス DLL コンポーネントを作成し、C + から使用する方法を示しています。/cli/CX、JavaScript、および C# の場合。

[DirectX の marble maze ゲームのサンプル](http://code.msdn.microsoft.com/windowsapps/DirectX-Marble-Maze-Game-e4806345)  
Windows ランタイム C++ テンプレート ライブラリを使用して、3-D ゲーム全体のコンテキストで DirectX や Media Foundation などの COM コンポーネントの有効期間を管理する方法を示します。

[デスクトップ アプリのサンプルからのトースト通知を送信します。](http://code.msdn.microsoft.com/windowsdesktop/Sending-toast-notifications-71e230a2)  
Windows ランタイム C++ テンプレート ライブラリを使用してデスクトップ アプリからのトースト通知を操作する方法を示します。

## <a name="windows-runtime-c-template-library-compared-to-atl"></a>Windows ランタイム C++ テンプレートのライブラリと ATL の比較

Windows ランタイム C++ テンプレート ライブラリでは、使用して、小規模で高速な COM オブジェクトを作成するために Active Template Library (ATL) が似ています。 Windows ランタイム C++ テンプレート ライブラリ、ATL もモジュール、インターフェイスの明示的な登録内のオブジェクトの定義などの概念を共有し、ファクトリを使用してオブジェクトの作成を開きます。 ATL. を使い慣れている場合は、Windows ランタイム C++ テンプレート ライブラリを理解してあります可能性があります。

Windows ランタイム C++ テンプレート ライブラリには、UWP アプリに必要な COM 機能がサポートされています。 したがって、以下のような COM 機能の直接サポートを省略した ATL とは異なっています。

- 集計

- ストックの実装

- デュアル インターフェイス (`IDispatch`)

- 標準的な列挙子インターフェイス

- 接続ポイント

- ティアオフ インターフェイス

- OLE 埋め込み

- ActiveX コントロール

- COM+

## <a name="concepts"></a>概念

Windows ランタイム C++ テンプレート ライブラリは、いくつかの基本的な概念を表す型を提供します。 以下のセクションでは、これらの型について説明します。

### <a name="comptr"></a>ComPtr

[ComPtr](../windows/comptr-class.md)は、*スマート ポインター*テンプレート パラメーターで指定されているインターフェイスを表す型。 インターフェイスから派生したオブジェクトのメンバーにアクセスできる変数を宣言するには、 `ComPtr` を使用します。 `ComPtr` は、基になるインターフェイス ポインターの参照カウントを維持し、参照カウントがゼロになるとそのインターフェイスを自動的に解放します。

### <a name="runtimeclass"></a>RuntimeClass

[RuntimeClass](../windows/runtimeclass-class.md)インスタンス化された指定したインターフェイスのセットを継承するクラスを表します。 A`RuntimeClass`オブジェクトは、1 つまたは複数の Windows ランタイムの COM インターフェイス、またはコンポーネントへの弱い参照のサポートの組み合わせを提供できます。

### <a name="module"></a>Module

[モジュール](../windows/module-class.md)関連オブジェクトのコレクションを表します。 `Module` オブジェクトは、オブジェクトを作成するクラス ファクトリと、他のアプリケーションからオブジェクトを使用できるようにする登録を管理します。

### <a name="callback"></a>コールバック

[コールバック](../windows/callback-function-windows-runtime-cpp-template-library.md)関数オブジェクトをメンバー関数は、イベント ハンドラー (コールバック メソッド) を作成します。 非同期操作を書き込むには、 `Callback` 関数を使用します。

### <a name="eventsource"></a>EventSource

[EventSource](../windows/eventsource-class.md)を管理するために使用*委任*イベント ハンドラー。 Windows ランタイム C++ テンプレート ライブラリを使用してデリゲートを実装し、使用`EventSource`を追加するには、削除、およびデリゲートを呼び出します。

### <a name="asyncbase"></a>AsyncBase

[AsyncBase](../windows/asyncbase-class.md) Windows ランタイムの非同期プログラミング モデルを表す仮想メソッドを提供します。 非同期操作の進行状況を開始、停止、または確認するカスタム クラスを作成するには、このクラス内のメンバーをオーバーライドします。

### <a name="ftmbase"></a>FtmBase

[FtmBase](../windows/ftmbase-class.md)フリー スレッド マーシャラー オブジェクトを表します。 `FtmBase` は、グローバル インターフェイス テーブル (GIT) を作成し、マーシャリングとプロキシ オブジェクトの管理を支援します。

### <a name="weakref"></a>WeakRef

[WeakRef](../windows/weakref-class.md)を表すスマート ポインター型には、*弱い参照*、またはアクセスできない可能性がありますのあるオブジェクトを参照します。 A `WeakRef` Windows ランタイムのみで、クラシック COM でないオブジェクトを使用できます

`WeakRef` オブジェクトは通常、外部スレッドまたは外部アプリケーションによって存在が制御されるオブジェクトを表します。 たとえば、 `WeakRef` オブジェクトを使用して、ファイル オブジェクトを参照できます。 そのファイルが開いている場合は、 `WeakRef` が有効になり、参照先ファイルにアクセスできます。 一方、そのファイルが閉じている場合は、 `WeakRef` が無効になり、そのファイルにアクセスできません。

## <a name="related-topics"></a>関連トピック

|||
|-|-|
|[カテゴリ別の主要な Api](../windows/key-wrl-apis-by-category.md)|主要な Windows ランタイム C++ テンプレート ライブラリの型、関数、およびマクロを強調表示されます。|
|[参照](../windows/wrl-reference.md)|Windows ランタイム C++ テンプレート ライブラリに関するリファレンス情報が含まれています。|
|[クイック リファレンス (Windows ランタイムと Visual C)](http://go.microsoft.com/fwlink/p/?linkid=229180)|簡単に説明する c++/cli CX 機能、Windows ランタイムをサポートします。|
|[Visual C での Windows ランタイム コンポーネントを使用します。](http://go.microsoft.com/fwlink/p/?linkid=229155)|C + を使用する方法を示します/cli CX 基本 Windows ランタイム コンポーネントを作成します。|