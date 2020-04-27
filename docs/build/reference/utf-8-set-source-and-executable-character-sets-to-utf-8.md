---
title: /8 (ソースと実行可能文字セットをにUTF-8設定します)
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
ms.openlocfilehash: c98a30b0ec4b36b8bd87fb0956d9382751975cfd
ms.sourcegitcommit: 2bc15c5b36372ab01fa21e9bcf718fa22705814f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2020
ms.locfileid: "82168866"
---
# <a name="utf-8-set-source-and-executable-character-sets-to-opno-locutf-8"></a>`/utf-8`(ソースと実行可能文字セットをUTF-8に設定します)

ソース文字セットと実行文字セットの両方をとしUTF-8て指定します。

## <a name="syntax"></a>構文

> **`/utf-8`**

## <a name="remarks"></a>解説

**`/utf-8`** オプションを使用すると、を使用UTF-8してエンコードされたソースと実行の両方の文字セットを指定できます。 これは、コマンドライン**`/source-charset:utf-8 /execution-charset:utf-8`** でを指定することと同じです。 これらのオプションのいずれでも**`/validate-charset`** 、既定でオプションが有効になります。 サポートされているコードページ識別子と文字セット名の一覧については、「[コードページ識別子](/windows/win32/Intl/code-page-identifiers)」を参照してください。

既定でUTF-16は、Visual Studio は、ソースファイルがエンコードされた Unicode 形式 (またはUTF-8など) であるかどうかを判断するために、バイト順マークを検出します。 バイト順マークが見つからない場合、または**`/utf-8`** **`/source-charset`** オプションを使用してコードページを指定していない限り、ソースファイルは現在のユーザーコードページを使用してエンコードされていると見なされます。 Visual Studio では、いくつかの文字エンコーディングのいずれかを使用して C++ ソースコードを保存できます。 ソース文字セットと実行文字セットの詳細については、言語ドキュメントの「[文字セット](../../cpp/character-sets.md)」を参照してください。

## <a name="set-the-option-in-visual-studio-or-programmatically"></a>Visual Studio またはプログラムでオプションを設定する

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳しくは、「[Visual Studio で C++ コンパイラとビルド プロパティを設定する](../working-with-project-properties.md)」をご覧ください。

1. [**構成プロパティ** > ] [**C/c + +** > **コマンドライン**] プロパティページを選択します。

1. [**追加オプション**] で、 **`/utf-8`** オプションを追加して、優先するエンコードを指定します。

1. **[OK]** を選択して変更を保存します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 「 <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A> 」を参照してください。

## <a name="see-also"></a>関連項目

[MSVC コンパイラ オプション](compiler-options.md)<br/>
[MSVC コンパイラ コマンド ラインの構文](compiler-command-line-syntax.md)<br/>
[/文字セット (実行文字セットの設定)](execution-charset-set-execution-character-set.md)<br/>
[/source-charset (ソース文字セットの設定)](source-charset-set-source-character-set.md)<br/>
[/validate-charset (互換性のある文字の検証)](validate-charset-validate-for-compatible-characters.md)
