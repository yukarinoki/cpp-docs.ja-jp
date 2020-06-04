---
title: /Os、/Ot (実行可能ファイルのサイズの優先、実行速度の優先)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLWCECompilerTool.FavorSizeOrSpeed
- /os
- VC.Project.VCCLCompilerTool.FavorSizeOrSpeed
helpviewer_keywords:
- favor fast code compiler option [C++]
- /Os compiler option [C++]
- Ot compiler option [C++]
- /Ot compiler option [C++]
- small machine code
- -Ot compiler option [C++]
- fast code
- favor small code compiler option [C++]
- Os compiler option [C++]
- -Os compiler option [C++]
ms.assetid: 9a340806-fa15-4308-892c-355d83cac0f2
ms.openlocfilehash: 0eda9461b3ef730e0e0a832aa94a688e03c7e1bb
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81336188"
---
# <a name="os-ot-favor-small-code-favor-fast-code"></a>/Os、/Ot (実行可能ファイルのサイズの優先、実行速度の優先)

EXE と DLL のサイズを最小化または最大化します。

## <a name="syntax"></a>構文

```
/Os
/Ot
```

## <a name="remarks"></a>解説

**/Os** (小規模コードを優先) は、コンパイラに速度よりもサイズを優先するように指示することで、EXE と DLL のサイズを最小限に抑えます。 コンパイラは、多くの C および C++ の構成要素を、機能的に類似したマシン コードのシーケンスに減らすことができます。 時折、これらの違いは、サイズと速度のトレードオフを提供します。 **/Os**および **/Ot**オプションを使用すると、一方の設定を他のオプションより優先的に指定できます。

**/Ot** (優先高速コード) は、コンパイラにサイズよりも速度を優先するように指示することにより、EXE と DLL の速度を最大化します。 (これがデフォルトです。コンパイラは、多くの C および C++ の構成要素を、機能的に類似したマシン コードのシーケンスに減らすことができます。 場合によっては、これらの違いはサイズと速度のトレードオフを提供します。 **/Ot**オプションは、速度最大化 ([/O2](o1-o2-minimize-size-maximize-speed.md)) オプションによって暗黙的に指定されます。 **/O2**オプションは、非常に高速なコードを生成するために、いくつかのオプションを組み合わせています。

**/Os**または **/Ot**を使用する場合は[、/Og](og-global-optimizations.md)を指定してコードを最適化する必要があります。

> [!NOTE]
> プロファイリング テストの実行から収集された情報は **、/Ob** **、/O、** または **/Ot**を指定すると有効になる最適化をオーバーライドします。 詳細については、「[ガイド付き最適化のプロファイル」を参照してください](../profile-guided-optimizations.md)。

**x86 固有の仕様→**

次のコード例は、優先小コード (**/Os**) オプションと Favor Fast Code (**/Ot**) オプションの違いを示しています。

> [!NOTE]
> 以下は **、/Os**または **/Ot**を使用する場合の予期される動作を示しています。 ただし、リリースからリリースへのコンパイラの動作は、以下のコードで異なる最適化を生じる可能性があります。

```
/* differ.c
  This program implements a multiplication operator
  Compile with /Os to implement multiply explicitly as multiply.
  Compile with /Ot to implement as a series of shift and LEA instructions.
*/
int differ(int x)
{
    return x * 71;
}
```

以下のマシンコードの断片に示すように、SIZE (**/Os**) に対して、コンパイラは return ステートメントの乗算式を明示的に乗算として実装し、短いが遅いコードシーケンスを生成します。

```
mov    eax, DWORD PTR _x$[ebp]
imul   eax, 71                  ; 00000047H
```

もう 1 つの方法として、SPEED (**/Ot**) を使用してコンパイルされた場合、コンパイラは return ステートメントの multiply`LEA`式を一連のシフトおよび命令として実装し、高速で長いコード シーケンスを生成します。

```
mov    eax, DWORD PTR _x$[ebp]
mov    ecx, eax
shl    eax, 3
lea    eax, DWORD PTR [eax+eax*8]
sub    eax, ecx
```

**エンド x86 特定**

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. **[C/C++]** フォルダーをクリックします。

1. [最適化] プロパティ ページ**を**クリックします。

1. **[優先サイズ] プロパティまたは [速度]** プロパティを変更します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.FavorSizeOrSpeed%2A>」を参照してください。

## <a name="see-also"></a>関連項目

[/O オプション (コードの最適化)](o-options-optimize-code.md)<br/>
[MSVC コンパイラ オプション](compiler-options.md)<br/>
[MSVC コンパイラ コマンド ラインの構文](compiler-command-line-syntax.md)
