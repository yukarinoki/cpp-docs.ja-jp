---
title: /Os、/Ot (実行可能ファイルのサイズの優先、実行速度の優先)
description: MSVC コンパイラオプション/Os および/Ot は、コードを最適化するときにサイズまたは速度を優先するかどうかを指定します。
ms.date: 07/08/2020
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
ms.openlocfilehash: 384019ddf7b80b8dd4e00197d73d1e4ac536634c
ms.sourcegitcommit: 80c8a512b361bd84e38958beb1a1bf6db7434021
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2020
ms.locfileid: "86180826"
---
# <a name="os-ot-favor-small-code-favor-fast-code"></a>`/Os`、 `/Ot` (小さいコードを優先、高速コードを優先)

Exe と Dll のサイズを最小化または最大化します。

## <a name="syntax"></a>構文

> **`/Os`**\
> **`/Ot`**

## <a name="remarks"></a>解説

**`/Os`**(小さいコードを優先) コンパイラが速度よりもサイズを優先するように指示することにより、Exe と Dll のサイズを最小限に抑えます。 コンパイラは、C および C++ のさまざまな構造を、コンピューターコードの機能的に似たシーケンスに減らすことができます。 これらの違いによって、サイズと速度のトレードオフが生じることがあります。 **`/Os`** オプションとオプションを使用すると、もう一方の **`/Ot`** 優先順位を指定できます。

**`/Ot`**(高速コードを優先) は、サイズよりも速い速度を優先するようコンパイラに指示することによって、Exe と Dll の速度を最大にします。 **`/Ot`** は、最適化が有効になっている場合の既定値です。 コンパイラは、C および C++ のさまざまな構造を、コンピューターコードの機能的に似たシーケンスに減らすことができます。 これらの違いによって、サイズと速度のトレードオフが生じることがあります。 **`/Ot`** オプションは、([速度を最大にする]) オプションによって示され [`/O2`](o1-o2-minimize-size-maximize-speed.md) ます。 オプションには、 **`/O2`** より高速なコードを生成するためのオプションがいくつか組み込まれています。

> [!NOTE]
> プロファイルテストを実行したときに収集された情報は **`/Ob`** 、、、またはを指定した場合に有効な最適化をオーバーライドし **`/Os`** **`/Ot`** ます。 詳細については、「[ガイド付き最適化のプロファイル](../profile-guided-optimizations.md)」を参照してください。

### <a name="x86-specific-example"></a>x86 固有の例

次のコード例は、 **`/Os`** ([小さいコードを優先]) オプションと [ **`/Ot`** (高速コードを優先)] オプションの違いを示しています。

> [!NOTE]
> この例では、またはを使用する場合の想定される動作について説明し **`/Os`** **`/Ot`** ます。 ただし、リリースからリリースへのコンパイラの動作により、以下のコードの最適化が異なる場合があります。

```c
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

次のマシンコードのフラグメントに示されているように、 *`differ.c`* が size () に対してコンパイルされると、 **`/Os`** コンパイラは return ステートメント内の乗算式を明示的に乗算として実装し、短い遅延したコードシーケンスを生成します。

```asm
mov    eax, DWORD PTR _x$[ebp]
imul   eax, 71                  ; 00000047H
```

また、 *`differ.c`* を speed () 用にコンパイルすると、 **`/Ot`** コンパイラは return ステートメント内の乗算式を一連のシフトとして実装し、 `LEA` 高速かつ長いコードシーケンスを生成する命令を実装します。

```asm
mov    eax, DWORD PTR _x$[ebp]
mov    ecx, eax
shl    eax, 3
lea    eax, DWORD PTR [eax+eax*8]
sub    eax, ecx
```

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. [**構成プロパティ**] [  >  **C/c + +**  >  **最適化**] プロパティページを選択します。

1. "**サイズまたは速度を優先**" プロパティを変更します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.FavorSizeOrSpeed%2A>

## <a name="see-also"></a>関連項目

[/O オプション (コードの最適化)](o-options-optimize-code.md)<br/>
[MSVC コンパイラ オプション](compiler-options.md)<br/>
[MSVC コンパイラ コマンド ラインの構文](compiler-command-line-syntax.md)
