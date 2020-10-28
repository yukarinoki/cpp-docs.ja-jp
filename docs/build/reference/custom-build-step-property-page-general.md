---
title: '[カスタム ビルド ステップ] プロパティ ページ: 全般'
description: この記事では、[プロパティページ] ダイアログボックスの [カスタムビルドステップ] ページで使用できるプロパティについて説明します。
ms.date: 10/27/2020
f1_keywords:
- VC.Project.VCCustomBuildStep.AdditionalInputs
- VC.Project.VCCustomBuildStep.CustomBuildAfterTargets
- VC.Project.VCCustomBuildStep.CustomBuildBeforeTargets
- VC.Project.VCCustomBuildStep.Outputs
- VC.Project.VCCustomBuildStep.Message
- VC.Project.VCCustomBuildStep.Command
helpviewer_keywords:
- project properties, custom build step
- custom build step (general)
ms.assetid: bd319741-0491-46c4-a428-7c61b4b46a02
ms.openlocfilehash: 53f2deef931821981b3301f44ba37660975fb811
ms.sourcegitcommit: 9c801a43ee0d4d84956b03fd387716c818705e0d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/28/2020
ms.locfileid: "92907585"
---
# <a name="custom-build-step-property-page-general"></a>[カスタム ビルド ステップ] プロパティ ページ: 全般

プロジェクトの構成とターゲットプラットフォームの組み合わせごとに、プロジェクトのビルド時に実行するカスタムステップを指定できます。

このページの Linux バージョンについては、「[カスタム ビルド ステップのプロパティ (Linux C++)](../../linux/prop-pages/custom-build-step-linux.md)」を参照してください。

## <a name="general-page"></a>[全般] ページ

- **コマンド ライン**

   カスタム ビルド ステップによって実行されるコマンド。

- **説明**

   カスタム ビルド ステップを実行するときに表示されるメッセージ。

- **出力**

   カスタム ビルド ステップが生成する出力ファイル。 この設定は、インクリメンタル ビルドが正しく機能するために必要です。

- **追加の依存ファイル**

   カスタム ビルド ステップで使用する追加の入力ファイルの、セミコロンで区切られた一覧。

- **[以後に実行] および [以前に実行]**

   ビルド プロセスでカスタム ビルド ステップが実行されるタイミングを、表示されているターゲットを基準にして定義します。 最も一般的に示されているターゲットは、、、 `BuildGenerateSources` `BuildCompile` およびです。これは、 `BuildLink` ビルド処理の主要な手順を表しているためです。 その他の一般的なターゲットは `Midl` 、、 `CLCompile` 、および `Link` です。

- **出力をコンテンツとして扱う**

   このオプションは、パッケージ内のすべてのコンテンツファイルを含むユニバーサル Windows プラットフォームまたは Windows Phone アプリに対してのみ意味があり *`.appx`* ます。

### <a name="to-specify-a-custom-build-step"></a>カスタム ビルド ステップを指定するには

1. メニュー バーで、 **[プロジェクト]**  >  **[プロパティ]** を選択します。 詳しくは、「[Visual Studio で C++ コンパイラとビルド プロパティを設定する](../working-with-project-properties.md)」をご覧ください。

1. [ **プロパティページ** ] ダイアログボックスで、[ **構成プロパティ** ]  >  [ **カスタムビルドステップ** の全般] ページに移動し  >  **General** ます。

1. 設定を変更します。

## <a name="see-also"></a>関連項目

[C++ プロジェクトのプロパティ ページのリファレンス](property-pages-visual-cpp.md)
