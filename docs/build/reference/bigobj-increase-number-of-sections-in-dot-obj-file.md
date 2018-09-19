---
title: -bigobj (のセクションの数を増加します。Obj ファイル) |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /bigobj
dev_langs:
- C++
helpviewer_keywords:
- -bigobj compiler option [C++]
- /bigobj compiler option [C++]
- bigobj compiler option [C++]
ms.assetid: ba94d602-4015-4a8d-86ec-49241ab74c12
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5f10456bea8be552df42efe135818ac9c47393fc
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45721488"
---
# <a name="bigobj-increase-number-of-sections-in-obj-file"></a>/bigobj (.obj ファイル内のセクションの数を増やす)

**/bigobj**のセクションでは、オブジェクト ファイルを格納できる数を増やします。

## <a name="syntax"></a>構文

```
/bigobj
```

## <a name="remarks"></a>Remarks

既定では、オブジェクト ファイルはアドレス指定可能なセクションを最大 65,536 (2^16) 保持できます。 これは、どのターゲット プラットフォームを指定したかにかかわらない場合です。 **/bigobj** 4,294,967,296 するアドレスの量が増加 (2 ^32)。

ほとんどのモジュールでは、65,536 を超えるセクションを格納する .obj ファイルを生成することはありません。 しかし、マシンによって生成されるコード、またはテンプレート ライブラリを多用するコードでは、より多くのセクションを保持できる .obj ファイルを必要とする可能性があります。 **/bigobj**がユニバーサル Windows プラットフォーム (UWP) プロジェクトで既定で有効になって、コンピューターによって生成された XAML コードに含まれるヘッダーの数が多いためです。 UWP アプリ プロジェクトでこのオプションを無効にした場合は、コンパイラ エラー C1128 が発生する可能性があります。

Visual C 2005 より前に付属していたリンカーで生成された .obj ファイルを読み取ることができません **/bigobj**します。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[プロジェクトのプロパティの操作](../../ide/working-with-project-properties.md)」を参照してください。

1. **[C/C++]** フォルダーをクリックします。

1. **[コマンド ライン]** プロパティ ページをクリックします。

1. **[追加のオプション]** ボックスにコンパイラ オプションを入力します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>

## <a name="see-also"></a>関連項目

[コンパイラ オプション](../../build/reference/compiler-options.md)<br/>
[コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)