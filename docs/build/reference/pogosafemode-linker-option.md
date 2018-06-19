---
title: /POGOSAFEMODE (スレッド セーフ モードで実行 PGO) |Microsoft ドキュメント
ms.custom: ''
ms.date: 03/14/2018
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
f1_keywords:
- POGOSAFEMODE
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 81392c67b47a0fa90c057ee4295667a054e34498
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32377334"
---
# <a name="pogosafemode-run-pgo-in-thread-safe-mode"></a>/POGOSAFEMODE (スレッド セーフ モードで実行 PGO)

**Visual Studio 2015 以降で/POGOSAFEMODE オプションは推奨されない**です。 使用して、 [/GENPROFILE: 正確な](genprofile-fastgenprofile-generate-profiling-instrumented-build.md)と **/GENPROFILE:NOEXACT**オプションの代わりにします。 **/POGOSAFEMODE**リンカー オプションは、トレーニングの実行プロファイルのガイド付き最適化の (PGO) の中にプロファイル データのキャプチャにスレッド セーフ モードを使用する、インストルメント化されたビルドが作成されたことを指定します。

## <a name="syntax"></a>構文

> **/POGOSAFEMODE**

## <a name="remarks"></a>コメント

最適化のガイド付きプロファイル (PGO) では、2 つのモードを持つ、プロファイリング フェーズ:*高速モード*と*セーフ モード*です。 高速モードでプロファイリングを行う、データ カウンター数を増やしますインクリメント命令が使用されます。 インクリメント命令は高速ですはスレッド セーフではありません。 セーフ モードでプロファイリングを行う、データ カウンター数を増やしますインタロック インクリメント命令が使用されます。 この命令は、時間がかかりますが、増分の命令があり、スレッド セーフでは、同様に、同じ機能を持ちます。

**/POGOSAFEMODE**オプションは、セーフ モードを使用してインストルメント化されたビルドを設定します。 このオプションは、必ず際に使用される、非推奨[/LTCG:PGINSTRUMENT](ltcg-link-time-code-generation.md) PGO instrumentation リンカーのフェーズ中に、指定します。

既定では、PGO プロファイリングは高速モードで動作します。 **/POGOSAFEMODE**がセーフ モードを使用するかどうかにのみ必要です。

実行するには PGO プロファイリングをセーフ モードで、いずれかを使用する必要があります **/GENPROFILE: 正確な**(推奨)、環境変数を使用または[PogoSafeMode](environment-variables-for-profile-guided-optimizations.md)かリンカー スイッチ **/POGOSAFEMODE**、システムによって異なります。 x64 コンピューターでプロファイリングを実行する場合は、リンカー スイッチを使用する必要があります。 X86 でプロファイリングを実行するかどうか、コンピューター、リンカー スイッチを使用するか、PGO インストルメンテーション プロセスを開始する前に、任意の値を環境変数を定義することがあります。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「 [Visual C プロジェクト プロパティの設定](../../ide/working-with-project-properties.md)です。

1. 選択、**構成プロパティ** > **リンカー** > **最適化**プロパティ ページ。

1. **リンク時コード生成**プロパティを選択して**ガイド付き最適化のプロファイルのインストルメント化 (//ltcg:pginstrument)** です。

1. 選択、**構成プロパティ** > **リンカー** > **コマンドライン**プロパティ ページ。

1. 入力、 **/POGOSAFEMODE**にオプション、**追加オプション**ボックス。 選択**OK**して変更を保存します。

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

- 「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>」を参照してください。

## <a name="see-also"></a>関連項目

[/GENPROFILE と/FASTGENPROFILE](genprofile-fastgenprofile-generate-profiling-instrumented-build.md)<br/>
[/LTCG](ltcg-link-time-code-generation.md)<br/>
[ガイド付き最適化のプロファイル](../../build/reference/profile-guided-optimizations.md)<br/>
[ガイド付き最適化のプロファイルの環境変数](../../build/reference/environment-variables-for-profile-guided-optimizations.md)<br/>
