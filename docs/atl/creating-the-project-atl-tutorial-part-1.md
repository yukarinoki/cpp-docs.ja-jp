---
title: プロジェクトの作成 (ATL チュートリアル、パート 1)
ms.custom: get-started-article
ms.date: 05/06/2019
ms.assetid: f6b727d1-390a-4b27-b82f-daadcd9fc059
ms.openlocfilehash: 0df793b23aaec57835774252eeac21b092f8a9e9
ms.sourcegitcommit: 0e3da5cea44437c132b5c2ea522bd229ea000a10
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2019
ms.locfileid: "67861021"
---
# <a name="creating-the-project-atl-tutorial-part-1"></a>プロジェクトの作成 (ATL チュートリアル、パート 1)

このチュートリアルでは、属性なしの ATL プロジェクト多角形を表示する ActiveX オブジェクトを作成する手順について説明します。 オブジェクトには、多角形、およびコードの表示を更新する辺の数を変更するユーザーを許可するためのオプションが含まれています。

> [!NOTE]
> ATL および MFC は一般にサポートされていません Visual Studio の Express edition でします。

> [!NOTE]
> このチュートリアルでは、多角形のサンプルと同じソース コードを作成します。 ソース コードを手動で入力しないようにする場合をからダウンロードできます、[多角形サンプル抽象](https://github.com/Microsoft/VCSamples/tree/master/VC2008Samples/ATL/Controls/Polygon)します。 「チュートリアル、またはそれを使用して、独自のプロジェクトのエラーを確認すると、多角形のソース コードにし、参照できます。
> をコンパイルするには、stdafx.h を開き、置換します。
> ```
> #ifndef WINVER
> #define WINVER 0x0400
> #endif
> ```
> with
> ```
> #ifndef WINVER
> #define WINVER 0x0500
> #define _WIN32_WINNT 0x0500
> #endif
> ```
> コンパイラの不満はまだ`regsvr32`が正しく終了していないに構築され、使用可能なコントロールの DLL がはずです。

### <a name="to-create-the-initial-atl-project-using-the-atl-project-wizard"></a>ATL プロジェクト ウィザードを使用して、初期の ATL プロジェクトを作成するには

1. Visual studio 2017 およびそれ以前。**ファイル** > **新しい** > **プロジェクト**します。 開く、 **Visual C++** タブ**MFC/ATL**します。 選択**ATL プロジェクト**します。

   Visual Studio 2019: で選択**ファイル** > **新規** > **プロジェクト**、検索ボックスで、"atl"を入力し、 **ATL プロジェクト**します。

1. 型*多角形*プロジェクト名として。

    ソース コードの場所は、通常は既定では \Users\\\<ユーザー名 > \source\repos、および新しいフォルダーが自動的に作成されます。

1. Visual Studio 2019 で既定値をそのまま使用し をクリックして**OK**します。 
   Visual Studio 2017 では、次のようにクリックします。 **OK**を開く、 **ATL プロジェクト**ウィザード。 クリックして**アプリケーション設定**に使用できるオプションを参照してください。 このプロジェクトは、コントロールを作成し、コントロールは、インプロセス サーバーである必要があります、ためにままにして、**アプリケーションの種類**DLL として。 **[OK]** をクリックします。

Visual Studio では、いくつかのファイルを生成することによって、プロジェクトを作成します。 これらのファイルを表示する**ソリューション エクスプ ローラー**を展開して、`Polygon`オブジェクト。 ファイルは、以下に示します。

|File|説明|
|----------|-----------------|
|Polygon.cpp|実装を含む`DllMain`、 `DllCanUnloadNow`、 `DllGetClassObject`、 `DllRegisterServer`、および`DllUnregisterServer`します。 また、プロジェクトで ATL オブジェクトの一覧であるオブジェクト マップが含まれます。 これは、最初は空です。|
|Polygon.def|このモジュール定義ファイルでは、DLL に必要なエクスポートに関する情報をリンカーを提供します。|
|Polygon.idl|インターフェイス定義言語ファイル、オブジェクトに固有のインターフェイスについて説明します。|
|Polygon.rgs|このレジストリ スクリプトには、プログラムの DLL を登録するための情報が含まれています。|
|Polygon.rc|最初にバージョン情報と、プロジェクト名を含む文字列を含むリソース ファイル。|
|Resource.h|リソース ファイルのヘッダー ファイルです。|
|Polygonps.def|このモジュール定義ファイルでは、リンカーがアパートメント間呼び出しをサポートするプロキシとスタブのコードに必要なエクスポートに関する情報を提供します。|
|stdafx.cpp|ファイル`#include`ATL 実装ファイルです。|
|stdafx.h|ファイル`#include`ATL ヘッダー ファイル。|

1. **ソリューション エクスプローラー**で、`Polygon` プロジェクトを右クリックします。

1. ショートカット メニューで、**プロパティ**します。

1. をクリックして**リンカー**します。 変更、 **UserRedirection あたり**オプションを**はい**します。

1. **[OK]** をクリックします。

次の手順では、プロジェクトに、コントロールを追加します。

[手順 2 に](../atl/adding-a-control-atl-tutorial-part-2.md)

## <a name="see-also"></a>関連項目

[チュートリアル](../atl/active-template-library-atl-tutorial.md)
