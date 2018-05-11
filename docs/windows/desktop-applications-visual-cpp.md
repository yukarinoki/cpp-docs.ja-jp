---
title: デスクトップ アプリケーション (Visual C) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: a020b534-293c-44e2-aa48-516c43ddeb8f
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f9c8180288374711db4e6d866c73a0bc8919caf2
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
---
# <a name="desktop-applications-visual-c"></a>デスクトップ アプリケーション (Visual C)
A*デスクトップ アプリケーション*C++ では、Windows Api といずれかの実行ウィンドウまたはシステム コンソールの完全なセットにアクセスできる、ネイティブ アプリケーションです。 C++ ではデスクトップ アプリケーションは、(ただし、Windows XP が不要になった公式にサポートされていて、それ以降に導入された多くの Windows Api) から Windows 10 の Windows XP で実行できます。   デスクトップ アプリケーションとは異なります、ユニバーサル Windows プラットフォーム (UWP) アプリ、Windows 10 を実行している pc と XBox、Windows Phone、Surface Hub、およびその他のデバイスでも実行できます。 詳細についてはデスクトップとします。UWP アプリケーションを参照してください[、テクノロジの選択](https://msdn.microsoft.com/en-us/library/windows/desktop/dn614993\(v=vs.85\).aspx)です。  
  
 **用語集**  
  
-   A *Win32*アプリケーションはネイティブの c++ できるようにするデスクトップ アプリケーションを使用して Windows [Windows C Api および COM Api](https://msdn.microsoft.com/en-us/library/windows/desktop/ff818516\(v=vs.85\).aspx) CRT、標準ライブラリの Api、およびサード パーティ製ライブラリです。 ウィンドウで実行される Win32 アプリケーションでは、Windows プロシージャ関数内の Windows メッセージを明示的に使用する開発者が必要です。 名前にかかわらず、Win32 アプリケーションは、32 ビット (x86) または 64 ビット (x64) バイナリとしてコンパイルできます。 IDE では Visual Studio、Win32、x86 の条件は同義です。  
  
-   [コンポーネント オブジェクト モデル (COM)](https://msdn.microsoft.com/en-us/library/windows/desktop/ms694363\(v=vs.85\).aspx)を相互に通信するためにさまざまな言語で書かれたプログラムを有効にする仕様です。 多くの Windows コンポーネントが、COM オブジェクトとして実装され、オブジェクト作成のための標準の COM 規則に従うには、検出とオブジェクトの破棄がインターフェイスです。  C++ デスクトップ アプリケーションから COM オブジェクトを使用して、比較的簡単ですが、独自の COM オブジェクトの記述がより高度な。 [アクティブ テンプレート ライブラリ (ATL)](../atl/atl-com-desktop-components.md)マクロおよび COM 開発を簡略化するヘルパー関数を提供します。  
  
-   MFC アプリケーションは、Windows デスクトップ アプリケーションを使用して、 [Microsoft Foundation Classes](../mfc/mfc-desktop-applications.md)ユーザー インターフェイスを作成します。 MFC アプリケーションは、COM コンポーネントと CRT と標準ライブラリの Api も使用できます。 MFC では、ウィンドウ メッセージ ループと Windows Api を介してシン C++ オブジェクト指向ラッパーを提供します。 MFC アプリケーションの既定のオプションは、— 特にエンタープライズ型アプリケーションでは、多数のユーザー インターフェイス コントロールまたはカスタム ユーザー コントロールがあります。 MFC には、ウィンドウの管理、シリアル化、テキスト操作、印刷、およびリボンなどのモダン ユーザー インターフェイス要素の便利なヘルパー クラスが用意されています。 MFC で有効にするには、Win32 について熟知してください。  
  
-   C + + CLI アプリケーションまたはコンポーネントを使用して C++ 構文の拡張機能 (C++ の仕様によって許可) と .NET とネイティブ c++ コード間の相互作用を有効にします。  C + +/CLI アプリケーションは、ネイティブに実行されるパートと .NET の基本クラス ライブラリにアクセス権を持つ .NET Framework で実行されるパートを持つことができます。 C + + CLI は、c# または Visual Basic で記述されたコードを使用する必要があるネイティブの C++ コードがある場合に推奨されるオプションです。 ユーザー インターフェイスのコードではなく .NET Dll で使用する場合に、主にものです。 詳細については、次を参照してください。 [C + での .NET プログラミング +/CLI (Visual c)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)です。  
  
 C ランタイム (CRT) および標準ライブラリのクラスと関数、COM オブジェクト、およびパブリックの Windows の機能は総称して、Windows API と呼ばれますが、C++ では、デスクトップ アプリケーションを使用できます。 C++ の Windows デスクトップ アプリケーションの概要については、「 [C++ による Windows プログラミングの学習](http://go.microsoft.com/fwlink/p/?LinkId=262281)」を参照してください。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
|Title|説明|  
|-----------|-----------------|  
|[コンソール アプリケーション](../windows/console-applications-in-visual-cpp.md)|コンソール アプリに関する情報が含まれています。 Win32 (または Win64) コンソール アプリケーションには、独自のウィンドウとメッセージ ループはありません。 コンソール ウィンドウで動作し、入出力はコマンド ラインを使用して扱われます。|  
|[Windows デスクトップ アプリケーション](../windows/windows-desktop-applications-cpp.md)|コンソールではなく windows で実行するデスクトップ アプリケーションを作成する方法。|  
|[DirectX (C++) を使用するゲームを作成するためのリソース](../windows/resources-for-creating-a-game-using-directx.md)|C++ でゲームを作成するためのコンテンツへのリンク。|  
|[チュートリアル: 作成とスタティック ライブラリの使用](../windows/walkthrough-creating-and-using-a-static-library-cpp.md)|.Lib バイナリ ファイルを作成する方法。|  
|[方法: Windows デスクトップ アプリケーションでの Windows 10 SDK の使用](../windows/how-to-use-the-windows-10-sdk-in-a-windows-desktop-application.md)|Windows 10 SDK を使用してビルドするプロジェクトの設定手順が示されています。|  
  
## <a name="related-articles"></a>関連トピック  
  
|タイトル|説明|  
|-----------|-----------------|  
|[Windows 開発](http://go.microsoft.com/fwlink/p/?LinkId=262282)|Windows API と COM に関する情報が含まれています (一部の Windows API とサードパーティ製 DLL は、COM オブジェクトとして実装されています)。|  
|[Hilo: Windows 7 対応 C++ アプリケーションの開発](http://go.microsoft.com/fwlink/p/?LinkId=262284)|手荷物の受け取り場所に基づくユーザー インターフェイスを作成するために、Windows Animation と Direct2D を使用するリッチ クライアントの Windows デスクトップ アプリケーションを作成する方法について説明します。  このチュートリアルが Windows 7 以降に更新されていないが、まだ Win32 プログラミングの詳細な概要を提供します。|  
|[Visual C++](../visual-cpp-in-visual-studio.md)|Visual Studio での Visual C++ の主な機能について説明し、他の Visual C++ ドキュメントへのリンクを示します。|  
  
## <a name="see-also"></a>関連項目  
 [Visual C++](../visual-cpp-in-visual-studio.md)
