---
title: 'チュートリアル: WRL および Media Foundation を使用した UWP アプリの作成'
ms.date: 04/23/2019
ms.topic: reference
ms.assetid: 0336c550-fbeb-4dc4-aa9b-660f9fc45382
ms.openlocfilehash: 272092982c5e9cc57f52043e08c8bd384c43ea96
ms.sourcegitcommit: 89d9e1cb08fa872483d1cde98bc2a7c870e505e9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "82031512"
---
# <a name="walkthrough-creating-a-uwp-app-using-wrl-and-media-foundation"></a>チュートリアル: WRL および Media Foundation を使用した UWP アプリの作成

> [!NOTE]
> 新しい UWP アプリとコンポーネントの場合は、Windows ランタイム API 用の新しい標準 C++17 言語プロジェクションである[C++/WinRT](/windows/uwp/cpp-and-winrt-apis/)を使用することをお勧めします。 C++/WinRT は、バージョン 1803 以降の Windows 10 SDK で使用できます。 C++/WinRT は、ヘッダー ファイルに完全に実装され、最新の Windows API へのファースト クラスのアクセスを提供するように設計されています。

このチュートリアルでは、Windows ランタイム C++ テンプレート ライブラリ (WRL) を使用して[、Microsoft メディア ファンデーション](/windows/win32/medfound/microsoft-media-foundation-sdk)を使用するユニバーサル Windows プラットフォーム (UWP) アプリを作成する方法について説明します。

この例では、Web カメラからキャプチャしたイメージにグレースケール効果を適用するカスタム メディア ファンデーション変換を作成します。 アプリでは、カスタム変換の定義のために C++ を使用し、キャプチャしたイメージを変換するコンポーネントを使用するために C# を使用しています。

> [!NOTE]
> C# の代わりに、JavaScript、Visual Basic、または C++ でカスタム変換コンポーネントを使用することもできます。

ほとんどの場合、C++/CX を使用して Windows ランタイムを作成できます。 ただし、場合によっては WRL を使用する必要があります。 たとえば、Microsoft メディア ファンデーションのメディア拡張機能を作成する場合は、COM インターフェイスと Windows ランタイム インターフェイスの両方を実装するコンポーネントを作成する必要があります。 C++/CX は Windows ランタイム オブジェクトを作成することしかできないため、メディア拡張機能を作成するには、COM インターフェイスと Windows ランタイム インターフェイスの両方の実装が可能になるため、WRL を使用する必要があります。

> [!NOTE]
> このコード例は長いですが、役に立つメディア ファンデーション変換を作成するために必要な最低限のコードを示しています。 独自のカスタム変換を作成するための出発点として、このコード例を使用することができます。 この例は、メディア拡張機能を使用して、ビデオにエフェクトを適用したり、ビデオをデコードしたり、メディアストリームを生成するスキームハンドラを作成したりする、[メディア拡張サンプル](https://code.msdn.microsoft.com/windowsapps/Media-extensions-sample-7b466096)からも適用されています。

## <a name="prerequisites"></a>前提条件

- Visual Studio 2017 以降では、UWP サポートはオプションのコンポーネントです。 インストールするには、Windows の [スタート] メニューから Visual Studio インストーラーを開き、使用しているバージョンの Visual Studio を見つけます。 [**変更]** を選択し、[**ユニバーサル Windows プラットフォーム開発**] タイルがオンになっていることを確認します。 [**省略可能なコンポーネント**] で、Visual Studio 2017 の UWP 用**C++ ツール (v141)** または Visual Studio 2019**の UWP 用 C++ ツール (v142) を**確認します。 次に、使用する Windows SDK のバージョンを確認します。

- [Windows ランタイム](/uwp/api/)の経験 :

- COM の使用経験。

- Web カメラ。

## <a name="key-points"></a>主要なポイント

- カスタム メディア ファンデーション コンポーネントを作成するには、Microsoft インターフェイス定義言語 (MIDL) の定義ファイルを使用してインターフェイスを定義し、そのインターフェイスを実装して、他のコンポーネントからアクティブ化できるようにします。

- 属性`namespace`と`runtimeclass``NTDDI_WIN8`[バージョン属性値](/windows/win32/Midl/version)は、WRL を使用するメディアファウンデーション コンポーネントの MIDL 定義の重要な部分です。

- [マイクロソフト::WRL::ランタイムクラス](runtimeclass-class.md)は、カスタムメディアファウンデーションコンポーネントの基本クラスです。 テンプレート引数として提供[される列挙値](runtimeclasstype-enumeration.md)は、Windows ランタイム クラスと従来の COM ランタイム クラスの両方として使用されるクラスをマークします。

- [InspectableClass](inspectableclass-macro.md)マクロは、参照カウントやメソッドなどの基本的な COM`QueryInterface`機能を実装し、ランタイム クラス名と信頼レベルを設定します。

- [モジュール クラス](module-class.md)を使用して、DLL のエントリ ポイント関数 (DllGetActivationFactory、DllCanUnloadNow、DllGetClassObject など) を実装[します](/windows/win32/api/combaseapi/nf-combaseapi-dllgetclassobject)。 [DllGetActivationFactory](/windows/win32/winrt/functions) [DllCanUnloadNow](/windows/win32/api/combaseapi/nf-combaseapi-dllcanunloadnow)

- コンポーネント DLL を runtimeobject.lib にリンクします。 また、リンカー行に[/WINMD](../../cppcx/compiler-and-linker-options-c-cx.md)を指定して、Windows メタデータを生成します。

- プロジェクト参照を使用して、UWP アプリから WRL コンポーネントにアクセスできるようにします。

### <a name="to-use-the-wrl-to-create-the-media-foundation-grayscale-transform-component"></a>WRL を使用してメディア ファンデーション のグレースケール変換コンポーネントを作成するには

1. Visual Studio で、**空のソリューション**プロジェクトを作成します。 プロジェクトに名前を付*けます*。

1. DLL **(ユニバーサル Windows)** プロジェクトをソリューションに追加します。 プロジェクトに名前を付*けます*。

1. **Midl ファイル (.idl)** ファイルをプロジェクトに追加します。 ファイルに名前を付*けます。*

1. 次のコードをグレースケールトランスフォーム.idlに追加します。

   [!code-cpp[wrl-media-capture#1](../codesnippet/CPP/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_1.idl)]

1. の内容を置き換えるには、次`pch.h`のコードを使用します。

   [!code-cpp[wrl-media-capture#2](../codesnippet/CPP/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_2.h)]

1. 新しいヘッダー ファイルをプロジェクトに追加し、`BufferLock.h`名前を付けて、内容を次のコードで置き換えます。

   [!code-cpp[wrl-media-capture#3](../codesnippet/CPP/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_3.h)]

1. `GrayscaleTransform.h`この例では使用されていません。 このファイルは必要に応じてプロジェクトから削除できます。

1. の内容を置き換えるには、次`GrayscaleTransform.cpp`のコードを使用します。

   [!code-cpp[wrl-media-capture#4](../codesnippet/CPP/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_4.cpp)]

1. 新しいモジュール定義ファイルをプロジェクトに追加し、名前`GrayscaleTransform.def`を付けて、次のコードを追加します。

   ```
   EXPORTS
       DllCanUnloadNow                     PRIVATE
       DllGetActivationFactory             PRIVATE
       DllGetClassObject                   PRIVATE
   ```

1. の内容を置き換えるには、次`dllmain.cpp`のコードを使用します。

   [!code-cpp[wrl-media-capture#6](../codesnippet/CPP/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_6.cpp)]

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスで、次の**リンカー**プロパティを設定します。

   1. [**入力**] の [`GrayScaleTransform.def`**モジュール定義ファイル**] で、 を指定します。

   1. また、[**入力**]`runtimeobject.lib`の`mfuuid.lib`下で`mfplat.lib`、 、 を追加し、**追加の依存関係**プロパティにします。

   1. [Windows**メタデータ**] で **、[Windows メタデータの生成**] を **[はい ] (/WINMD)** に設定します。

### <a name="to-use-the-wrl-the-custom-media-foundation-component-from-a-c-app"></a>C# アプリからカスタム メディア ファンデーション コンポーネントを WRL を使用するには

1. 新しい**C# 空のアプリケーション (ユニバーサル Windows)** プロジェクトをソリューションに追加します`MediaCapture`。 プロジェクトに名前を付*けます*。

1. **MediaCapture**プロジェクトで、プロジェクトへの参照を追加`GrayscaleTransform`します。 方法については、「[方法 : 参照マネージャーを使用して参照を追加または削除する](/visualstudio/ide/how-to-add-or-remove-references-by-using-the-reference-manager)」を参照してください。

1. で`Package.appxmanifest`、[**機能**] タブで [**マイク**と**Web カメラ**] を選択します。 Web カメラから写真をキャプチャするために、両方の機能が必要です。

1. で`MainPage.xaml`、次のコードをルート[Grid](/uwp/api/windows.ui.xaml.controls.grid)要素に追加します。

   [!code-xml[wrl-media-capture#7](../codesnippet/Xaml/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_7.xaml)]

1. の内容を置き換えるには、次`MainPage.xaml.cs`のコードを使用します。

   [!code-cs[wrl-media-capture#8](../codesnippet/CSharp/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_8.cs)]

次の図は、`MediaCapture app`を示しています。

![写真をキャプチャする MediaCapture アプリ](../media/wrl_media_capture.png "WRL_Media_Capture")

## <a name="next-steps"></a>次の手順

例では、既定の Web カメラから写真を 1 枚ずつキャプチャする方法を示します。 [メディア拡張機能のサンプル](https://code.msdn.microsoft.com/windowsapps/Media-extensions-sample-7b466096)では、より多くのことを行います。 そのサンプルでは、Web カメラ デバイスを列挙し、ローカル スキーム ハンドラーを使用する方法や、個別の写真とビデオ ストリームの両方で機能する追加のメディア効果について示します。

## <a name="see-also"></a>関連項目

[Windows ランタイム C++ テンプレート ライブラリ (WRL)](windows-runtime-cpp-template-library-wrl.md)<br/>
[マイクロソフト メディア ファウンデーション](/windows/win32/medfound/microsoft-media-foundation-sdk)<br/>
[メディア拡張のサンプル](https://code.msdn.microsoft.com/windowsapps/Media-extensions-sample-7b466096)
