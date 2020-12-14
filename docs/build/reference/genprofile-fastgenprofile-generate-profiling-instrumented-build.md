---
description: 詳細情報:/genprofile、/FASTGENPROFILE (プロファイリングインストルメントビルドの生成)
title: /GENPROFILE、/FASTGENPROFILE (プロファイル インストルメント ビルドの生成)
ms.date: 03/14/2018
f1_keywords:
- GENPROFILE
- FASTGENPROFILE
- /GENPROFILE
- /FASTGENPROFILE
helpviewer_keywords:
- GENPROFILE
- FASTGENPROFILE
ms.assetid: deff5ce7-46f5-448a-b9cd-a7a83a6864c6
ms.openlocfilehash: 7bb0f9b1c7a6036c5e721f79b438bf9dd6504111
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97200235"
---
# <a name="genprofile-fastgenprofile-generate-profiling-instrumented-build"></a>/GENPROFILE、/FASTGENPROFILE (プロファイル インストルメント ビルドの生成)

ガイド付き最適化のプロファイル (PGO) をサポートするために、リンカーによる .pgd ファイルの生成を指定します。 **/Genprofile** と **/FASTGENPROFILE** は異なる既定のパラメーターを使用します。 プロファイル時の速度とメモリ使用量の精度を優先するには、 **/genprofile** を使用します。 **/FASTGENPROFILE** を使用すると、メモリ使用量が小さくなり、精度が向上します。

## <a name="syntax"></a>構文

> **/Genprofile** \[**:**{ \[ **COUNTER32** \| **COUNTER64**] \| \[ **EXACT** \| **noexact**] \| **memmax =** _#_ \| **memmax =** _#_ \| \[ **PATH** \| **noexact**] \| \[ **trackeh** \| **notrackeh** ] \| **PGD =**_filename_}] \
> **/FASTGENPROFILE** \[**:**{ \[ **COUNTER32** \| **COUNTER64**] \| \[ **EXACT** \| **noexact**] \| **memmax =** _#_ \| **memmax =** _#_ \| [**PATH** \| **noexact** ] \| \[ **trackeh** \| **notrackeh** ] \| **PGD =**_filename_}]

### <a name="arguments"></a>引数

次のいずれかの **引数を指定すること** ができます、 **/FASTGENPROFILE** です。 ここでパイプ () 文字で区切られた引数 **|** は、相互に排他的です。 オプションを区切るには、コンマ (**,**) 文字を使用します。

**COUNTER32** &#124; **COUNTER64**<br/>
**COUNTER32** を使用して32ビットプローブカウンターの使用を指定し、 **COUNTER64** を使用して64ビットプローブカウンターを指定します。 **/Genprofile** を指定すると、既定値は **COUNTER64** になります。 **/FASTGENPROFILE** を指定すると、既定値は **COUNTER32** になります。

**厳密** な &#124; **noexact**<br/>
プローブにスレッドセーフなインタロックインクリメントを指定するには、 **EXACT** を使用します。 **Noexact** は、プローブの保護されていないインクリメント操作を指定します。 既定値は **Noexact** です。

**Memmax** =*value*、 **memmin** = *値*<br/>
**Memmax** と **memmax** を使用して、メモリ内のトレーニングデータの最大予約サイズと最小予約サイズを指定します。 値は、予約するメモリ量 (バイト単位) です。 既定では、これらの値は内部ヒューリスティックによって決定されます。

**パス**  &#124; **nopath** <br/>
**パス** を使用して、関数への一意のパスごとに個別の PGO カウンターのセットを指定します。 関数ごとにカウンターのセットを1つだけ指定するには、 **Nopath**  を使用します。 **/Genprofile** を指定した場合、既定値は **PATH** です。 **/FASTGENPROFILE** を指定した場合、既定値は **nopath** です。

**Trackeh**  &#124; **Notrackeh** <br/>
トレーニング中に例外がスローされた場合に、追加のカウンターを使用して正確なカウントを保持するかどうかを指定します。 **Trackeh** を使用して、正確なカウントに追加のカウンターを指定します。 **Notrackeh** を使用して、例外処理を使用しないコード、またはトレーニングシナリオで例外を発生させないコードに1つのカウンターを指定します。  **/Genprofile** を指定した場合、既定値は **trackeh** です。 **/FASTGENPROFILE** を指定する場合、既定値は **Notrackeh** です。

**PGD** =*ファイル名*<br/>
.pgd ファイルの基本ファイル名を指定します。 既定では、リンカーは、基本の実行可能イメージのファイル名に .pgd 拡張子を付けて使用します。

## <a name="remarks"></a>解説

/FASTGENPROFILE **オプションは、** ガイド付き最適化のプロファイル (PGO) のためのアプリケーショントレーニングをサポートするために必要なプロファイルインストルメンテーションファイルを生成するようにリンカーに指示します。 これらのオプションは、Visual Studio 2015 で新しく追加されたものです。 これらのオプションは、非推奨の **/ltcg: PGINSTRUMENT**、 **/PGD** 、および **/Pogoセーフ** オプションと、 **pogoセーフ**、 **VCPROFILE_ALLOC_SCALE** および **VCPROFILE_PATH** 環境変数に優先します。 アプリケーションのトレーニングによって生成されたプロファイル情報が、ビルド中に入力として使用され、対象のプログラム全体の最適化が実行されます。 アプリのトレーニング中とビルド中にパフォーマンスのためのさまざまなプロファイル機能を制御する追加のオプションを設定することができます。 既定のオプションである **/genprofile** では、特に大規模で複雑なマルチスレッドアプリの場合に、最も正確な結果が得られます。 **/FASTGENPROFILE** オプションは、精度を犠牲にして、トレーニング中のメモリフットプリントが小さく、パフォーマンスが速くなるように、異なる既定値を使用します。

**/FASTGENPROFILE** の **/genprofile** を使用してビルドした後、インストルメント化されたアプリを実行すると、プロファイル情報がキャプチャされます。 この情報は、 [/USEPROFILE](useprofile.md) リンカーオプションを指定してプロファイリング手順を実行し、最適化されたビルド手順をガイドするときにキャプチャされます。 アプリをトレーニングする方法と収集されたデータの詳細については、「 [ガイド付き最適化のプロファイル](../profile-guided-optimizations.md)」を参照してください。

また、 **/genprofile** または **/FASTGENPROFILE** を指定する場合は、 **/ltcg** も指定する必要があります。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. **[構成プロパティ]**  >  **[リンカー]**  >  **[コマンド ライン]** プロパティ ページを選択します。

1. [**追加のオプション**] ボックス **に、** **/FASTGENPROFILE** オプションと引数を入力します。 **[OK]** を選択して変更を保存します。

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>

## <a name="see-also"></a>関連項目

[MSVC リンカーのリファレンス](linking.md)<br/>
[MSVC リンカー オプション](linker-options.md)<br/>
[/LTCG (リンク時のコード生成)](ltcg-link-time-code-generation.md)<br/>
