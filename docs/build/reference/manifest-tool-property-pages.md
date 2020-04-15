---
title: マニフェスト ツールのプロパティ ページ
ms.date: 07/24/2019
ms.topic: article
f1_keywords:
- VC.Project.VCManifestTool.SuppressStartupBanner
- VC.Project.VCManifestTool.VerboseOutput
- VC.Project.VCManifestTool.AssemblyIdentity
- VC.Project.VCManifestTool.AdditionalManifestFiles
- VC.Project.VCManifestTool.InputResourceManifests
- VC.Project.VCManifestTool.EmbedManifest
- VC.Project.VCManifestTool.OutputManifestFile
- VC.Project.VCManifestTool.ResourceOutputFileName
- VC.Project.VCManifestTool.GenerateCatalogFiles
- VC.Project.VCManifestTool.ManifestFromManagedAssembly
- VC.Project.VCManifestTool.SuppressDependencyElement
- VC.Project.VCManifestTool.GenerateCategoryTags
- VC.Project.VCManifestTool.EnableDPIAwareness
- VC.Project.VCManifestTool.TypeLibraryFile
- VC.Project.VCManifestTool.RegistrarScriptFile
- VC.Project.VCManifestTool.ComponentFileName
- VC.Project.VCManifestTool.ReplacementsFile
- VC.Project.VCManifestTool.UpdateFileHashes
- VC.Project.VCManifestTool.UpdateFileHashesSearchPath
- vc.project.AdditionalOptionsPage
ms.assetid: f33499c4-7733-42d9-80e3-8a5018786965
ms.openlocfilehash: e1d0f1ac889cb915216ceb70d48e36efe4ad21bc
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81336296"
---
# <a name="manifest-tool-property-pages"></a>マニフェスト ツールのプロパティ ページ

これらのページを使用して[、Mt.exe](/windows/win32/sbscs/mt-exe)の全般オプションを指定します。 これらのページは、**プロジェクト** > **プロパティ** > **構成プロパティ** > **マニフェスト ツール**の下にあります。

## <a name="general-property-page"></a>[全般] プロパティ ページ

### <a name="suppress-startup-banner"></a>著作権情報の非表示

   **[はい (/nologo)]** の場合、マニフェスト ツールを起動したとき、Microsoft の標準的な著作権情報が隠されます。 ビルド プロセスの一部として、あるいはビルド環境から mt.exe を実行するとき、ログ ファイルに不要な出力を表示しない場合、このオプションを使用します。

### <a name="verbose-output"></a>詳細出力

   **[はい (/verbose)]** の場合、マニフェスト生成中、追加のビルド情報が表示されます。

### <a name="assembly-identity"></a>アセンブリ ID

/identity オプションを使用して、[\<アセンブリ ID> 要素](/visualstudio/deployment/assemblyidentity-element-clickonce-application)の属性で構成される ID 文字列を指定します。 `name` ID ストリングは属性の値で始まり、その後に*属性* = *値*のペアが続きます。 ID 文字列の属性はコンマで区切られます。

ID 文字列の例を次に示します。`Microsoft.Windows.Common-Controls, processorArchitecture=x86, version=6.0.0.0, type=win32, publicKeyToken=6595b64144ccf1df`

## <a name="input-and-output-property-page"></a>入力および出力プロパティ ページ

### <a name="additional-manifest-files"></a>追加のマニフェスト ファイル

**/manifest** オプションを使用して、マニフェスト ツールで処理またはマージされる追加のマニフェスト ファイルの完全パスを指定します。 完全パスはセミコロンで区切ります。 (マニフェスト [マニフェスト1] [マニフェスト2].)

### <a name="input-resource-manifests"></a>入力リソース マニフェスト

**/inputresource** オプションを使用して、マニフェスト ツールに入力される RT_MANIFEST 型のリソースの完全パスを指定します。 パスの後には、特定のリソース ID を続けることができます。 次に例を示します。

`dll_with_manifest.dll;#1`

### <a name="embed-manifest"></a>埋め込みマニフェスト

- **[はい]** を指定すると、プロジェクト システムによって、アプリケーション マニフェスト ファイルがアセンブリに埋め込まれます。

- **[いいえ]** を指定すると、プロジェクト システムによって、アプリケーション マニフェスト ファイルがスタンドアロン ファイルとして作成されます。

### <a name="output-manifest-file"></a>出力マニフェスト ファイル

出力マニフェスト ファイルの名前を指定します。 マニフェスト ツールで操作されるマニフェスト ファイルが 1 つだけの場合、このプロパティは省略できます。 (アウト:[ファイル];#[リソースID])

### <a name="manifest-resource-file"></a>マニフェスト リソース ファイル

マニフェストをプロジェクト出力に埋め込むために使用する出力リソース ファイルを指定します。

### <a name="generate-catalog-files"></a>カタログ ファイルの生成

**/makecdfs** オプションを使用して、カタログを作成するために使用されるカタログ定義ファイル (.cdf ファイル) をマニフェスト ツールで生成するように指定します。 (/メイクスDFS)

### <a name="generate-manifest-from-managedassembly"></a>ManagedAssembly からのマニフェストの生成

マネージド アセンブリからマニフェストを生成します  (マネージ アセンブリ名:\[ファイル))

### <a name="suppress-dependency-element"></a>依存要素の抑制

マネージ アセンブリと共に使用されます。 は、最終的なマニフェストでの依存関係要素の生成を抑制します。 (-非依存)

### <a name="generate-category-tags"></a>カタログ タグの生成

マネージ アセンブリと共に使用されます。 -category を指定すると、カテゴリ タグが生成されます。 (カテゴリ)

### <a name="dpi-awareness"></a>DPI の認識

アプリケーションが DPI 対応かどうかを指定します。 既定では、この設定は MFC プロジェクトの場合は **[はい]**、それ以外の場合は **[いいえ]** に指定されています。これは、MFC プロジェクトのみが DPI 認識でビルドされるためです。 別の DPI 設定を扱うコードを追加すると、この設定をオーバーライドして **[はい]** にすることができます。 DPI 対応ではないのに DPI 対応として設定すると、アプリケーションが不明瞭にまたは小さく見えることがあります。

**選択肢**

- **なし**
- **高 DPI 対応**
- **モニター単位の高 DPI 対応**

## <a name="isolated-com-property-page"></a>分離 COM プロパティ ページ

分離された COM の詳細については、「[分離アプリケーション](/windows/win32/SbsCs/isolated-applications)と[方法 : COM コンポーネントを使用する分離アプリケーションをビルドする](../how-to-build-isolated-applications-to-consume-com-components.md)」を参照してください。

### <a name="type-library-file"></a>タイプ ライブラリ ファイル

regfree COM マニフェスト サポートに使用するタイプ ライブラリを指定します。 (-tlb:[ファイル])

### <a name="registrar-script-file"></a>レジスタ スクリプト ファイル

regfree COM マニフェストサポートに使用するレジストラー スクリプト ファイルを指定します。 (-rgs:[ファイル])

### <a name="component-file-name"></a>コンポーネント ファイル名

指定した .tlb または .rgs からビルドされるコンポーネントのファイル名を指定します。 (-dll:[ファイル])

### <a name="replacements-file"></a>置換ファイル

RGS ファイル内の置換可能文字列の値を含むファイルを指定します。 (置き換え:[ファイル])

## <a name="advanced-property-page"></a>[詳細プロパティ] ページ

### <a name="update-file-hashes"></a>ファイル ハッシュの更新

ファイル要素で指定されたファイルのハッシュを計算し、この値でハッシュ属性を更新します。 (ハッシュアップデート:[パス])

### <a name="update-file-hashes-search-path"></a>ファイル ハッシュの更新の検索パス

ファイル のファイル の更新時に使用する検索パスを指定します。

### <a name="additional-options"></a>追加オプション

追加オプション

## <a name="see-also"></a>関連項目

[C++ プロジェクトのプロパティ ページのリファレンス](property-pages-visual-cpp.md)
