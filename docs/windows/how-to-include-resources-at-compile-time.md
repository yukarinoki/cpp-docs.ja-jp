---
title: '方法: リソースは、コンパイル時 (C++)'
ms.date: 11/04/2016
f1_keywords:
- vs.resvw.resource.including
- vc.resvw.resource.including
- vc.editors.resourceincludes
helpviewer_keywords:
- comments [C++], compiled files
- resources [C++], including at compile time
- projects [C++], including resources
- '#include directive'
- include directive (#include)
- Resource Includes dialog box [C++]
- rc files [C++], changing storage
- symbol header files [C++], changing
- .rc files [C++], changing storage
- symbol header files [C++], read-only
- symbols [C++], symbol header files
- directories [C++], specifying include paths for resources
- include files [C++], specifying for resources
- resources [C++], including in projects
- symbols [C++], finding
- resources [C++], searching for symbols
ms.assetid: 357e93c2-0a29-42f9-806f-882f688b8924
ms.openlocfilehash: 8df5a8ee6583b1e9f5c50a428b69babb0d56961b
ms.sourcegitcommit: f4be868c0d1d78e550fba105d4d3c993743a1f4b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/12/2019
ms.locfileid: "56152379"
---
# <a name="how-to-include-resources-at-compile-time-c"></a>方法: リソースは、コンパイル時 (C++)

通常 1 つのリソース スクリプト (.rc) ファイル内のすべてのリソースの既定の並べ替え方法を使用する便利な簡単になります。 ただし、追加できますリソースその他のファイルで、現在のプロジェクトにコンパイル時にリストにすることによって、**コンパイル時ディレクティブ**ボックスに、**リソースが含まれています** ダイアログ ボックス。

メインの .rc ファイル以外のファイルにリソースを配置する理由のいくつかを次に示します。

- .Rc ファイルを保存するときに削除されないリソース ステートメントには、コメントを追加します。

   リソース エディターを読まない .rc 直接または`resource.h`ファイル。 リソース コンパイラがこれらのファイルをコンパイルして、リソース エディターで使用される .aps ファイルにします。 これはコンパイル手順のファイルで、シンボル データのみが格納されます。 通常のコンパイル プロセスでは、コンパイル プロセス中にシンボリック (たとえば、コメントなど) でない情報が破棄されます。 .Rc ファイルを再生成するたびに .aps ファイルを取得、.rc ファイルとの同期、(たとえば、保存すると、リソース エディターを上書き、.rc ファイルと`resource.h`ファイル)。 リソース自体に対する変更は .rc ファイルに組み込まれたままですが、コメントは .rc ファイルが上書きされると失われます。

- リソースが既に開発し、テストをインクルードして、さらに変更の必要はありません。 (が含まれていますが、.rc 拡張子を持っていないすべてのファイルはありませんは、リソース エディターで編集可能な) です。

- リソースを含めるいくつかの異なるプロジェクトで使用されているか、ソース コードのバージョン管理システムの一部であり、その変更がすべてのプロジェクトに影響が中央の場所に存在する必要があります。

- カスタム形式のリソース (たとえば、RCDATA リソース) をインクルードする。 RCDATA リソースには、特別な要件があります。 たとえば、nameID フィールドの値として式を使用できません。 詳細については、Windows SDK ドキュメントを参照してください。

セクションでは、1 つに配置してこれらの条件のいずれかを満たす既存の .rc ファイルにセクションがある場合または別個の .rc ファイルの詳細、およびそれらを使用して、プロジェクトに含める、**リソース ファイルのインクルード** ダイアログ ボックス。 *Projectname*新しいプロジェクトの \res サブディレクトリに作成された .rc2 ファイルはこの目的に使用します。

使用することができます、**リソースが含まれています**プロジェクトの .rc ファイル内のすべてのリソースを格納する、環境の通常の作業配置を変更する C++ プロジェクトのダイアログ ボックス[シンボル](../windows/symbols-resource-identifiers.md)Resource.h にします。

開くには、**リソースが含まれています**ダイアログ ボックスで、右クリックして .rc ファイル[リソース ビュー](../windows/resource-view-window.md)を選択し、**リソースが含まれています**ショートカット メニューから。 このダイアログ ボックスには、次のプロパティがあります。

|プロパティ|説明|
|---|---|
|**シンボル ヘッダー ファイル**|リソース ファイルのシンボル定義が格納されているヘッダー ファイルの名前を変更することができます。 詳細については、次を参照してください。[シンボル ヘッダー ファイルの名前を変更する](../windows/changing-the-names-of-symbol-header-files.md)します。|
|**読み取り専用シンボル ディレクティブ**|編集セッション中に変更されるべきではないシンボルが含まれているヘッダー ファイルをインクルードできます。 たとえば、いくつかのプロジェクト間で共有されるシンボル ファイルをインクルードできます。 MFC の .h ファイルをインクルードすることもできます。 詳細については、次を参照してください。[共有 (読み取り専用) または計算型シンボル](../windows/including-shared-read-only-or-calculated-symbols.md)します。|
|**コンパイル時ディレクティブ**|作成され、メイン リソース ファイル内のリソースから個別に編集されているリソース ファイルを含めることができます (など、それらのディレクティブを条件付きでリソースを含む)、コンパイル時ディレクティブを含めることがまたは、カスタム形式でリソースが含まれます。 使用することも、**コンパイル時ディレクティブ ボックス**標準 MFC リソース ファイルをインクルードします。 詳細については、次を参照してください。[コンパイル時にリソースを含む](../windows/how-to-include-resources-at-compile-time.md)します。|

> [!NOTE]
> マークされた .rc ファイルにこれらのテキスト ボックス内のエントリが表示される`TEXTINCLUDE 1`、 `TEXTINCLUDE 2`、および`TEXTINCLUDE 3`それぞれします。 詳細については、次を参照してください[TN035:。複数のリソース ファイルとヘッダー ファイルを使用して、Visual C を使った](../mfc/tn035-using-multiple-resource-files-and-header-files-with-visual-cpp.md)します。

リソース ファイルを使用して変更を行った場合、**リソース ファイルのインクルード**ダイアログ ボックスで、.rc ファイルを閉じてから開き、変更内容を反映する必要があります。

マネージ プロジェクトにリソースを追加する方法については、次を参照してください。 [Resources in Desktop Apps](/dotnet/framework/resources/index)で .NET Framework 開発者ガイド。

## <a name="to-include-resources-in-your-project-at-compile-time"></a>コンパイル時にリソースをインクルードするには

1. 一意のファイル名を持つリソース スクリプト ファイルにリソースを配置します。 使用しない*projectname*.rc、この名前は、メイン リソース スクリプト ファイルを使用するファイル名。

1. .Rc ファイルを右クリックして (で[リソース ビュー](../windows/resource-view-window.md)) 選択**リソース ファイルのインクルード**ショートカット メニューから。

1. **コンパイル時ディレクティブ**ボックスで、追加、 [#include](../preprocessor/hash-include-directive-c-cpp.md)開発環境で、メイン リソース ファイルで新しいリソース ファイルをインクルードします。

   この方法でインクルードされるリソースは、コンパイル時に実行可能ファイルの一部になります。 プロジェクトのメイン .rc ファイルで作業するときに編集または変更を直接使用できません。 別にインクルードされる .rc ファイルを開きます。 含まれていますが、.rc 拡張子を持っていないすべてのファイルは、リソース エディターで編集することはできません。

## <a name="to-specify-include-directories-for-a-specific-resource-rc-file"></a>指定する、特定のリソース (.rc ファイル) のインクルード ディレクトリ

1. ソリューション エクスプ ローラーで .rc ファイルを右クリックして**プロパティ**ショートカット メニューから。

1. **プロパティ ページ**ダイアログ ボックスで、**リソース**左側のウィンドウでノードが、追加のインクルード ディレクトリを指定、**追加のインクルード ディレクトリ**プロパティ。

## <a name="to-find-symbols-in-resources"></a>リソース内のシンボルを検索するには

1. **編集**] メニューの [選択**シンボルの検索**します。

1. [シンボルの検索 ダイアログ ボックス](/visualstudio/ide/go-to)の**検索**ボックスで、ドロップダウン リストから、以前の検索文字列を選択するか、(用、id_accel1 を検索するアクセラレータ キーを入力します。

   > [!TIP]
   > 使用する[正規](/visualstudio/ide/using-regular-expressions-in-visual-studio)検索に使用する必要があります、 [Findinfiles コマンド](/visualstudio/ide/reference/find-command)から、**編集**メニューの代わりに、 **シンボルの検索**コマンド。 正規表現を有効にするが必要、**使用。正規表現**チェック ボックスをオン、[検索 ダイアログ ボックス](/visualstudio/ide/finding-and-replacing-text)します。 右側に、右矢印ボタンを選択できるよう、**検索**検索の正規表現の一覧を表示するボックスです。 この一覧から式を選択すると、検索文字列として設定されます、**検索**ボックス。

1. いずれかの選択、**検索**オプション。

1. **[次を検索]** をクリックします。

> [!NOTE]
> 文字列リソース、アクセラレータ リソース、またはバイナリ リソース内のシンボルは検索できません。

## <a name="requirements"></a>必要条件

Win32

## <a name="see-also"></a>関連項目

[リソース ファイル](../windows/resource-files-visual-studio.md)<br/>
[リソース エディター](../windows/resource-editors.md)<br/>
[シンボル:リソース識別子](../windows/symbols-resource-identifiers.md)<br/>