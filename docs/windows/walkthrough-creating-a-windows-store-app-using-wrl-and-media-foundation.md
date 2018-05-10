---
title: 'チュートリアル: WRL および Media Foundation を使用して、UWP アプリの作成 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
ms.assetid: 0336c550-fbeb-4dc4-aa9b-660f9fc45382
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 1c9e3f678a65b3dacfc5bba012656118b6fe2fa1
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
---
# <a name="walkthrough-creating-a-uwp-app-using-wrl-and-media-foundation"></a>チュートリアル: WRL および Media Foundation を使用して、UWP アプリの作成
Windows ランタイム C++ テンプレート ライブラリ (WRL) を使用して、使用するユニバーサル Windows プラットフォーム (UWP) アプリを作成する方法を学習[Microsoft メディア ファンデーション](http://msdn.microsoft.com/library/windows/apps/ms694197)です。  
  
 この例では、Web カメラからキャプチャしたイメージにグレースケール効果を適用するカスタム メディア ファンデーション変換を作成します。 アプリでは、カスタム変換の定義のために C++ を使用し、キャプチャしたイメージを変換するコンポーネントを使用するために C# を使用しています。  
  
> [!NOTE]
>  C# の代わりに、JavaScript、Visual Basic、または C++ でカスタム変換コンポーネントを使用することもできます。  
  

 ほとんどの場合にを使用することが C + + CX を Windows ランタイムを作成する)。 ただし、場合があります、WRL を使用する必要があります。 たとえば、Microsoft メディア ファンデーションのメディア拡張機能を作成するときに、COM および Windows ランタイムの両方のインターフェイスを実装するコンポーネントを作成する必要があります。 C + + CX では、Windows ランタイム オブジェクトを作成できるのみ、COM および Windows ランタイムの両方のインターフェイスの実装を有効にするため、メディア拡張機能を作成する、WRL を使用する必要があります。  

  
> [!NOTE]
>  このコード例は長いですが、役に立つメディア ファンデーション変換を作成するために必要な最低限のコードを示しています。 独自のカスタム変換を作成するための出発点として、このコード例を使用することができます。 この例は、[メディア拡張機能サンプル](http://code.msdn.microsoft.com/windowsapps/Media-extensions-sample-7b466096)ビデオへの効果を使用してメディア拡張機能を適用、ビデオのデコード、メディア ストリームを生成するスキーム ハンドラーを作成します。  
  
## <a name="prerequisites"></a>必須コンポーネント  
  
-   エクスペリエンス、 [Windows ランタイム](http://msdn.microsoft.com/library/windows/apps/br211377.aspx)です。  
  
-   COM の使用経験。  
  
-   Web カメラ。  
  
## <a name="key-points"></a>主要なポイント  
  
-   カスタム メディア ファンデーション コンポーネントを作成するには、Microsoft インターフェイス定義言語 (MIDL) の定義ファイルを使用してインターフェイスを定義し、そのインターフェイスを実装して、他のコンポーネントからアクティブ化できるようにします。  
  
-   `namespace`と`runtimeclass`属性、および`NTDDI_WIN8`[バージョン](http://msdn.microsoft.com/en-us/66ac5cf3-2230-44fd-aaf6-8013e4a4ae81)属性値は、WRL を使用するメディア ファンデーション コンポーネントの MIDL 定義の重要な部分です。  
  
-   [Microsoft::WRL::RuntimeClass](../windows/runtimeclass-class.md)カスタム メディア ファンデーション コンポーネントの基本クラスです。 [Microsoft::WRL::RuntimeClassType::WinRtClassicComMix](../windows/runtimeclasstype-enumeration.md)列挙値は、テンプレート引数として指定される、Windows ランタイム クラスとクラシック COM ランタイム クラスの両方に使用されるクラスをマークします。  
  
-   [InspectableClass](../windows/inspectableclass-macro.md)マクロは、参照カウントなどの COM 基本機能を実装し、`QueryInterface`メソッド、およびランタイム クラス名と信頼レベルを設定します。  
  
-   使用して、microsoft::wrl::[モジュール クラス](https://www.microsoftonedoc.com/#/organizations/e6f6a65cf14f462597b64ac058dbe1d0/projects/3fedad16-eaf1-41a6-8f96-0c1949c68f32/containers/a3daf831-1c5f-4bbe-964d-503870caf874/tocpaths/b4acf5de-2f4c-4c8b-b5ff-9140d023ecbe/locales/en-US)など DLL エントリ ポイント関数を実装する[DllGetActivationFactory](http://msdn.microsoft.com/library/br205771.aspx)、 [DllCanUnloadNow](http://msdn.microsoft.com/library/windows/desktop/ms690368\(v=vs.85\).aspx)、および[DllGetClassObject](http://msdn.microsoft.com/library/windows/desktop/ms680760\(v=vs.85\).aspx)です。  
  
-   コンポーネント DLL を runtimeobject.lib にリンクします。 指定[/WINMD](../cppcx/compiler-and-linker-options-c-cx.md) Windows メタデータを生成するリンカー行にします。  
  
-   プロジェクト参照を使用して、WRL コンポーネントを UWP アプリにアクセスできるようにします。  
  
### <a name="to-use-the-wrl-to-create-the-media-foundation-grayscale-transform-component"></a>WRL メディア ファンデーションのグレースケールを作成する変換コンポーネントを使用するには  
  
1.  Visual Studio で、作成、**空のソリューション**プロジェクト。 など、プロジェクトの名前`MediaCapture`です。  
  
2.  追加、 **DLL (ユニバーサル Windows)** プロジェクトがソリューションにします。 など、プロジェクトの名前`GrayscaleTransform`です。  
  
3.  追加、 **Midl ファイル (.idl)** ファイルをプロジェクト。 など、ファイルの名前`GrayscaleTransform.idl`です。  
  
4.  次のコードを GrayscaleTransform.idl に追加します。  
  
     [!code-cpp[wrl-media-capture#1](../windows/codesnippet/CPP/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_1.idl)]  
  
5.  次のコードを使用して pch.h の内容を置き換えます。  
  
     [!code-cpp[wrl-media-capture#2](../windows/codesnippet/CPP/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_2.h)]  
  
6.  プロジェクトに新しいヘッダー ファイルを追加、名前を付けます`BufferLock.h`、このコードを追加します。  
  
     [!code-cpp[wrl-media-capture#3](../windows/codesnippet/CPP/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_3.h)]  
  
7.  GrayscaleTransform.h は、この例では使用しません。 このファイルは必要に応じてプロジェクトから削除できます。  
  
8.  次のコードを使用して GrayscaleTransform.cpp の内容を置き換えます。  
  
     [!code-cpp[wrl-media-capture#4](../windows/codesnippet/CPP/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_4.cpp)]  
  
9. プロジェクトに新しいモジュール定義ファイルを追加、名前を付けます`GrayscaleTransform.def`、このコードを追加します。  
  
   ```
   EXPORTS
       DllCanUnloadNow                     PRIVATE
       DllGetActivationFactory             PRIVATE
       DllGetClassObject                   PRIVATE
   ```   
  
10. 次のコードを使用して dllmain.cpp の内容を置き換えます。  
  
     [!code-cpp[wrl-media-capture#6](../windows/codesnippet/CPP/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_6.cpp)]  
  
11. プロジェクトの**プロパティ ページ** ダイアログ ボックスで、以下の設定を**リンカー**プロパティです。  
  
    1.  **入力**、用、**モジュール定義ファイル**、指定`GrayScaleTransform.def`です。  
  
    2.  でも**入力**、追加`runtimeobject.lib`、 `mfuuid.lib`、および`mfplatf.lib`を**追加の依存関係**プロパティです。  
  
    3.  **Windows メタデータ**設定、 **Windows メタデータの生成**に**はい (/WINMD)** です。  
  
### <a name="to-use-the-wrl-the-custom-media-foundation-component-from-a-c-app"></a>WRL c# アプリからカスタム メディア ファンデーション コンポーネントを使用するには  
  
1.  新しい**c# 新しいアプリケーション (XAML)** プロジェクトを`MediaCapture`ソリューションです。 など、プロジェクトの名前`MediaCapture`です。  
  
2.  **MediaCapture**プロジェクトへの参照を追加、`GrayscaleTransform`プロジェクト。 学習する方法についてを参照してください[する方法: 追加または参照マネージャーを使用して参照を削除する](/visualstudio/ide/how-to-add-or-remove-references-by-using-the-reference-manager)です。  
  
3.  Package.appxmanifest 上、**機能**] タブで [**マイク**と**web カメラ**です。 Web カメラから写真をキャプチャするために、両方の機能が必要です。  
  
4.  MainPage.xaml で、ルートにこのコードを追加[グリッド](http://msdn.microsoft.com/library/windows/apps/xaml/windows.ui.xaml.controls.grid.aspx)要素。  
  
     [!code-xml[wrl-media-capture#7](../windows/codesnippet/Xaml/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_7.xaml)]  
  
5.  次のコードを使用して MainPage.xaml.cs の内容を置き換えます。  
  
     [!code-cs[wrl-media-capture#8](../windows/codesnippet/CSharp/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_8.cs)]  
  
 次の図は、MediaCapture アプリを示しています。  
  
 ![写真をキャプチャする MediaCapture アプリ](../windows/media/wrl_media_capture.png "WRL_Media_Capture")  
  
## <a name="next-steps"></a>次の手順  
 例では、既定の Web カメラから写真を 1 枚ずつキャプチャする方法を示します。 [メディア拡張機能サンプル](http://code.msdn.microsoft.com/windowsapps/Media-extensions-sample-7b466096)は以上です。 そのサンプルでは、Web カメラ デバイスを列挙し、ローカル スキーム ハンドラーを使用する方法や、個別の写真とビデオ ストリームの両方で機能する追加のメディア効果について示します。  
  
## <a name="see-also"></a>関連項目  
 [Windows ランタイム C++ テンプレート ライブラリ (WRL)](../windows/windows-runtime-cpp-template-library-wrl.md)   
 [Microsoft メディア ファンデーション](http://msdn.microsoft.com/library/windows/apps/ms694197)   
 [メディア拡張機能サンプル](http://code.msdn.microsoft.com/windowsapps/Media-extensions-sample-7b466096)