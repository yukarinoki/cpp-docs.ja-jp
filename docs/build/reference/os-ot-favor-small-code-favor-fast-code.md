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
ms.openlocfilehash: c2abf23c15e6550a6d115f2e2b41a9c59de5fa3a
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57424640"
---
# <a name="os-ot-favor-small-code-favor-fast-code"></a>/Os、/Ot (実行可能ファイルのサイズの優先、実行速度の優先)

最小化または Exe および Dll のサイズを最大化します。

## <a name="syntax"></a>構文

```
/Os
/Ot
```

## <a name="remarks"></a>Remarks

**/Os** (小さなコードのどちらを優先) サイズの優先順位の速度をコンパイラに指示して Exe および Dll のサイズを最小限に抑えられます。 コンパイラは、機能的に同等のマシン語コードの多くの C および C++ の構造を減らすことができます。 場合によってはこれらの違いは、サイズと速度のトレードオフを提供します。 **/Os**と **/Ot**オプションを使用すると、相互の基本設定を指定できます。

**/Ot** (優先する高速コード) では、Exe および Dll の速度を最大限のサイズを超える速度を優先するようにコンパイラに指示しています。 (これは、既定値です)。コンパイラは、機能的に同等のマシン語コードの多くの C および C++ の構造を減らすことができます。 場合によっては、これらの違いは、サイズと速度のトレードオフを提供します。 速度の最大化が/Ot オプションが含まれる ([/O2](../../build/reference/o1-o2-minimize-size-maximize-speed.md)) オプション。 **/O2**オプションは、非常に高速なコードを生成するためにいくつかのオプションを結合します。

使用する場合 **/Os**または **/Ot**、その後も指定する必要があります[/Og](../../build/reference/og-global-optimizations.md)コードを最適化します。

> [!NOTE]
>  プロファイリングのテスト実行から収集される情報はそれ以外の場合に効果を指定する場合の最適化が上書きされます **/Ob**、 **/Os**、または **/Ot**します。 詳細については、[ガイド付き最適化の](../../build/reference/profile-guided-optimizations.md)します。

**x86 固有**

次のコード例は、優先する小さなコードの間の違いを示します (**/Os**) オプションと優先する高速のコード (**/Ot**) オプション。

> [!NOTE]
>  使用する場合、次に、予想される動作について説明します **/Os**または **/Ot**します。 ただし、コンパイラの動作リリースごとに次のコードの最適化が異なる可能性があります。

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

以下のマシン語コードのフラグメントに示すように DIFFER.c がコンパイルされたときのサイズ (**/Os**)、コンパイラの実装、return ステートメントで式を乗算として明示的に、コードの短いが低速のシーケンスを生成するには、乗数値。

```
mov    eax, DWORD PTR _x$[ebp]
imul   eax, 71                  ; 00000047H
```

速度の DIFFER.c がコンパイルされたときに代わりに、(**/Ot**)、コンパイラの実装、一連のシフトとして return ステートメントで式を乗算と`LEA`コードの高速であるが、長いシーケンスを生成する手順。

```
mov    eax, DWORD PTR _x$[ebp]
mov    ecx, eax
shl    eax, 3
lea    eax, DWORD PTR [eax+eax*8]
sub    eax, ecx
```

**END x86 固有**

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境において、このコンパイラ オプションを設定する方法

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[プロジェクトのプロパティの操作](../../ide/working-with-project-properties.md)」を参照してください。

1. **[C/C++]** フォルダーをクリックします。

1. をクリックして、**最適化**プロパティ ページ。

1. 変更、**速度またはサイズを優先**プロパティ。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.FavorSizeOrSpeed%2A>

## <a name="see-also"></a>関連項目

[/O オプション (コードの最適化)](../../build/reference/o-options-optimize-code.md)<br/>
[コンパイラ オプション](../../build/reference/compiler-options.md)<br/>
[コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)
