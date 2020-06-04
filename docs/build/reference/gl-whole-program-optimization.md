---
title: /GL (プログラム全体の最適化)
ms.date: 11/04/2016
f1_keywords:
- /gl
helpviewer_keywords:
- /GL compiler option [C++]
- whole program optimizations and C++ compiler
- -GL compiler option [C++]
- GL compiler option [C++]
ms.assetid: 09d51e2d-9728-4bd0-b5dc-3b8284aca1d1
ms.openlocfilehash: 875865a32dcb80cb8a6d8fa53646260f3d9413a5
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2020
ms.locfileid: "79439656"
---
# <a name="gl-whole-program-optimization"></a>/GL (プログラム全体の最適化)

プログラム全体の最適化を有効にします。

## <a name="syntax"></a>構文

```
/GL[-]
```

## <a name="remarks"></a>コメント

プログラム全体の最適化により、コンパイラはプログラム内のすべてのモジュールに関する情報を使用して最適化を実行できます。 プログラム全体の最適化を行わないと、最適化はモジュール単位 (コンパイル単位) ごとに実行されます。

プログラム全体の最適化は既定でオフになっており、明示的に有効にする必要があります。 ただし、 **/GL-** を使用して明示的に無効にすることもできます。

すべてのモジュールに関する情報を使用して、コンパイラは次のことを実行できます。

- 関数の境界を越えてレジスタの使用を最適化します。

- グローバルデータの変更を追跡し、負荷とストアの数を減らすことができるようにします。

- ポインターの逆参照によって変更された項目のセットを追跡し、負荷とストアの数を減らすことで、より適切なジョブを実行します。

- 関数が別のモジュールで定義されている場合でも、モジュール内の関数をインライン化します。

**/gl**を使用して生成された .obj ファイルは、 [EDITBIN](editbin-reference.md)および[DUMPBIN](dumpbin-reference.md)のようなリンカーユーティリティでは使用できません。

**/Gl**と[/c](c-compile-without-linking.md)を使用してプログラムをコンパイルする場合は、/ltcg リンカーオプションを使用して出力ファイルを作成する必要があります。

[/Zi](z7-zi-zi-debug-information-format.md)を **/gl**と共に使用することはできません

現在のバージョンで **/gl**を使用して生成されたファイルの形式は、それ以降C++のバージョンのビジュアルでは読み取ることができません。 **/Gl**を使用して生成された .obj ファイルで構成された .lib ファイルは、ユーザーが使用する予定のすべてのバージョンの Visual C++の .lib ファイルのコピーを配布しないようにする必要があります。

**/gl**ファイルとプリコンパイル済みヘッダーファイルを使用して生成された .obj ファイルは **、その .lib**ファイルを生成したコンピューター上でリンクされていない限り、.lib ファイルのビルドには使用しないでください。 .Obj ファイルのプリコンパイル済みヘッダーファイルからの情報は、リンク時に必要になります。

で使用できる最適化と、プログラム全体の最適化の制限事項の詳細については、「 [/ltcg](ltcg-link-time-code-generation.md)」を参照してください。  **/Gl**では、プロファイルガイド付き最適化も使用できます。/LTCG. を参照してください  ガイド付き最適化のプロファイル用にコンパイルするときに、プロファイルガイド付き最適化から関数順序を設定する場合は、 [/gy](gy-enable-function-level-linking.md)または/gyを暗黙的に指定するコンパイラオプションを使用してコンパイルする必要があります。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには

1. 開発環境で **/gl**を指定する方法については、「 [/ltcg (リンク時のコード生成)](ltcg-link-time-code-generation.md) 」を参照してください。

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

1. [https://docs.microsoft.com/azure/active-directory/develop/scenario-protected-web-api-overview](<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.WholeProgramOptimization%2A>) をご覧ください。

## <a name="see-also"></a>参照

[MSVC コンパイラ オプション](compiler-options.md)<br/>
[MSVC コンパイラ コマンド ラインの構文](compiler-command-line-syntax.md)
