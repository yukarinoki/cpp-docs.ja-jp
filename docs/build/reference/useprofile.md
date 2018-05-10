---
title: /USEPROFILE (LTCG を含む PGO を使用するデータ) |Microsoft ドキュメント
ms.custom: ''
ms.date: 03/14/2018
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
f1_keywords:
- USEPROFILE
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 156a571eaa3db31b8c5345f1550346503651665d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="useprofile-run-pgo-in-thread-safe-mode"></a>/USEPROFILE (スレッド セーフ モードで実行 PGO)

このリンカー オプションと共に[/LTCG (リンク時コード生成](ltcg-link-time-code-generation.md)プロファイル ガイド付き最適化の (PGO トレーニング データを使用してビルドするようにリンカーに指示します。

## <a name="syntax"></a>構文

> **/USEPROFILE**[**:**{**アグレッシブ**|**PGD =**_filename_}]

### <a name="arguments"></a>引数

**余裕のないです。**<br/>
この省略可能な引数では、最適化されたコードの生成中に積極的な速度の最適化を使用することを指定します。

**PGD**=*ファイル名*<br/>
.pgd ファイルの基本ファイル名を指定します。 既定では、リンカーは、.pgd 拡張子を持つ基本の実行可能ファイル名を使用します。

## <a name="remarks"></a>コメント

**/USEPROFILE**と共にリンカー オプションを使用する **/LTCG**を生成するか、PGO トレーニング データに基づく最適化されたビルドを更新します。 非推奨のと同じ **/LTCG:PGUPDATE**と **/LTCG:PGOPTIMIZE**オプション。

省略可能な**アグレッシブ**引数速度を最適化しようとするサイズに関連するヒューリスティックを無効にします。 これにより、最適化を大幅に、実行可能ファイルのサイズを増やすし、結果として得られる速度を上げることがありますいない可能性があります。 プロファイルし、を使用してを使用していないの結果を比較する必要があります**アグレッシブ**です。 この引数を明示的に指定する必要があります。既定では無効です。

**PGD**オプションと同様、使用するトレーニング データの .pgd ファイルの名前を指定する引数[/GENPROFILE または/FASTGENPROFILE](genprofile-fastgenprofile-generate-profiling-instrumented-build.md)です。 非推奨のと同じ **/PGD**スイッチします。 既定では、ない場合または*filename*が指定されている .pgd ファイルを実行可能ファイルが使用されるものと同じ基本名を持ちます。

**/USEPROFILE**リンカー オプションは、Visual Studio 2015 の新機能です。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「 [Visual C プロジェクト プロパティの設定](../../ide/working-with-project-properties.md)です。

1. 選択、**構成プロパティ** > **リンカー** > **最適化**プロパティ ページ。

1. **リンク時コード生成**プロパティを選択して**を使用してリンク時コード生成 (/LTCG)** です。

1. 選択、**構成プロパティ** > **リンカー** > **コマンドライン**プロパティ ページ。

1. 入力、 **/USEPROFILE**オプションと省略可能な引数を**追加オプション**ボックス。 選択**OK**して変更を保存します。

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

- 「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>」を参照してください。

## <a name="see-also"></a>関連項目

[/GENPROFILE と/FASTGENPROFILE](genprofile-fastgenprofile-generate-profiling-instrumented-build.md)<br/>
[/LTCG](ltcg-link-time-code-generation.md)<br/>
[ガイド付き最適化のプロファイル](../../build/reference/profile-guided-optimizations.md)<br/>
[ガイド付き最適化のプロファイルの環境変数](../../build/reference/environment-variables-for-profile-guided-optimizations.md)<br/>
