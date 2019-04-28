---
title: /LN (MSIL モジュールの作成)
ms.date: 11/04/2016
f1_keywords:
- /LN
helpviewer_keywords:
- -LN compiler option [C++]
- /LN compiler option [C++]
ms.assetid: 4f38f4f4-3176-4caf-8200-5c7585dc1ed3
ms.openlocfilehash: 18b0e72d50f328afc1f2856f833cec1aa7d46f30
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62176217"
---
# <a name="ln-create-msil-module"></a>/LN (MSIL モジュールの作成)

アセンブリ マニフェストを出力ファイルに挿入できないことを指定します。

## <a name="syntax"></a>構文

```
/LN
```

## <a name="remarks"></a>Remarks

既定では、 **/LN**は無効 (アセンブリ マニフェストを出力ファイルに挿入します)。

ときに **/LN**を使用するのいずれか、 [/clr (共通言語ランタイムのコンパイル)](clr-common-language-runtime-compilation.md)オプションも使用する必要があります。

マニフェストにアセンブリ メタデータがないマネージ プログラムには、モジュールが呼び出されます。 コンパイルする場合[(コンパイル リンクなしの)/c](c-compile-without-linking.md)と **/LN**、指定[/NOASSEMBLY (MSIL モジュールの作成)](noassembly-create-a-msil-module.md)出力ファイルを作成するリンカーのフェーズでします。

アセンブリを構築するためのコンポーネント ベースのアプローチを実行する場合は、モジュールを作成することがあります。  つまり、型を作成し、モジュールにコンパイルできます。  次に、1 つまたは複数のモジュールからアセンブリを生成できます。  モジュールからアセンブリを作成する方法の詳細については、次を参照してください。[リンカー入力としての .netmodule ファイル](netmodule-files-as-linker-input.md)または[Al.exe (アセンブリ リンカー)](/dotnet/framework/tools/al-exe-assembly-linker)します。

モジュールの既定のファイル拡張子は、.netmodule です。

Visual C 2005 より前に、の Visual C のリリースでは、モジュールで作成された **/clr:noAssembly**します。

MSVC リンカー入力としての .netmodule ファイルを受け入れるし、リンカーによって生成された出力ファイルは、アセンブリまたは実行時の依存しない、リンカーに .netmodule のいずれかで .netmodule になります。  詳細については、「 [リンカー入力としての .netmodule ファイル](netmodule-files-as-linker-input.md)」を参照してください。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境において、このコンパイラ オプションを設定する方法

- 指定[/NOASSEMBLY (MSIL モジュールの作成)](noassembly-create-a-msil-module.md)出力ファイルを作成するリンカーのフェーズでします。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- このコンパイラ オプションをプログラムで変更することはできません。

## <a name="see-also"></a>関連項目

[MSVC コンパイラ オプション](compiler-options.md)<br/>
[MSVC コンパイラ コマンド ラインの構文](compiler-command-line-syntax.md)
