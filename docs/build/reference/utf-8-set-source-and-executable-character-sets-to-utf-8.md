---
description: 詳細については、次を参照してください。 `/utf-8` (ソースと実行可能文字セットをに設定します UTF-8 )
title: /8 (ソースと実行可能文字セットをに設定します UTF-8 )
ms.date: 04/26/2020
f1_keywords:
- /utf-8
helpviewer_keywords:
- /utf-8 compiler option
ms.assetid: f0e1f3cb-6cae-46eb-9483-04ed13d9b504
no-loc:
- UTF
- UTF-8
- UTF-16
ms.openlocfilehash: f9d58315a55d0e390ec07a1907af0befda127c54
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97176406"
---
# <a name="utf-8-set-source-and-executable-character-sets-to-no-locutf-8"></a>`/utf-8` (ソースと実行可能文字セットをに設定します UTF-8 )

ソース文字セットと実行文字セットの両方をとして指定し UTF-8 ます。

## <a name="syntax"></a>構文

> **`/utf-8`**

## <a name="remarks"></a>解説

オプションを使用すると、を使用してエンコードされた **`/utf-8`** ソースと実行の両方の文字セットを指定でき UTF-8 ます。 これ **`/source-charset:utf-8 /execution-charset:utf-8`** は、コマンドラインでを指定することと同じです。 これらのオプションのいずれでも、既定でオプションが有効になり **`/validate-charset`** ます。 サポートされているコードページ識別子と文字セット名の一覧については、「 [コードページ識別子](/windows/win32/Intl/code-page-identifiers)」を参照してください。

既定では、Visual Studio は、ソースファイルがエンコードされた Unicode 形式 (またはなど) であるかどうかを判断するために、バイト順マークを検出し UTF-16 UTF-8 ます。 バイト順マークが見つからない場合、またはオプションを使用してコードページを指定していない限り、ソースファイルは現在のユーザーコードページを使用してエンコードされていると見なされ **`/utf-8`** **`/source-charset`** ます。 Visual Studio では、いくつかの文字エンコーディングのいずれかを使用して C++ ソースコードを保存できます。 ソース文字セットと実行文字セットの詳細については、言語ドキュメントの「 [文字セット](../../cpp/character-sets.md) 」を参照してください。

## <a name="set-the-option-in-visual-studio-or-programmatically"></a>Visual Studio またはプログラムでオプションを設定する

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳しくは、「[Visual Studio で C++ コンパイラとビルド プロパティを設定する](../working-with-project-properties.md)」をご覧ください。

1. [**構成プロパティ**] [  >  **C/c + +**  >  **コマンドライン**] プロパティページを選択します。

1. [ **追加オプション**] で、オプションを追加し **`/utf-8`** て、優先するエンコードを指定します。

1. **[OK]** を選択して変更を保存します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>

## <a name="see-also"></a>関連項目

[MSVC コンパイラ オプション](compiler-options.md)<br/>
[MSVC Compiler Command-Line 構文](compiler-command-line-syntax.md)<br/>
[/文字セット (実行文字セットの設定)](execution-charset-set-execution-character-set.md)<br/>
[/source-charset (ソース文字セットの設定)](source-charset-set-source-character-set.md)<br/>
[/validate-charset (互換性のある文字の検証)](validate-charset-validate-for-compatible-characters.md)
