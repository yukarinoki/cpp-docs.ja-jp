---
title: /utf-8 (ソースの設定と実行可能ファイルの文字セットを utf-8)
ms.date: 11/04/2016
f1_keywords:
- /utf-8
helpviewer_keywords:
- /utf-8 compiler option
ms.assetid: f0e1f3cb-6cae-46eb-9483-04ed13d9b504
ms.openlocfilehash: cb683e9baddea455b72bb823676ba1e6adabfd4c
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57421559"
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

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[プロジェクト プロパティの操作](../../ide/working-with-project-properties.md)」を参照してください。

1. 展開、**構成プロパティ**、 **C/C++**、**コマンドライン**フォルダー。

1. **追加オプション**、追加、 **/utf-8**使用するエンコーディングを指定するオプション。

1. **OK** を選択して変更を保存してください。

## <a name="see-also"></a>関連項目

[コンパイラ オプション](../../build/reference/compiler-options.md)<br/>
[コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)<br/>
[/execution-charset (実行文字セット)](../../build/reference/execution-charset-set-execution-character-set.md)<br/>
[/source-charset (ソース文字セットの設定)](../../build/reference/source-charset-set-source-character-set.md)<br/>
[/validate-charset (互換性のある文字の検証)](../../build/reference/validate-charset-validate-for-compatible-characters.md)
