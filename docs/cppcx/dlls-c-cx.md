---
title: Dll (C + + CX) |Microsoft Docs
ms.custom: ''
ms.date: 02/06/2018
ms.technology: cpp-windows
ms.topic: language-reference
ms.assetid: 5b8bcc57-64dd-4c54-9f24-26a25bd5dddd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1ac06336e5ba80406157285ebe660080aff6e319
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2018
ms.locfileid: "43763634"
---
# <a name="dlls-ccx"></a>DLL (C++/CX)

Visual Studio を使用して、標準の Win32 DLL または Windows ランタイム コンポーネントのユニバーサル Windows プラットフォーム (UWP) アプリで使用できる DLL を作成することができます。 Visual Studio または Visual Studio 2012 は UWP アプリでは正しく読み込まれない可能性があり、Microsoft Store でアプリの検証テストに合格しない場合がありますより前である Visual C コンパイラのバージョンを使用して作成された標準 DLL です。

## <a name="windows-runtime-component-dlls"></a>Windows ランタイム コンポーネント Dll

ほとんどの場合を作成するときに用の DLL は UWP アプリで使用、その名前のプロジェクト テンプレートを使用して、Windows ランタイム コンポーネントとして作成します。 パブリックまたはプライベートの Windows ランタイム型を持つ dll の場合は、Windows ランタイム コンポーネント プロジェクトを作成できます。 Windows ランタイム コンポーネントは、任意の Windows ランタイムと互換性のある言語で記述されたアプリからアクセスできます。 Windows ランタイム コンポーネント用のコンパイラ設定を既定には、プロジェクトの使用、 **/ZW**スイッチします。 .winmd ファイルには、ルート名前空間と同じ名前が必要です。 たとえば、A.B.C.MyClass という名前のクラスは、A.winmd または A.B.winmd または A.B.C.winmd という名前のメタデータ ファイルで定義されている場合のみインスタンス化できます。 DLL の名前が .winmd ファイル名と一致する必要はありません。

詳細については、次を参照してください。 [C++ での Windows ランタイム コンポーネントの作成](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp)です。

### <a name="to-reference-a-third-party-windows-runtime-component-binary-in-your-project"></a>サード パーティの Windows ランタイム コンポーネント プロジェクトのバイナリを参照するには

1. DLL を使用するプロジェクトのショートカット メニューを開き、 **[プロパティ]** をクリックします。 **[共通プロパティ]** ページで、 **[新しい参照の追加]** をクリックします。

1. Windows ランタイム コンポーネントは、DLL ファイルとメタデータを含む .winmd ファイルで構成されます。 通常、これらのファイルは同じフォルダーにあります。 **[参照の追加]** ダイアログ ボックスの左ペインで、 **[参照]** をクリックし、DLL とその .winmd ファイルの場所に移動します。 詳細については、次を参照してください。[拡張 Sdk](/visualstudio/extensibility/creating-a-software-development-kit#ExtensionSDKs)します。

## <a name="standard-dlls"></a>標準 DLL

使用またはパブリックの Windows ランタイム型を生成し、UWP アプリから使用しない C++ コード用の標準 DLL を作成することができます。 このバージョンの Visual Studio でコンパイルされますが、コードは、Windows ランタイム コンポーネント プロジェクトに変換する既存の DLL を移行する場合は、ダイナミック リンク ライブラリ (DLL) プロジェクトの種類を使用します。 次の手順を使用する場合、DLL は .appx パッケージのアプリ実行可能ファイルと一緒に配置されます。

### <a name="to-create-a-standard-dll-in-visual-studio"></a>Visual Studio で、標準 DLL を作成するには

1. メニュー バーで、**ファイル**、**新規**、**プロジェクト**、クリックして、**ダイナミック リンク ライブラリ (DLL)** テンプレート。

1. プロジェクトの名前を入力し、 **[OK]** をクリックします。

1. コードを追加します。 必ず、エクスポートする対象の関数 ( `__declspec(dllexport)` など) の `__declspec(dllexport) Add(int I, in j);`を使用してください。

1. 追加`#include winapifamily.h`UWP アプリ用 Windows SDK からのヘッダー ファイルを含めるし、マクロを設定する`WINAPI_FAMILY=WINAPI_PARTITION_APP`します。

### <a name="to-reference-a-standard-dll-project-from-the-same-solution"></a>同じソリューションから標準 DLL プロジェクトを参照するには

1. DLL を使用するプロジェクトのショートカット メニューを開き、 **[プロパティ]** をクリックします。 **[共通プロパティ]** ページで、 **[新しい参照の追加]** をクリックします。

1. 左ペインで **[ソリューション]** をクリックし、右ペインの対応するチェック ボックスをオンにします。

1. ソース コード ファイルで、必要に応じて DLL のヘッダー ファイルの `#include` ステートメントを追加します。

### <a name="to-reference-a-standard-dll-binary"></a>標準 DLL バイナリを参照するには

1. DLL ファイル、.lib ファイル、およびヘッダー ファイルをコピーし、既知の場所 (現在のプロジェクト フォルダーなど) に貼り付けます。

1. DLL を使用するプロジェクトのショートカット メニューを開き、 **[プロパティ]** をクリックします。 **[構成プロパティ]**、 **[リンカー]** の順にクリックし、 **[入力]** ページで、依存関係として .lib ファイルを追加します。

1. ソース コード ファイルで、必要に応じて DLL のヘッダー ファイルの `#include` ステートメントを追加します。

### <a name="to-migrate-an-existing-win32-dll-for-uwp-app-compatibility"></a>UWP アプリの互換性のための既存の Win32 DLL を移行するには

1. DLL (ユニバーサル Windows) の種類のプロジェクトを作成し、既存のソース コードを追加します。

1. 追加`#include winapifamily.h`UWP アプリ用 Windows SDK からのヘッダー ファイルを含めるし、マクロを設定する`WINAPI_FAMILY=WINAPI_PARTITION_APP`します。

1. ソース コード ファイルで、必要に応じて DLL のヘッダー ファイルの `#include` ステートメントを追加します。
