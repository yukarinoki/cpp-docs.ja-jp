---
title: /OPT (最適化)
ms.date: 05/18/2018
f1_keywords:
- VC.Project.VCLinkerTool.OptimizeReferences
- /opt
- VC.Project.VCLinkerTool.OptimizeForWindows98
- VC.Project.VCLinkerTool.EnableCOMDATFolding
- VC.Project.VCLinkerTool.OptimizeFolding
- VC.Project.VCLinkerTool.FoldingIterations
- VC.Project.VCLinkerTool.OptimizeFoldingIterations
helpviewer_keywords:
- LINK tool [C++], controlling optimizations
- -OPT linker option
- linker [C++], optimizations
- OPT linker option
- optimization, linker
- /OPT linker option
ms.assetid: 8f229863-5f53-48a8-9478-243a647093ac
ms.openlocfilehash: b25db4d6c260c3c6751de293aa2a82df8aa05e7e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81336220"
---
# <a name="opt-optimizations"></a>/OPT (最適化)

LINK がビルド時に実行する最適化を制御します。

## <a name="syntax"></a>構文

> **/OPT:**{**参照** | **NOREF**}<br/>
> **/OPT:**{**ICF**[**=**_イテレーション_] |**NOICF**}<br/>
> **/OPT:**{**LBR** | **NOLBR**}

## <a name="arguments"></a>引数

**参照**&#124;**ノレフ**

**/OPT:REF**は、参照されることのない関数とデータを除去します。**/OPT:NOREF**は、参照されていない関数とデータを保持します。

/OPT:REF が有効になっている場合、LINK は *、COMDAT*と呼ばれる、参照されていないパッケージ化された関数とデータを削除します。 この最適化は、中間 COMDAT 除去として知られています。 **/OPT:REF**オプションは、インクリメンタル リンクも無効にします。

クラス宣言の内部で定義されたインライン関数とメンバー関数は、常に COMDAT です。 オブジェクト ファイル内のすべての関数は[、/Gy](gy-enable-function-level-linking.md)オプションを使用してコンパイルされた場合、COMDAT に変換されます。 COMDAT に**定数**データを配置するには、 を使用`__declspec(selectany)`して宣言する必要があります。 削除または折りたたみのデータを指定する方法については、 [selectany](../../cpp/selectany.md)を参照してください。

デフォルトでは **、/OPT:NOREF**または[/DEBUG](debug-generate-debug-info.md)が指定されていない限り、リンカーによって **/OPT:REF**が有効になります。 このデフォルトをオーバーライドし、参照されていない COMDTO をプログラムに残す場合は **、/OPT:NOREF**を指定します。 [/INCLUDE](include-force-symbol-references.md)オプションを使用すると、特定のシンボルの削除をオーバーライドできます。

[/DEBUG](debug-generate-debug-info.md)を指定すると **、/OPT**の既定値は**NOREF**になり、すべての関数がイメージに保持されます。 このデフォルトをオーバーライドしてデバッグビルドを最適化するには **、/OPT:REF**を指定します。 これにより、実行可能ファイルのサイズが小さくなり、デバッグ ビルドでも有効な最適化になります。 デバッグ ビルドで同じ機能を保持するために **、/OPT:NOICF**も指定することをお勧めします。 これにより、スタック トレースを読み取って、圧縮された関数にブレークポイントを設定しやすくなります。

**[** **noICF** &#124; ICF_のイテレーション_]\[**=**

**ICF**\[**=**_の反復_] を使用して、同一の COMDAT 折りたたみを実行します。 リンカー出力から余分な COMDAT シンボルを削除できます。 オプションの*iterations*パラメーターは、重複するシンボルを走査する回数を指定します。 既定の反復回数は 1 です。 イテレーションの回数を増やすと、前回のイテレーションで圧縮されなかった重複が検出されることがあります。

デフォルトでは **、/OPT:NOICF**または[/DEBUG](debug-generate-debug-info.md)が指定されていない限り、リンカーによって **/OPT:ICF**が有効になります。 このデフォルトをオーバーライドして、COMDAT がプログラム内で折り畳まれないようにするには **、/OPT:NOICF**を指定します。

デバッグ ビルドでは、COMDAT のフォールディングを有効にするには **、/OPT:ICF**を明示的に指定する必要があります。 ただし **、/OPT:ICF は**同一のデータまたは関数をマージできるため、スタック トレースに表示される関数名を変更できます。 また、特定の関数にブレークポイントを設定したり、デバッガーでデータを調べたりすることが不可能になり、コードをシングル ステップで実行すると、予期しない関数に移動する可能性があります。 コードの動作は同じですが、デバッガーのプレゼンテーションは非常に混乱する可能性があります。 したがって、コードが小さい場合の利点がこれらの欠点を上回らない限り、デバッグ ビルドで **/OPT:ICF**を使用しないことをお勧めします。

> [!NOTE]
> **/OPT:ICF**は、同じアドレスを異なる関数または読み取り専用データ メンバー **(/Gy**を使用してコンパイルした**場合は const**変数) に割り当てられる可能性があるため、関数または読み取り専用データ メンバーの一意のアドレスに依存するプログラムを中断できます。 詳細については、「[/Gy (関数レベルのリンクの有効化)](gy-enable-function-level-linking.md)」を参照してください。

**LBR** **&#124;・ノーブル**

**/OPT:LBR**および **/OPT:NOLBR**オプションは、ARM バイナリにのみ適用されます。 特定の ARM プロセッサブランチ命令は範囲が限られているため、リンカーが範囲外アドレスへのジャンプを検出すると、ブランチ命令の宛先アドレスを、実際の宛先を対象とする分岐命令を含むコード 「アイランド」のアドレスに置き換えます。 **/OPT:LBR**を使用すると、長いブランチ命令の検出と、コード全体のサイズを最小限に抑える中間コード アイランドの配置を最適化できます。 **/OPT:NOLBR**は、リンカーに対して、長いブランチ命令が検出された場合にコード アイランドを生成するように指示します。

デフォルトでは、インクリメンタル リンクが有効でない場合は **、/OPT:LBR**オプションが設定されます。 非インクリメンタル リンクを使用し、長いブランチの最適化を行わない場合は **、/OPT:NOLBR**を指定します。 **/OPT:LBR**オプションは、インクリメンタル リンクを無効にします。

## <a name="remarks"></a>解説

コマンド ラインで使用すると、リンカーは既定で **/OPT:REF、ICF、LBR**に設定されます。 **/DEBUG**が指定されている場合、デフォルトは **/OPT:NOREF、NOICF、NOLBR**です。

**/OPT**最適化では、一般にイメージサイズが小さくなり、プログラムの速度が向上します。 これらの機能強化は、大規模なプログラムでは大幅に行われる可能性があるため、製品版のビルドでは既定で有効になっています。

リンカーの最適化は、前もって余分な時間がかかりますが、最適化されたコードは、リンカーが修正する再配置が少なく、最終的なイメージを作成する時間を節約し、PDB を処理して書き込むデバッグ情報が少ない場合に、さらに多くの時間を節約します。 最適化が有効になっていると、リンカーの時間の節約により、分析のわずかな追加コストが小さなバイナリを渡すため、全体的にリンク時間が短縮される可能性があります。

**/OPT**引数は、コンマで区切って指定できます。 たとえば **、/OPT:REF /OPT:NOICF**の代わりに **、/OPT:REF,NOICF を**指定できます。

[/VERBOSE](verbose-print-progress-messages.md)リンカー オプションを使用すると **、/OPT:REF**によって削除された関数と **、/OPT:ICF**によって折り畳まれた関数を確認できます。

**/OPT**引数は、Visual Studio IDE の **[新しいプロジェクト**] ダイアログを使用して作成されたプロジェクトに対して設定されることが多く、デバッグ構成とリリース構成では通常は異なる値を持ちます。 プロジェクトでこれらのリンカー オプションに値が設定されていない場合は、プロジェクトの既定値を取得できます。

### <a name="to-set-the-opticf-or-optref-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境で OPT:ICF リンカー オプションまたは OPT:REF リンカー オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. **[構成プロパティ リン** > **カ** > **の最適化**] プロパティ ページを選択します。

1. 次のいずれかのプロパティを変更します。

   - **[COMDAT の圧縮]**

   - **参照**

### <a name="to-set-the-optlbr-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境で OPT:LBR リンカー オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. **[構成プロパティ リン** > **カー** > **コマンド ライン**] プロパティ ページを選択します。

1. [追加オプション] に**オプションを**入力します。

   `/opt:lbr` または `/opt:nolbr`

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.EnableCOMDATFolding%2A> プロパティおよび <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.OptimizeReferences%2A> プロパティを参照してください。

## <a name="see-also"></a>関連項目

- [MSVC リンカーのリファレンス](linking.md)
- [MSVC リンカー オプション](linker-options.md)
