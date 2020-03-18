---
title: プロジェクトの作成 (ATL チュートリアル、パート 1)
ms.custom: get-started-article
ms.date: 08/19/2019
ms.assetid: f6b727d1-390a-4b27-b82f-daadcd9fc059
ms.openlocfilehash: b4c18d83feb6c61b603bb1880960193cf9150f9b
ms.sourcegitcommit: 44eeb065c3148d0484de791080a3f963109744fc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/18/2020
ms.locfileid: "79509396"
---
# <a name="creating-the-project-atl-tutorial-part-1"></a>プロジェクトの作成 (ATL チュートリアル、パート 1)

このチュートリアルでは、多角形を表示する ActiveX オブジェクトを作成する、属性のない ATL プロジェクトのステップバイステップの手順について説明します。 オブジェクトには、多角形を構成する辺の数をユーザーが変更できるようにするためのオプション、および表示を更新するためのコードが含まれています。

> [!NOTE]
> このチュートリアルでは、Polygon サンプルと同じソースコードを作成します。 ソースコードが手動で入力されないようにする場合は、 [Polygon sample abstract](https://github.com/Microsoft/VCSamples/tree/master/VC2008Samples/ATL/Controls/Polygon)からダウンロードできます。 その後、チュートリアルで作業するときに Polygon ソースコードを参照するか、またはそれを使用して独自のプロジェクトでエラーをチェックすることができます。
> コンパイルするには、 *.pch* (Visual Studio 2017 以前では*stdafx.h* ) を開き、次のように置き換えます。
>
> ```
> #ifndef WINVER
> #define WINVER 0x0400
> #endif
> ```
>
> with
>
> ```
> #ifndef WINVER
> #define WINVER 0x0500
> #define _WIN32_WINNT 0x0500
> #endif
> ```
>
> コンパイラは、正常に終了していない `regsvr32` を引き続き通知しますが、コントロールの DLL をビルドして使用できるようにする必要があります。

### <a name="to-create-the-initial-atl-project-using-the-atl-project-wizard"></a>ATL プロジェクトウィザードを使用して最初の ATL プロジェクトを作成するには

1. Visual Studio 2017 以前の場合: **File** > **New** > **Project** を実行します。 **[ビジュアルC++ ]** タブを開き、 **[MFC/ATL]** を選択します。 **[ATL プロジェクト]** を選択します。

   Visual Studio 2019: [**ファイル** > **新しい** > **プロジェクト**] を選択し、検索ボックスに「atl」と入力して、 **[atl プロジェクト]** を選択します。

1. プロジェクト名として「 *Polygon* 」と入力します。

    通常、ソースコードの場所は、既定では \ ユーザー\\\<ユーザー名 > になります。新しいフォルダーが自動的に作成されます。

1. Visual Studio 2019 で、既定値をそのまま使用し、[ **OK]** をクリックします。 
   Visual Studio 2017 で **[OK]** をクリックして、 **ATL プロジェクト**ウィザードを開きます。 **[アプリケーションの設定]** をクリックして、使用可能なオプションを表示します。 このプロジェクトはコントロールを作成し、コントロールはインプロセスサーバーである必要があるため、**アプリケーションの種類**は DLL として残しておきます。 **[OK]** をクリックすると、

Visual Studio では、複数のファイルを生成することでプロジェクトが作成されます。 これらのファイルを**ソリューションエクスプローラー**で表示するには、`Polygon` オブジェクトを展開します。 ファイルは次のとおりです。

::: moniker range="<=vs-2017"

|ファイル|説明|
|----------|-----------------|
|Polygon|`DllMain`、`DllCanUnloadNow`、`DllGetClassObject`、`DllRegisterServer`、および `DllUnregisterServer`の実装が含まれています。 には、プロジェクト内の ATL オブジェクトのリストであるオブジェクトマップも含まれています。 最初は空白になります。|
|Polygon .def|このモジュール定義ファイルは、DLL で必要とされるエクスポートに関する情報をリンカーに提供します。|
|Polygon .idl|インターフェイス定義言語ファイル。オブジェクトに固有のインターフェイスを記述します。|
|Polygon .rgs|このレジストリスクリプトには、プログラムの DLL を登録するための情報が含まれています。|
|Polygon|リソースファイル。最初はバージョン情報とプロジェクト名を含む文字列が含まれています。|
|Resource.h|リソース ファイルのヘッダー ファイルです。|
|Polygonps|このモジュール定義ファイルは、アパートメント間の呼び出しをサポートするプロキシおよびスタブコードに必要なエクスポートに関する情報をリンカーに提供します。|
|stdafx.cpp|*Stdafx.h*を `#include` するファイル。|
|stdafx.h|ATL ヘッダーファイルの `#include` およびプリコンパイルを実行するファイル。|

::: moniker-end

::: moniker range=">=vs-2019"

|ファイル|説明|
|----------|-----------------|
|Polygon|`DllMain`、`DllCanUnloadNow`、`DllGetClassObject`、`DllRegisterServer`、および `DllUnregisterServer`の実装が含まれています。 には、プロジェクト内の ATL オブジェクトのリストであるオブジェクトマップも含まれています。 最初は空白になります。|
|Polygon .def|このモジュール定義ファイルは、DLL で必要とされるエクスポートに関する情報をリンカーに提供します。|
|Polygon .idl|インターフェイス定義言語ファイル。オブジェクトに固有のインターフェイスを記述します。|
|Polygon .rgs|このレジストリスクリプトには、プログラムの DLL を登録するための情報が含まれています。|
|Polygon|リソースファイル。最初はバージョン情報とプロジェクト名を含む文字列が含まれています。|
|Resource.h|リソース ファイルのヘッダー ファイルです。|
|Polygonps|このモジュール定義ファイルは、アパートメント間の呼び出しをサポートするプロキシおよびスタブコードに必要なエクスポートに関する情報をリンカーに提供します。|
|pch|*Pch*`#include` れるファイル。|
|.pch. h|ATL ヘッダーファイルの `#include` およびプリコンパイルを実行するファイル。|

::: moniker-end

1. **ソリューション エクスプローラー**で、`Polygon` プロジェクトを右クリックします。

1. ショートカットメニューの **[プロパティ]** をクリックします。

1. **[リンカー]** をクリックします。 **UserRedirection**オプションを **[はい]** に変更します。

1. **[OK]** をクリックすると、

次の手順では、プロジェクトにコントロールを追加します。

[手順2に進みます。](../atl/adding-a-control-atl-tutorial-part-2.md)

## <a name="see-also"></a>参照

[チュートリアル](../atl/active-template-library-atl-tutorial.md)
