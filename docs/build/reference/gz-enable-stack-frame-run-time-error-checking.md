---
description: 詳細については、次を参照してください:/GZ (スタックフレームの有効化 Run-Time エラーチェック)
title: /GZ (スタック フレームのランタイム エラー チェックの有効化)
ms.date: 11/04/2016
f1_keywords:
- /gz
helpviewer_keywords:
- -GZ compiler option [C++]
- release-build errors
- /GZ compiler option [C++]
- GZ compiler option [C++]
- debug builds, catch release-build errors
ms.assetid: b3efeeff-d5e3-4057-91c9-f6fc73d0270c
ms.openlocfilehash: 0b0936037c265bf57413c458ffc0a831184cb074
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97191694"
---
# <a name="gz-enable-stack-frame-run-time-error-checking"></a>/GZ (スタック フレームのランタイム エラー チェックの有効化)

は、 [/rtc (実行時エラーチェック)](rtc-run-time-error-checks.md) オプションと同じ操作を実行します。 非推奨になりました。

## <a name="syntax"></a>構文

```
/GZ
```

## <a name="remarks"></a>解説

**/GZ** は、非最適化 ([/od (無効 (デバッグ)](od-disable-debug.md)) ビルドでのみ使用されます。

**/GZ** は Visual Studio 2005 以降では非推奨とされます。代わりに、 [/rtc (ランタイムエラーチェック)](rtc-run-time-error-checks.md) を使用してください。 非推奨のコンパイラオプションの一覧については、「[カテゴリ別に一覧表示さ](compiler-options-listed-by-category.md)れたコンパイラオプションの **非推奨のコンパイラオプション**」を参照してください。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. **[C/C++]** フォルダーをクリックします。

1. **[コマンド ライン]** プロパティ ページをクリックします。

1. [追加のオプション]  ボックスにコンパイラ オプションを入力します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>

## <a name="see-also"></a>関連項目

[MSVC コンパイラ オプション](compiler-options.md)<br/>
[MSVC Compiler Command-Line 構文](compiler-command-line-syntax.md)
