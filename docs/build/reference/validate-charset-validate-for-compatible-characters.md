---
description: 詳細については、「文字セット (互換性のある文字の検証)」を参照してください。
title: /validate-charset (互換性のある文字の検証)
ms.date: 02/06/2019
f1_keywords:
- /validate-charset
- validate-charset
helpviewer_keywords:
- /validate-charset compiler option
ms.assetid: 50360fd0-4d32-4a4f-95d0-53d38c12ad4c
ms.openlocfilehash: bda69c59fc89aae5028543ba579ee1e0b70f67e7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97250401"
---
# <a name="validate-charset-validate-for-compatible-characters"></a>/validate-charset (互換性のある文字の検証)

ソースファイルのテキストに UTF-8 として表現できる文字のみが含まれていることを検証します。

## <a name="syntax"></a>構文

```
/validate-charset[-]
```

## <a name="remarks"></a>解説

**/Validatecharset** オプションを使用すると、ソース文字セットと実行文字セットの両方で表現できる文字のみがソースコードに含まれていることを検証できます。 このチェックは、 **/source-charset**、または **文字セット**、または 3 **つ** のコンパイラオプションを指定すると、自動的に有効になります。 このチェックを明示的に無効にする **には、オプションを** 指定します。

既定では、Visual Studio は、ソースファイルがエンコードされた Unicode 形式であるかどうかを判断するためにバイト順マークを検出します (UTF-16 や UTF-8 など)。 バイト順マークが見つからない場合は、 **/source-charset** オプション **を使用し** てコードページを指定しない限り、ソースファイルが現在のユーザーコードページを使用してエンコードされているものと見なされます。 Visual Studio では、いくつかの文字エンコーディングのいずれかを使用して C++ ソースコードを保存できます。 ソース文字セットと実行文字セットの詳細については、言語ドキュメントの「 [文字セット](../../cpp/character-sets.md) 」を参照してください。 サポートされているコードページ識別子と文字セット名の一覧については、「 [コードページ識別子](/windows/win32/Intl/code-page-identifiers)」を参照してください。

Visual Studio では、ソース文字セットと実行文字セットの間の変換中に、内部文字エンコーディングとして UTF-8 が使用されます。 ソースファイル内の文字を実行文字セットで表すことができない場合、UTF-8 変換は疑問符 '? ' 文字に置き換えられます。 この **オプションを** 指定すると、コンパイル時に警告が報告されます。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳しくは、「[Visual Studio で C++ コンパイラとビルド プロパティを設定する](../working-with-project-properties.md)」をご覧ください。

1. [ **構成プロパティ**]、[ **c/c + +**]、[ **コマンドライン** フォルダー] の順に展開します。

1. [ **追加オプション**] で、[ **文字セット** ] オプションを追加し、任意のエンコードを指定します。

1. **[OK]** を選択して変更を保存します。

## <a name="see-also"></a>関連項目

[MSVC コンパイラ オプション](compiler-options.md)<br/>
[MSVC Compiler Command-Line 構文](compiler-command-line-syntax.md)<br/>
[/文字セット (実行文字セットの設定)](execution-charset-set-execution-character-set.md)<br/>
[/source-charset (ソース文字セットの設定)](source-charset-set-source-character-set.md)<br/>
[/8 (ソースと実行可能文字セットを UTF-8 に設定する)](utf-8-set-source-and-executable-character-sets-to-utf-8.md)
