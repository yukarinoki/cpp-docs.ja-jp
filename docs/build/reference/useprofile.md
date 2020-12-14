---
description: 詳細については、次を参照してください:/USEPROFILE (スレッドセーフモードで PGO を実行)
title: /USEPROFILE (LTCG での PGO データの使用)
ms.date: 03/14/2018
f1_keywords:
- USEPROFILE
ms.openlocfilehash: c6c293b8467ea308dc2f7b4a4cd916cc5d9ac4c9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97247047"
---
# <a name="useprofile-run-pgo-in-thread-safe-mode"></a>/USEPROFILE (PGO をスレッドセーフモードで実行する)

このリンカーオプションと [/ltcg (リンク時のコード生成](ltcg-link-time-code-generation.md) ) を使用して、リンカーにガイド付き最適化のプロファイル (PGO) トレーニングデータを使用してビルドするように指示します。

## <a name="syntax"></a>構文

> **/USEPROFILE**[**:**{**アグレッシブ** な | **PGD =**_ファイル名_}]

### <a name="arguments"></a>引数

**アグレッシブな**<br/>
この省略可能な引数は、最適化されたコード生成時に積極的な速度の最適化を使用する必要があることを指定します。

**PGD** =*ファイル名*<br/>
.pgd ファイルの基本ファイル名を指定します。 既定では、リンカーは、基本の実行可能ファイル名に .pgd 拡張子を付けて使用します。

## <a name="remarks"></a>解説

**/USEPROFILE** リンカーオプションを **/ltcg** と共に使用して、PGO トレーニングデータに基づいて最適化されたビルドを生成または更新します。 これは、非推奨の **/ltcg: PGUPDATE** オプションと **/LTCG: pgupdate** オプションに相当します。

オプションの **アグレッシブ** 引数は、サイズに関連するヒューリスティックを無効にして、速度の最適化を試みます。 これにより、実行可能ファイルのサイズが大幅に増加し、結果として得られる速度が向上しない可能性があります。 を使用した結果をプロファイリングし、 **積極的** に使用しないように比較する必要があります。 この引数は明示的に指定する必要があります。既定では有効になっていません。

**Pgd** 引数には、使用するトレーニングデータの .pgd ファイルの名前 (省略可能) を指定します。これは、 [/FASTGENPROFILE](genprofile-fastgenprofile-generate-profiling-instrumented-build.md)の場合と同じです。 これは、非推奨の **/PGD** スイッチに相当します。 既定では、 *ファイル名* が指定されていない場合、実行可能ファイルと同じ基本名を持つ .pgd ファイルが使用されます。

**/USEPROFILE** リンカーオプションは、Visual Studio 2015 の新機能です。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. [**構成プロパティ**] [  >  **リンカー** の  >  **最適化**] プロパティページを選択します。

1. [ **リンク時のコード生成** ] プロパティで、[ **リンク時のコード生成 (/Ltcg) を使用する**] を選択します。

1. **[構成プロパティ]**  >  **[リンカー]**  >  **[コマンド ライン]** プロパティ ページを選択します。

1. [**追加オプション**] ボックスに、 **/USEPROFILE** オプションと省略可能な引数を入力します。 **[OK]** を選択して変更を保存します。

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>

## <a name="see-also"></a>関連項目

[/GENPROFILE と /FASTGENPROFILE](genprofile-fastgenprofile-generate-profiling-instrumented-build.md)<br/>
[/LTCG](ltcg-link-time-code-generation.md)<br/>
[ガイド付き最適化のプロファイル](../profile-guided-optimizations.md)<br/>
[Profile-Guided の最適化のための環境変数](../environment-variables-for-profile-guided-optimizations.md)<br/>
