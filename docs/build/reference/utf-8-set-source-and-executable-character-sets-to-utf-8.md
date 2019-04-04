---
title: /utf-8 (ソースの設定と実行可能ファイルの文字セットを utf-8)
ms.date: 11/04/2016
f1_keywords:
- /utf-8
helpviewer_keywords:
- /utf-8 compiler option
ms.assetid: f0e1f3cb-6cae-46eb-9483-04ed13d9b504
ms.openlocfilehash: 5ac15c63041e76b8bb0d292868bb982c21866078
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2019
ms.locfileid: "57812292"
---
# <a name="utf-8-set-source-and-executable-character-sets-to-utf-8"></a>/utf-8 (ソースの設定と実行可能ファイルの文字セットを utf-8)

ソース文字セットし、実行文字セットを utf-8 としての両方を指定します。

## <a name="syntax"></a>構文

```
/utf-8
```

## <a name="remarks"></a>Remarks

使用することができます、 **/utf-8**オプション、ソースと実行文字セットと utf-8 を使用してエンコードを指定します。 指定することと同じである **/source -charset:utf-8/execution-charset:utf-8**コマンド行にします。 これらのいずれかのオプションも有効、 **/validate-charset**既定ではオプションです。 一覧には、コード ページ識別子がサポートされている文字セットの名前を参照してください。[コード ページ識別子](/windows/desktop/Intl/code-page-identifiers)します。

既定では、Visual Studio は、utf-8 または utf-16、たとえば、ソース ファイルが、エンコードされた Unicode 形式であるか判断のバイト順マークを検出します。 バイト順マークが見つからない場合は、ソース ファイルを使ってエンコードされる現在のユーザーのコード ページを使用してコード ページを指定していない限り想定しています。 **/utf-8**または **/source-charset**オプション。 Visual Studio では、いくつかの文字エン コードのいずれかを使用して、C++ ソース コードを保存できます。 ソースと実行文字セットの詳細については、次を参照してください。[文字セット](../../cpp/character-sets.md)言語ドキュメント。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境において、このコンパイラ オプションを設定する方法

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での設定の C++ コンパイラとビルド プロパティ](../working-with-project-properties.md)を参照してください。

1. 展開、**構成プロパティ**、 **C/C++**、**コマンドライン**フォルダー。

1. **追加オプション**、追加、 **/utf-8**使用するエンコーディングを指定するオプション。

1. **OK** を選択して変更を保存してください。

## <a name="see-also"></a>関連項目

[MSVC コンパイラ オプション](compiler-options.md)<br/>
[MSVC コンパイラ コマンドラインの構文](compiler-command-line-syntax.md)<br/>
[/execution-charset (実行文字セット)](execution-charset-set-execution-character-set.md)<br/>
[/source-charset (ソース文字セットの設定)](source-charset-set-source-character-set.md)<br/>
[/validate-charset (互換性のある文字の検証)](validate-charset-validate-for-compatible-characters.md)
