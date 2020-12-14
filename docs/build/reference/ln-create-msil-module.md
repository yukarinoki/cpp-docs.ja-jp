---
description: 詳細情報:/LN (MSIL モジュールの作成)
title: /LN (MSIL モジュールの作成)
ms.date: 11/04/2016
f1_keywords:
- /LN
helpviewer_keywords:
- -LN compiler option [C++]
- /LN compiler option [C++]
ms.assetid: 4f38f4f4-3176-4caf-8200-5c7585dc1ed3
ms.openlocfilehash: 63b6f47fe6bef24341d3c19a6ad96ac3808e486e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97190920"
---
# <a name="ln-create-msil-module"></a>/LN (MSIL モジュールの作成)

アセンブリ マニフェストを出力ファイルに挿入できないことを指定します。

## <a name="syntax"></a>構文

```
/LN
```

## <a name="remarks"></a>解説

既定では、 **/LN** は有効ではありません (出力ファイルにアセンブリマニフェストが挿入されます)。

**/LN** を使用する場合は、 [/Clr (共通言語ランタイムのコンパイル)](clr-common-language-runtime-compilation.md)オプションの1つも使用する必要があります。

マニフェストにアセンブリメタデータがないマネージプログラムは、モジュールと呼ばれます。 [/C (リンクを使用せずにコンパイル)](c-compile-without-linking.md)および **/LN** を使用してコンパイルする場合は、リンカーフェーズで [/NOASSEMBLY (MSIL モジュールの作成)](noassembly-create-a-msil-module.md)を指定して出力ファイルを作成します。

アセンブリを構築するためのコンポーネントベースのアプローチを使用する場合は、モジュールを作成することをお勧めします。  つまり、型を作成し、モジュールにコンパイルできます。  次に、1つまたは複数のモジュールからアセンブリを生成できます。  モジュールからアセンブリを作成する方法の詳細については、「 [リンカー入力としての .Netmodule ファイル](netmodule-files-as-linker-input.md) 」または「 [Al.exe (アセンブリリンカー)](/dotnet/framework/tools/al-exe-assembly-linker)」を参照してください。

モジュールの既定のファイル拡張子は .netmodule です。

Visual Studio 2005 より前のリリースでは、 **/clr: noAssembly** を使用してモジュールが作成されました。

MSVC リンカーは、入力として .netmodule ファイルを受け入れます。リンカーによって生成される出力ファイルは、リンカーに対して入力された netmodule のいずれにも実行時の依存関係がないアセンブリまたは .netmodule になります。  詳細については、「 [リンカー入力としての .netmodule ファイル](netmodule-files-as-linker-input.md)」を参照してください。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

- リンカーフェーズで [/NOASSEMBLY (MSIL モジュールの作成)](noassembly-create-a-msil-module.md) を指定して、出力ファイルを作成します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- このコンパイラオプションをプログラムで変更することはできません。

## <a name="see-also"></a>関連項目

[MSVC コンパイラ オプション](compiler-options.md)<br/>
[MSVC Compiler Command-Line 構文](compiler-command-line-syntax.md)
