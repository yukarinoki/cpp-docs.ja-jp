---
title: /w、/W0、/W1、/W2、/W3、/W4、/W1、/W2、/W3、/W4、/Wall、/wd、/we、/wo、/Wv、/WX (警告レベル)
ms.date: 01/31/2018
f1_keywords:
- VC.Project.VCCLCompilerTool.DisableSpecificWarnings
- VC.Project.VCCLCompilerTool.WarningLevel
- VC.Project.VCCLWCECompilerTool.DisableSpecificWarnings
- VC.Project.VCCLCompilerTool.WarnAsError
- VC.Project.VCCLWCECompilerTool.WarnAsError
- /wx
- VC.Project.VCCLWCECompilerTool.WarningLevel
- /wall
- VC.Project.VCCLCompilerTool.TreatSpecificWarningsAsErrors
- /Wv
- /w0
- /w1
- /w2
- /w3
- /w4
- /wd
- /we
- /wo
helpviewer_keywords:
- /W1 compiler option [C++]
- w compiler option [C++]
- -wo compiler option [C++]
- Warning Level compiler option
- W1 compiler option [C++]
- -we compiler option [C++]
- /WX compiler option [C++]
- -wd compiler option [C++]
- WX compiler option [C++]
- wo compiler option [C++]
- Wall compiler option [C++]
- /w compiler option
- W2 compiler option [C++]
- -W2 compiler option [C++]
- wd compiler option [C++]
- /we compiler option [C++]
- we compiler option [C++]
- -W1 compiler option [C++]
- -W4 compiler option [C++]
- -Wall compiler option [C++]
- /Wall compiler option [C++]
- -W0 compiler option [C++]
- W0 compiler option [C++]
- -WX compiler option [C++]
- /wo compiler option [C++]
- W4 compiler option [C++]
- W3 compiler option [C++]
- /wd compiler option [C++]
- warnings, as errors compiler option
- /W3 compiler option [C++]
- /W0 compiler option [C++]
- /W4 compiler option [C++]
- -W3 compiler option [C++]
- -w compiler option [C++]
- /W2 compiler option [C++]
- /Wv compiler option [C++]
ms.openlocfilehash: 7d2fd21c476ef4346aa86e682047ea644183b2f3
ms.sourcegitcommit: d0504e2337bb671e78ec6dd1c7b05d89e7adf6a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/02/2019
ms.locfileid: "74683059"
---
# <a name="w-w0-w1-w2-w3-w4-w1-w2-w3-w4-wall-wd-we-wo-wv-wx-warning-level"></a>/w、/W0、/W1、/W2、/W3、/W4、/W1、/W2、/W3、/W4、/Wall、/wd、/we、/wo、/Wv、/WX (警告レベル)

指定したコンパイルに対してコンパイラが警告を生成する方法を指定します。

## <a name="syntax"></a>構文

> **/w**\
> **/W0**\
> **/W1**\
> **/W2**\
> **/W3**\
> **/W4**\
> **/Wall**\
> **/Wv**\[ **:** _バージョン_] \
> **/Wx**\
> **/w1**の_警告_\
> **/w2**の_警告_\
> **/w3**の_警告_\
> **/w4**の_警告_\
> **/wd**_警告_\
> **/we**の_警告_\
> **/wo**_警告_

## <a name="remarks"></a>Remarks

警告オプションでは、表示するコンパイラ警告とコンパイル全体の警告動作を指定します。

次の表では、警告オプションと関連する引数について説明します。

|オプション|説明|
------------|-----------------|
|**/w**|すべてのコンパイラ警告を非表示にします。|
|**/W0**<br /><br /> **/W1**<br /><br /> **/W2**<br /><br /> **/W3**<br /><br /> **/W4**|コンパイラによって生成される警告のレベルを指定します。 有効な警告レベルは、0 ~ 4 の範囲です。<br />**/W0**すべての警告を抑制します。 これは、 **/w**と同じです。<br />**/W1**は、レベル 1 (重大) の警告を表示します。 **/W1**は、コマンドラインコンパイラの既定の設定です。<br />**/W2**レベル1およびレベル 2 (重要) の警告が表示されます。<br />**/W3**には、レベル1、レベル2、レベル 3 (実稼働品質) の警告が表示されます。 **/W3**は、IDE の既定の設定です。<br />**/W4**は、レベル1、レベル2、レベル3の警告、および既定でオフになっていないすべてのレベル 4 (情報案内) の警告を表示します。 このオプションを使用して、けばに似た警告を提供することをお勧めします。 新しいプロジェクトの場合は、すべてのコンパイルで **/W4**を使用することをお勧めします。これにより、コードの欠陥が発見される可能性が最小限に抑えられます。|
|**/Wall**|**/W4**によって表示されるすべての警告と、 **/W4**に含まれない他のすべての警告 (既定ではオフになっている警告など) を表示します。 詳細については、「[既定でオフになっているコンパイラ警告](../../preprocessor/compiler-warnings-that-are-off-by-default.md)」を参照してください。|
|**/Wv**\[ **:** _バージョン_]|コンパイラバージョン*バージョン*以前で導入された警告のみを表示します。 このオプションを使用すると、新しいバージョンのコンパイラに移行するときにコードの新しい警告を抑制し、既存のビルドプロセスを修正して維持することができます。 省略可能なパラメーターの*バージョン*は、 *nn*[という形式になります。*mm*[。*bbbbb*]] の場合、 *nn*はメジャーバージョン番号、 *mm*は省略可能なマイナーバージョン番号、 *bbbbb*はコンパイラのオプションのビルド番号です。 たとえば、 */Wv:17*を使用して、Visual Studio 2012 で導入された警告を表示します (つまり、メジャーバージョン番号が17より前のバージョンのコンパイラ)。ただし、Visual Studio 2013 (メジャーバージョン 18) 以降で導入された警告を非表示にします。 既定では、 **/Wv**は現在のコンパイラのバージョン番号を使用し、警告は抑制されません。 コンパイラのバージョンによってどの警告が抑制されるかについては、「コンパイラの[バージョン別のコンパイラ警告](../../error-messages/compiler-warnings/compiler-warnings-by-compiler-version.md)」を参照してください。|
|**/WX**|コンパイラ警告をすべてエラーとして扱います。 新しいプロジェクトの場合は、すべてのコンパイルで **/wx**を使用することをお勧めします。すべての警告を解決することで、コードの欠陥が発見される可能性が最小限に抑えられます。<br /><br /> リンカーには、 **/wx**オプションもあります。 詳細については、「[/WX (リンカー警告をエラーとして扱う)](wx-treat-linker-warnings-as-errors.md)」を参照してください。|
|**/w1**_nnnn_<br /><br /> **/w2**_nnnn_<br /><br /> **/w3**_nnnn_<br /><br /> **/w4**_nnnn_|_Nnnn_によって指定された警告番号の警告レベルを設定します。 これにより、特定の警告レベルが設定されている場合に、その警告のコンパイラの動作を変更できます。 これらのオプションを他の警告オプションと組み合わせて使用すると、Visual Studio によって提供される既定の設定ではなく、独自のコーディング標準を警告に適用できます。<br /><br /> たとえば、 **/w34326**を指定すると、レベル1ではなくレベル3の警告として C4326 が生成されます。 **/W34326**オプションと **/W2**オプションの両方を使用してコンパイルした場合、警告 C4326 は生成されません。|
|**/wd**_nnnn_|_Nnnn_によって指定されたコンパイラの警告を非表示にします。<br /><br /> たとえば、 **/wd4326**は、コンパイラの警告 C4326 を抑制します。|
|**/we**_nnnn_|は、 _nnnn_によって指定されたコンパイラの警告をエラーとして扱います。<br /><br /> たとえば、 **/we4326**では、コンパイラによって警告番号 C4326 がエラーとして扱われます。|
|**/wo**_nnnn_|_Nnnn_によって指定されたコンパイラの警告を1回だけ報告します。<br /><br /> たとえば、 **/wo4326**を指定すると、コンパイラによって最初に検出されたときに、警告 C4326 が1回だけ報告されます。|

[/Yc](yc-create-precompiled-header-file.md)オプションを使用してプリコンパイル済みヘッダーを作成するときに、いずれかの警告オプションを使用すると、 [/yu](yu-use-precompiled-header-file.md)オプションを使用してプリコンパイル済みヘッダーを使用すると、同じ警告オプションが再び有効になります。 プリコンパイル済みヘッダーに設定されている警告オプションは、コマンドラインで別の警告オプションを使用してオーバーライドできます。

[#Pragma warning](../../preprocessor/warning.md)ディレクティブを使用して、コンパイル時に特定のソースファイルで報告される警告のレベルを制御できます。

ソースコード内の警告プラグマディレクティブは、 **/w**オプションの影響を受けません。

[ビルドエラーのドキュメント](../../error-messages/compiler-errors-1/c-cpp-build-errors.md)では、警告と警告のレベルについて説明し、特定のステートメントが意図したとおりにコンパイルされない理由を示します。

### <a name="to-set-the-compiler-options-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でコンパイラオプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. **/W0**、 **/W1**、 **/W2**、 **/W3**、 **/W4**、 **/Wall**、 **/Wv**、 **/wx** 、または **/WX-** オプションを設定するには、 > **C/C++**  > **全般** プロパティページの **構成プロパティ** を選択します。

   - **/W0**、 **/W1**、 **/W2**、 **/W3**、 **/W4**、または **/Wall**オプションを設定するには、 **[警告レベル]** プロパティを変更します。

   - **/Wx**オプションまたは **/WX-** オプションを設定するには、 **[警告をエラーとして扱う]** プロパティを変更します。

   - **/Wv**オプションのバージョンを設定するには、 **[警告バージョン]** プロパティにコンパイラのバージョン番号を入力します。

1. **/Wd**オプションまたは **/we**オプションを設定するには、 **[構成プロパティ]**  > [ **C/C++**  > **詳細**設定] プロパティページを選択します。

   - **/Wd**オプションを設定するには、 **[特定の警告を無効に]** する プロパティドロップダウンコントロールを選択し、 **[編集]** を選択します。 **特定の警告を無効にする** ダイアログの 編集 ボックスに、警告番号を入力します。 複数の警告を入力するには、セミコロン ( **;** ) を使用して値を区切ります。 たとえば、C4001 と C4010 の両方を無効にするには、「 **4001; 4010**」と入力します。 **[OK]** を選択して変更を保存し、 **[プロパティページ]** ダイアログに戻ります。

   - **/We**オプションを設定するには、 **[特定の警告をエラーとして扱う]** プロパティドロップダウンコントロールを選択し、 **[編集]** を選択します。 **特定の警告をエラーとして扱う** ダイアログボックスの 編集 ボックスに、警告番号を入力します。 複数の警告を入力するには、セミコロン ( **;** ) を使用して値を区切ります。 たとえば、C4001 と C4010 の両方をエラーとして扱うには、「 **4001; 4010**」と入力します。 **[OK]** を選択して変更を保存し、 **[プロパティページ]** ダイアログに戻ります。

1. **/Wo**オプションを設定するには、 **[構成プロパティ]**  > [ **CC++ /**  > **コマンドライン**] プロパティページを選択します。 **[追加オプション]** ボックスにコンパイラオプションを入力します。

1. **[OK]** を選択して変更を保存します。

### <a name="to-set-the-compiler-option-programmatically"></a>プログラムによってコンパイラオプションを設定するには

- 「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.WarningLevel%2A>」、「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.WarnAsError%2A>」、「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.DisableSpecificWarnings%2A>」、および「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>」を参照してください。

## <a name="see-also"></a>参照

[MSVC コンパイラオプション](compiler-options.md)\
[MSVC コンパイラ コマンド ラインの構文](compiler-command-line-syntax.md)
