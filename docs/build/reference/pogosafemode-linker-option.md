---
description: 詳細情報:/pogoセーフ (スレッドセーフモードで PGO を実行)
title: /Pogoセーフ (スレッドセーフモードで PGO を実行)
ms.date: 03/14/2018
f1_keywords:
- POGOSAFEMODE
ms.openlocfilehash: dfe8d46a3008a1d41156d077e5b87e50ac345e18
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97225922"
---
# <a name="pogosafemode-run-pgo-in-thread-safe-mode"></a>/Pogoセーフ (スレッドセーフモードで PGO を実行)

**/Pogoセーフオプションは、Visual Studio 2015 以降では非推奨とされ** ます。 代わりに、 [/genprofile: EXACT](genprofile-fastgenprofile-generate-profiling-instrumented-build.md) および **/GENPROFILE: noexact** オプションを使用します。 **/Pogoセーフ** リンカーオプションは、インストルメント化されたビルドが、ガイド付き最適化 (PGO) トレーニングの実行時にプロファイルデータキャプチャにスレッドセーフモードを使用するように作成されることを指定します。

## <a name="syntax"></a>構文

> **/POGOSAFEMODE**

## <a name="remarks"></a>解説

ガイド付き最適化のプロファイル (PGO: Profile-Guided Optimization) では、プロファイリング フェーズで *高速モード* と *セーフ モード* の 2 つのモードを使用できます。 プロファイリングが高速モードの場合は、インクリメント命令を使用してデータカウンターを増やします。 インクリメント命令は高速ですが、スレッドセーフではありません。 プロファイルがセーフモードのときは、インタロックインクリメント命令を使用してデータカウンターを増やします。 この命令にはインクリメント命令と同じ機能があり、スレッドセーフですが、処理速度は遅くなります。

**/Pogoセーフ** オプションは、インストルメント化されたビルドをセーフモードを使用するように設定します。 このオプションは、PGO インストルメンテーションリンカーフェーズ中に、非推奨の [/ltcg: PGINSTRUMENT](ltcg-link-time-code-generation.md) が指定されている場合にのみ使用できます。

既定では、PGO プロファイリングは高速モードで動作します。 **/Pogoセーフ** は、セーフモードを使用する場合にのみ必要です。

PGO プロファイルをセーフモードで実行するには、システムに応じて、 **/genprofile: EXACT** (好ましい) を使用するか、環境変数 [pogosafemode](../environment-variables-for-profile-guided-optimizations.md) またはリンカースイッチ **/pogosafemode** を使用する必要があります。 x64 コンピューターでプロファイリングを実行する場合は、リンカー スイッチを使用する必要があります。 X86 コンピューターでプロファイリングを実行する場合は、PGO インストルメンテーションプロセスを開始する前に、リンカースイッチを使用するか、環境変数を任意の値に定義することができます。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. [**構成プロパティ**] [  >  **リンカー** の  >  **最適化**] プロパティページを選択します。

1. [ **リンク時のコード生成** ] プロパティで、[ **ガイド付き最適化のプロファイル-インストルメント (/Ltcg: pginstrument)**] を選択します。

1. **[構成プロパティ]**  >  **[リンカー]**  >  **[コマンド ライン]** プロパティ ページを選択します。

1. [**追加のオプション**] ボックスに、[ **/pogoセーフ**] オプションを入力します。 **[OK]** を選択して変更を保存します。

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>

## <a name="see-also"></a>関連項目

[/GENPROFILE と /FASTGENPROFILE](genprofile-fastgenprofile-generate-profiling-instrumented-build.md)<br/>
[/LTCG](ltcg-link-time-code-generation.md)<br/>
[ガイド付き最適化のプロファイル](../profile-guided-optimizations.md)<br/>
[Profile-Guided の最適化のための環境変数](../environment-variables-for-profile-guided-optimizations.md)<br/>
