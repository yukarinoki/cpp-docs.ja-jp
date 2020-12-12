---
description: 詳細情報:/arch (ARM)
title: /arch (ARM)
ms.date: 11/04/2016
ms.assetid: 4f1406ff-f174-487c-a126-8ab06cf447c1
ms.openlocfilehash: 885b624eb6a470d24d691641d0be63515ee76a49
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97179565"
---
# <a name="arch-arm"></a>/arch (ARM)

ARM でのコード生成のアーキテクチャを指定します。 「 [/Arch (x86)](arch-x86.md) 」および「 [/arch (x64)](arch-x64.md)」も参照してください。

## <a name="syntax"></a>構文

```
/arch:[ARMv7VE|VFPv4]
```

## <a name="arguments"></a>引数

**/arch: ARMv7VE**<br/>
ARMv7VE 仮想化拡張命令の使用を有効にします。

**/arch: VFPv4**<br/>
ARM VFPv4 命令の使用を有効にします。 このオプションを指定しない場合は、VFPv3 が既定値です。

## <a name="remarks"></a>解説

`_M_ARM_FP`マクロ (ARM の場合のみ) は、 **/arch** コンパイラオプションが使用されていた場合はそれを示します。 詳細については、「 [Predefined Macros](../../preprocessor/predefined-macros.md)」を参照してください。

[/Clr](clr-common-language-runtime-compilation.md)を使用してコンパイルする場合、 **/arch** はマネージ関数のコード生成には影響しません。 **/arch** は、ネイティブ関数のコード生成にのみ影響します。

### <a name="to-set-the-archarmv7ve-or-archvfpv4-compiler-option-in-visual-studio"></a>Visual Studio で、/arch:ARMv7VE または/arch:VFPv4 コンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳しくは、「[Visual Studio で C++ コンパイラとビルド プロパティを設定する](../working-with-project-properties.md)」をご覧ください。

1. [ **C/c + +** ] フォルダーを選択します。

1. [ **コマンドライン** ] プロパティページを選択します。

1. [ **追加オプション** ] ボックスで、 `/arch:ARMv7VE` またはを追加し `/arch:VFPv4` ます。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnableEnhancedInstructionSet%2A>

## <a name="see-also"></a>関連項目

[/arch (最小 CPU アーキテクチャ)](arch-minimum-cpu-architecture.md)<br/>
[MSVC コンパイラ オプション](compiler-options.md)<br/>
[MSVC Compiler Command-Line 構文](compiler-command-line-syntax.md)
