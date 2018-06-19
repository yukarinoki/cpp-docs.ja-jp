---
title: /GENPROFILE、/FASTGENPROFILE (プロファイル インストルメント ビルドの生成) |Microsoft ドキュメント
ms.custom: ''
ms.date: 03/14/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- GENPROFILE
- FASTGENPROFILE
- /GENPROFILE
- /FASTGENPROFILE
helpviewer_keywords:
- GENPROFILE
- FASTGENPROFILE
ms.assetid: deff5ce7-46f5-448a-b9cd-a7a83a6864c6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 05d7961ff46661b8f6df2768591932699c3965d4
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32379303"
---
# <a name="genprofile-fastgenprofile-generate-profiling-instrumented-build"></a>/GENPROFILE、/FASTGENPROFILE (プロファイル インストルメント ビルドの生成)

ガイド付き最適化のプロファイル (PGO) をサポートするために、リンカーによる .pgd ファイルの生成を指定します。 **/GENPROFILE**と **/FASTGENPROFILE**異なる既定のパラメーターを使用します。 使用して **/GENPROFILE**速度とメモリ使用量をプロファイリング実行中に有効桁数を優先するようにします。 使用して **/FASTGENPROFILE**精度より小さいメモリ使用量と速度を優先するようにします。

## <a name="syntax"></a>構文

> **/GENPROFILE**[**:**{[**COUNTER32**|**COUNTER64**]|[**EXACT**|**NOEXACT**]|**MEMMAX=**_#_|**MEMMIN=**_#_|[**PATH**|**NOPATH** ]|[**TRACKEH** |**NOTRACKEH** ]|**PGD=**_filename_}]<br/>
> **/FASTGENPROFILE**[**:**{[**COUNTER32**|**COUNTER64**]|[**EXACT**|**NOEXACT**]|**MEMMAX=**_#_|**MEMMIN=**_#_|[**PATH**|**NOPATH** ]|[**TRACKEH** |**NOTRACKEH** ]|**PGD=**_filename_}]

### <a name="arguments"></a>引数

次の引数のいずれかを指定するを **/GENPROFILE**または **/FASTGENPROFILE**です。 次に示す引数が、パイプで区切られた (**|**) 文字は相互に排他的です。 コンマを使用して (**、**) オプションを区切る文字です。

**COUNTER32** &AMP;#124; **COUNTER64**<br/>
使用して**COUNTER32** 32 ビットのプローブのカウンターの使用を指定して**COUNTER64**を 64 ビットのプローブのカウンターを指定します。 指定すると **/GENPROFILE**、既定値は**COUNTER64**です。 指定すると **/FASTGENPROFILE**、既定値は**COUNTER32**です。

**正確な** &AMP;#124; **NOEXACT は、**<br/>
使用して**EXACT**プローブのスレッド セーフであるインタロックされた増分値を指定します。 **Noexact は、** プローブの保護されていないインクリメント操作を指定します。 既定値は **、NOEXACT**です。

**MEMMAX**=*値*、 **MEMMIN**=*値*<br/>
使用して**MEMMAX**と**MEMMIN**をメモリ内のトレーニング データの最大値と最小の予約サイズを指定します。 値は、予約するメモリ量 (バイト単位) です。 既定では、これらの値は内部ヒューリスティックによって決定されます。

**パス**&AMP;#124; **NOPATH**  <br/>
使用して**パス**を別の関数に一意のパスごとの PGO カウンターのセットを指定します。 使用して**NOPATH**関数の各カウンターの 1 つだけのセットを指定します。 指定すると **/GENPROFILE**、既定値は**パス**です。 指定すると **/FASTGENPROFILE**、既定値は**NOPATH**です。

**TRACKEH**  &#124; **NOTRACKEH** <br/>
トレーニング中に例外がスローされた場合に、追加のカウンターを使用して正確なカウントを保持するかどうかを指定します。 使用して**TRACKEH**正確な数の追加のカウンターを指定します。 使用して**NOTRACKEH**例外を使用しないコードの 1 つのカウンターを指定するまたは処理が発生しない、トレーニング シナリオでの例外。  指定すると **/GENPROFILE**、既定値は**TRACKEH**です。 指定すると **/FASTGENPROFILE**、既定値は**NOTRACKEH**です。

**PGD**=*ファイル名*<br/>
.pgd ファイルの基本ファイル名を指定します。 既定では、リンカーは、基本の実行可能イメージのファイル名に .pgd 拡張子を付けて使用します。

## <a name="remarks"></a>コメント

**/GENPROFILE**と **/FASTGENPROFILE**オプション プロファイル ガイド付き最適化の (PGO) のアプリケーション トレーニングをサポートするために必要なプロファイル インストルメンテーション ファイルを生成するようにリンカーに指示します。 これらのオプションは、Visual Studio 2015 の新機能です。 非推奨にこれらのオプションを必要に応じて **/LTCG:PGINSTRUMENT**、 **/PGD**と **/POGOSAFEMODE**オプションおよび**PogoSafeMode**、 **VCPROFILE_ALLOC_SCALE**と**VCPROFILE_PATH**環境変数。 アプリケーションのトレーニングによって生成されたプロファイル情報が、ビルド中に入力として使用され、対象のプログラム全体の最適化が実行されます。 アプリのトレーニング中とビルド中にパフォーマンスのためのさまざまなプロファイル機能を制御する追加のオプションを設定することができます。 既定のオプションで指定された **/GENPROFILE**特に大規模で複雑なマルチ スレッド アプリケーションの場合、最も正確な結果を提供します。 **/FASTGENPROFILE**オプションでは、別の既定値を低いメモリ使用量とトレーニングの精度を犠牲にして、パフォーマンスが高速にします。

使用してビルドした後に、インストルメントされたアプリを実行するときに、プロファイル情報がキャプチャ **/GENPROFILE**の **/FASTGENPROFILE**です。 指定すると、この情報がキャプチャされた、 [/USEPROFILE](useprofile.md)リンカー オプションをプロファイリングを実行する手順し、最適化されたビルド手順について説明するために使用します。 アプリをトレーニングする方法の詳細と、収集したデータの詳細については、次を参照してください。[ガイド付き最適化のプロファイル](profile-guided-optimizations.md)です。

指定する必要がありますも **/LTCG**を指定すると **/GENPROFILE**または **/FASTGENPROFILE**です。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「 [Visual C プロジェクト プロパティの設定](../../ide/working-with-project-properties.md)です。

1. 選択、**構成プロパティ** > **リンカー** > **コマンドライン**プロパティ ページ。

1. 入力、 **/GENPROFILE**または **/FASTGENPROFILE**オプションと引数を**追加オプション**ボックス。 選択**OK**して変更を保存します。

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

- 「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>」を参照してください。

## <a name="see-also"></a>関連項目

[リンカー オプションの設定](../../build/reference/setting-linker-options.md)<br/>
[リンカー オプション](../../build/reference/linker-options.md)<br/>
[/LTCG (リンク時のコード生成)](../../build/reference/ltcg-link-time-code-generation.md)<br/>
