---
title: -J (既定の char 型の unsigned) |マイクロソフトのドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLCompilerTool.DefaultCharIsUnsigned
- VC.Project.VCCLWCECompilerTool.DefaultCharIsUnsigned
- /j
dev_langs:
- C++
helpviewer_keywords:
- defaults, char type
- char data type
- -J compiler option [C++]
- /J compiler option [C++]
- J compiler option [C++]
- default char type is unsigned
ms.assetid: 50973667-6638-491e-9c41-bff73acae19f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 400985751d9ceebf7cc2c5f632cb33c5ba847bfe
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45714286"
---
# <a name="j-default-char-type-is-unsigned"></a>/J (既定の char 型の unsigned への変更)

既定値が変更`char`から入力`signed char`に`unsigned char`、および`char`型ゼロ拡張は、上位変換するときに、`int`型。

## <a name="syntax"></a>構文

```
/J
```

## <a name="remarks"></a>Remarks

場合、`char`として値を明示的に宣言`signed`、 **/J**オプションには影響しません、および値が符号拡張され、上位変換するときに、`int`型。

**/J**オプション定義`_CHAR_UNSIGNED`で使用される`#ifndef`で既定値の範囲を定義しており、LIMITS.h ファイル`char`型。

ANSI C および C++ での特定の実装が必要ありません、`char`型。 このオプションは、文字データ、最終的に英語以外の言語に翻訳されますを使用している場合に便利です。

> [!NOTE]
>  ATL と MFC でこのコンパイラ オプションを使用する場合は、エラーを生成する可能性があります。 定義することによってこのエラーを無効にすることが`_ATL_ALLOW_CHAR_UNSIGNED`、この回避策はサポートされていないとが常に機能しません。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. **ソリューション エクスプローラー**で、プロジェクトのショートカット メニューを開き、 **[プロパティ]** をクリックします。

1. プロジェクトで**プロパティ ページ**] ダイアログ ボックスで、下の左ペインで**構成プロパティ**、展開**C/C++** し、[**コマンドライン**.

1. **追加オプション**ウィンドウで、指定、 **/J**コンパイラ オプション。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.DefaultCharIsUnsigned%2A>

## <a name="see-also"></a>関連項目

[コンパイラ オプション](../../build/reference/compiler-options.md)<br/>
[コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)<br/>
[プロジェクトのプロパティの操作](../../ide/working-with-project-properties.md)