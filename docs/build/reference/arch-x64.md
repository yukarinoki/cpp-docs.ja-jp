---
title: /arch (x64)
ms.date: 11/04/2016
ms.assetid: ecda22bf-5bed-43f4-99fb-88aedd83d9d8
ms.openlocfilehash: d1ee086eff73b0538390764ef26b051919d65bcf
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50456798"
---
# <a name="arch-x64"></a>/arch (x64)

x64 でのコード生成のアーキテクチャを指定します。 参照してください[/arch (x86)](../../build/reference/arch-x86.md)と[/arch (ARM)](../../build/reference/arch-arm.md)します。

## <a name="syntax"></a>構文

```
/arch:[AVX|AVX2]
```

## <a name="arguments"></a>引数

**/arch:AVX**<br/>
Advanced Vector Extensions 命令の使用を有効にします。

**/arch:AVX2**<br/>
Advanced Vector Extensions 2 命令の使用を有効にします。

## <a name="remarks"></a>Remarks

**/arch**だけでネイティブ関数の生成のコードに影響します。 使用すると[/clr](../../build/reference/clr-common-language-runtime-compilation.md)をコンパイルする **/arch**マネージ関数のコード生成に影響を与えません。

`__AVX__`プリプロセッサ シンボルが定義されているときに、 **/arch:AVX**コンパイラ オプションを指定します。 `__AVX2__`プリプロセッサ シンボルが定義されているときに、 **/arch:AVX2**コンパイラ オプションを指定します。 詳細については、「 [Predefined Macros](../../preprocessor/predefined-macros.md)」を参照してください。 **/Arch:AVX2**オプションは Visual Studio 2013 Update 2、バージョン 12.0.34567.1 で導入されました。

### <a name="to-set-the-archavx-or-archavx2-compiler-option-in-visual-studio"></a>/arch:AVX または /arch:AVX2 コンパイラ オプションを Visual Studio で設定するには

1. 開く、**プロパティ ページ**プロジェクトのダイアログ ボックス。 詳細については、「[プロジェクト プロパティの操作](../../ide/working-with-project-properties.md)」を参照してください。

1. 選択、**構成プロパティ**、 **C/C++** フォルダー。

1. 選択、**コード生成**プロパティ ページ。

1. **拡張命令セットを有効にする**ドロップダウン ボックスで、選択**Advanced Vector Extensions (//ARCH:AVX)** または**Advanced Vector Extensions 2 (/arch: AVX2)** します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnableEnhancedInstructionSet%2A>

## <a name="see-also"></a>関連項目

[/arch (最小限の CPU アーキテクチャ)](../../build/reference/arch-minimum-cpu-architecture.md)<br/>
[コンパイラ オプション](../../build/reference/compiler-options.md)<br/>
[コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)