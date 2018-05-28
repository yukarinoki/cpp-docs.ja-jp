---
title: Windows ランタイム C++ テンプレート ライブラリ (WRL) |Microsoft ドキュメント
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
ms.openlocfilehash: 40d2ecbcfcd4121727bfe34bf2ffd571722b8a68
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
---
# <a name="windows-runtime-c-template-library-wrl"></a>Windows ランタイム C++ テンプレート ライブラリ (WRL)
Windows ランタイム C++ テンプレート ライブラリ (WRL) は、Windows ランタイム コンポーネントを作成および使用するための低レベルの手段を提供するテンプレート ライブラリです。

> [!NOTE]
> WRL は今すぐに取って代わら C + + WinRT、標準 c++ 17 言語射影の Windows ランタイム Api。 C + + WinRT はバージョン 1803 以降から Windows 10 SDK で使用できます。 C + + WinRT がヘッダー ファイルの完全に実装され、最新の Windows API にファースト クラスのアクセスを提供するように設計します。

> C + + WinRT、両方を使用してその標準に準拠した c++ 17 コンパイラを使用して Windows ランタイム Api を作成します。 C + + WinRT は通常パフォーマンスが向上し、Windows ランタイムの他の言語オプションよりも小さいバイナリを生成します。 C + をサポートするために引き続き +/CX および WRL、C + 新しいアプリケーションに使用することを強く勧めが + WinRT です。 詳細については、次を参照してください。 [C + + WinRT](https://docs.microsoft.com/windows/uwp/cpp-and-winrt-apis/index)です。   
  
## <a name="benefits"></a>利点  
 Windows ランタイム C++ テンプレート ライブラリを使用するより簡単に実装し、コンポーネント オブジェクト モデル (COM) コンポーネントを使用できます。 これは、オブジェクトの有効期間を管理するための参照カウントや、操作が成功したか失敗したかを判断するための `HRESULT` 値のテストのような管理技法を提供します。 Windows ランタイム C++ テンプレート ライブラリを正常に使用するのには、これらの規則や技法に注意深く従う必要があります。  
  
 C + + CX は Windows ランタイム コンポーネントを使用して、言語ベースの高度な方法です。 Windows ランタイム C++ テンプレート ライブラリと C + + CX、あなたに代わってハウスキーピング タスクを自動的に実行することによって、Windows ランタイムのコードの記述を簡略化します。  
  
 Windows ランタイム C++ テンプレート ライブラリおよび C + + CX さまざまな利点があります。 ここでは、いくつかの理由ではなく C + Windows ランタイム C++ テンプレート ライブラリを使用する場合があります + CX:  
  
-   Windows ランタイム C++ テンプレート ライブラリは経由で、Windows ランタイム アプリケーション バイナリ インターフェイス (ABI) のほとんどの抽象化を追加しより効率的に基になるコードを制御する機能が提供を作成または Windows ランタイム Api を使用します。  
  
-   C + + CX 表す COM`HRESULT`例外としての値。 COM、または例外を使用しない 1 つを使用するコード ベースを継承した場合、Windows ランタイム C++ テンプレート ライブラリが例外を使用する必要がないため、Windows ランタイムを使用するより自然な方法であることがあります。  
  
    > [!NOTE]
    >  Windows ランタイム C++ テンプレート ライブラリを使用して`HRESULT`値し、例外をスローしません。 さらに、Windows ランタイム C++ テンプレート ライブラリを使用してスマート ポインターと RAII パターンを保証するオブジェクトが正しく破棄されるとき、アプリケーション コードが例外をスローします。 スマート ポインターと RAII に関する詳細については、次を参照してください。[スマート ポインター](../cpp/smart-pointers-modern-cpp.md)と[オブジェクト固有のリソース (RAII)](../cpp/objects-own-resources-raii.md)です。  
  
-   目的と、Windows ランタイム C++ テンプレート ライブラリの設計に基づいてアクティブ テンプレート ライブラリ (ATL)、COM オブジェクトのプログラミングを簡略化するテンプレート ベースの C++ クラスのセットです。 Windows ランタイム C++ テンプレート ライブラリでは、標準 C++ を使用して、Windows ランタイムをラップする、ためより簡単にポートし、Windows ランタイムに ATL で記述された既存の多くの COM コンポーネントと対話します。 ATL 既にわかっている場合、Windows ランタイム C++ テンプレート ライブラリのプログラミングが容易ことがあります。  
  
## <a name="getting-started"></a>作業の開始  
 ここでは、Windows ランタイム C++ テンプレート ライブラリですぐに作業を取得するのに役立ついくつかのリソースです。  
  
 [Windows ランタイム ライブラリ (WRL)](http://channel9.msdn.com/Events/Windows-Camp/Developing-Windows-8-Metro-style-apps-in-Cpp/The-Windows-Runtime-Library-WRL-)  
 この Channel 9 ビデオの詳細について、Windows ランタイム C++ テンプレート ライブラリの利用方法のユニバーサル Windows プラットフォーム (UWP) アプリと作成、および Windows ランタイム コンポーネントを使用する方法を記述します。  
  
 [方法: アクティブ化、および Windows ランタイム コンポーネント](../windows/how-to-activate-and-use-a-windows-runtime-component-using-wrl.md)  
 Windows ランタイム C++ テンプレート ライブラリを使用して、Windows ランタイムを初期化およびアクティブ化、および Windows ランタイム コンポーネントを使用する方法を示します。  
  
 [方法: 非同期操作の完了](../windows/how-to-complete-asynchronous-operations-using-wrl.md)  
 Windows ランタイム C++ テンプレート ライブラリを使用して、非同期操作を開始し、操作が完了した時点に作業を実行する方法を示します。  
  
 [方法: イベントの処理](../windows/how-to-handle-events-using-wrl.md)  
 Windows ランタイム C++ テンプレート ライブラリを使用してサブスクライブして、Windows ランタイム オブジェクトのイベントを処理する方法を示します。  
  
 [チュートリアル: WRL および Media Foundation を使用した UWP アプリの作成](../windows/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation.md)  
 使用する UWP アプリを作成する方法を学習[Microsoft メディア ファンデーション](http://msdn.microsoft.com/library/windows/apps/ms694197)です。  
  
 [方法: 従来の COM コンポーネントを作成します。](../windows/how-to-create-a-classic-com-component-using-wrl.md)  
 Windows ランタイム C++ テンプレート ライブラリを使用して基本の COM コンポーネントを登録して、デスクトップ アプリから COM コンポーネントを使用する基本的な方法を作成する方法を示します。  
  
 [方法: WRL コンポーネントを直接インスタンス化する](../windows/how-to-instantiate-wrl-components-directly.md)  
 使用する方法、 [Microsoft::WRL::Make](../windows/make-function.md)と[Microsoft::WRL::Details::MakeAndInitialize](../windows/makeandinitialize-function.md)関数を定義しているモジュールからコンポーネントをインスタンス化します。  
  
 [方法: winmdidl.exe と midlrt.exe を使用して、Windows メタデータから .h ファイルを作成する](../windows/use-winmdidl-and-midlrt-to-create-h-files-from-windows-metadata.md)  
 .winmd メタデータから IDL ファイルを作成して、WRL からカスタム Windows ランタイム コンポーネントを使用する方法を示します。  
  
 [チュートリアル: タスクおよび XML HTTP 要求を使用した接続](../parallel/concrt/walkthrough-connecting-using-tasks-and-xml-http-requests.md)  
 使用する方法を示します、 [IXMLHTTPRequest2](http://msdn.microsoft.com/en-us/bbc11c4a-aecf-4d6d-8275-3e852e309908)と[IXMLHTTPRequest2Callback](http://msdn.microsoft.com/en-us/aa4b3f4c-6e28-458b-be25-6cce8865fc71) UWP アプリでの web サービスに HTTP GET および POST 要求を送信するタスクとインターフェイスします。  
  
 [Bing マップ トリップ オプティマイザーのサンプル](http://code.msdn.microsoft.com/Bing-Maps-trip-optimizer-c4e037f7)  
 使用して、`HttpRequest`クラスで定義されている[チュートリアル: 接続を使用してタスクおよび XML HTTP 要求](../parallel/concrt/walkthrough-connecting-using-tasks-and-xml-http-requests.md)完全 UWP アプリのコンテキストでします。  
  
 [C++ のサンプルを Windows ランタイム DLL コンポーネントを作成します。](http://code.msdn.microsoft.com/windowsapps/Creating-a-Windows-Runtime-6c399797)  
 Windows ランタイム C++ テンプレート ライブラリを使用してインプロセス DLL コンポーネントを作成し、C + から使用する方法を示しています。 +/CX、JavaScript、および C# の場合。  
  
 [DirectX の marble maze ゲームのサンプル](http://code.msdn.microsoft.com/windowsapps/DirectX-Marble-Maze-Game-e4806345)  
 Windows ランタイム C++ テンプレート ライブラリを使用して、3-D ゲーム全体のコンテキストでは、DirectX や Media Foundation などの COM コンポーネントの有効期間を管理する方法を示します。  
  
 [デスクトップ アプリのサンプルからのトースト通知を送信します。](http://code.msdn.microsoft.com/windowsdesktop/Sending-toast-notifications-71e230a2)  
 Windows ランタイム C++ テンプレート ライブラリを使用して、デスクトップ アプリからのトースト通知を操作する方法を示します。  
  
## <a name="windows-runtime-c-template-library-compared-to-atl"></a>Windows ランタイム C++ テンプレート ライブラリと ATL の比較  
 Windows ランタイム C++ テンプレート ライブラリでは、使用して、小規模で高速な COM オブジェクトを作成するためにアクティブ テンプレート ライブラリ (ATL) が似ています。 Windows ランタイム C++ テンプレート ライブラリと ATL もモジュール、インターフェイスの明示的な登録内のオブジェクトの定義などの概念を共有し、ファクトリを使用して、オブジェクトの作成を開きます。 ATL. に慣れている場合は、Windows ランタイム C++ テンプレート ライブラリを理解してあります可能性があります。  
  
 Windows ランタイム C++ テンプレート ライブラリは、UWP アプリに必要な COM 機能をサポートします。 したがって、以下のような COM 機能の直接サポートを省略した ATL とは異なっています。  
  
-   集計  
  
-   ストックの実装  
  
-   デュアル インターフェイス (`IDispatch`)  
  
-   標準的な列挙子インターフェイス  
  
-   接続ポイント  
  
-   ティアオフ インターフェイス  
  
-   OLE 埋め込み  
  
-   ActiveX コントロール  
  
-   COM+  
  
## <a name="concepts"></a>概念  
 Windows ランタイム C++ テンプレート ライブラリは、いくつかの基本的な概念を表す型を提供します。 以下のセクションでは、これらの型について説明します。  
  
### <a name="comptr"></a>ComPtr  
 [ComPtr](../windows/comptr-class.md)は、*スマート ポインター*をテンプレート パラメーターで指定されているインターフェイスを表す型。 インターフェイスから派生したオブジェクトのメンバーにアクセスできる変数を宣言するには、 `ComPtr` を使用します。 `ComPtr` は、基になるインターフェイス ポインターの参照カウントを維持し、参照カウントがゼロになるとそのインターフェイスを自動的に解放します。  
  
### <a name="runtimeclass"></a>RuntimeClass  
 [RuntimeClass](../windows/runtimeclass-class.md)インスタンス化された指定したインターフェイスのセットを継承するクラスを表します。 A`RuntimeClass`オブジェクトは、1 つまたは複数の Windows ランタイムの COM インターフェイス、またはコンポーネントへの弱い参照のサポートの組み合わせを提供できます。  
  
### <a name="module"></a>Module  
 [モジュール](../windows/module-class.md)関連オブジェクトのコレクションを表します。 `Module` オブジェクトは、オブジェクトを作成するクラス ファクトリと、他のアプリケーションからオブジェクトを使用できるようにする登録を管理します。  
  
### <a name="callback"></a>コールバック  
 [コールバック](../windows/callback-function-windows-runtime-cpp-template-library.md)関数がメンバー関数のイベント ハンドラー (コールバック メソッド) であるオブジェクトを作成します。 非同期操作を書き込むには、 `Callback` 関数を使用します。  
  
### <a name="eventsource"></a>EventSource  
 [EventSource](../windows/eventsource-class.md)管理に使用される*委任*イベント ハンドラー。 Windows ランタイム C++ テンプレート ライブラリを使用して、デリゲートを実装し、使用`EventSource`を追加するには、削除、およびデリゲートを起動します。  
  
### <a name="asyncbase"></a>AsyncBase  
 [AsyncBase](../windows/asyncbase-class.md)を Windows ランタイムの非同期プログラミング モデルを表す仮想メソッドを提供します。 非同期操作の進行状況を開始、停止、または確認するカスタム クラスを作成するには、このクラス内のメンバーをオーバーライドします。  
  
### <a name="ftmbase"></a>FtmBase  
 [FtmBase](../windows/ftmbase-class.md)フリー スレッド マーシャラー オブジェクトを表します。 `FtmBase` は、グローバル インターフェイス テーブル (GIT) を作成し、マーシャリングとプロキシ オブジェクトの管理を支援します。  
  
### <a name="weakref"></a>WeakRef  
 [WeakRef](../windows/weakref-class.md)を表すスマート ポインター型には、*弱い参照*、可能性や、アクセスできない可能性があるオブジェクトを参照します。 A `WeakRef` Windows ランタイムでのみとクラシック COM でないオブジェクトを使用できます  
  
 `WeakRef` オブジェクトは通常、外部スレッドまたは外部アプリケーションによって存在が制御されるオブジェクトを表します。 たとえば、 `WeakRef` オブジェクトを使用して、ファイル オブジェクトを参照できます。 そのファイルが開いている場合は、 `WeakRef` が有効になり、参照先ファイルにアクセスできます。 一方、そのファイルが閉じている場合は、 `WeakRef` が無効になり、そのファイルにアクセスできません。  
  
## <a name="related-topics"></a>関連トピック  
  
|||  
|-|-|  
|[カテゴリ別の主要な Api](../windows/key-wrl-apis-by-category.md)|主要な Windows ランタイム C++ テンプレート ライブラリ型、関数、およびマクロが強調表示されます。|  
|[参照](../windows/wrl-reference.md)|Windows ランタイム C++ テンプレート ライブラリに関するリファレンス情報が含まれています。|  
|[クイック リファレンス (Windows ランタイムと Visual C)](http://go.microsoft.com/fwlink/p/?linkid=229180)|簡単な説明、C + + CX をサポートする機能、Windows ランタイム。|  
|[Visual C での Windows ランタイム コンポーネントの使用](http://go.microsoft.com/fwlink/p/?linkid=229155)|C + を使用する方法を示します +/CX を基本的な Windows ランタイム コンポーネントを作成します。|