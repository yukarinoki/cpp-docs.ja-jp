---
description: 詳細については、次を参照してください:/vmb,/vmg (表現メソッド)
title: /vmb、/vmg (処理形式)
ms.date: 11/04/2016
f1_keywords:
- /vmb
- /vmg
helpviewer_keywords:
- vmb compiler option [C++]
- -vmg compiler option [C++]
- vmg compiler option [C++]
- -vmb compiler option [C++]
- /vmb compiler option [C++]
- representation method compiler options [C++]
- /vmg compiler option [C++]
ms.assetid: ecdb391c-7dab-40b1-916b-673d10889fd4
ms.openlocfilehash: 19d183ef8d1dd152043d7249d907c9d5b48de230
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97254285"
---
# <a name="vmb-vmg-representation-method"></a>/vmb、/vmg (処理形式)

クラスメンバーへのポインターを表すためにコンパイラが使用するメソッドを選択します。

クラスのメンバーへのポインターを宣言する前に、常にクラスを定義する場合は、 **/vmb** を使用します。

クラスを定義する前に、 **/vmg** を使用して、クラスのメンバーへのポインターを宣言します。 このニーズは、互いを参照する2つの異なるクラスでメンバーを定義した場合に発生する可能性があります。 このような相互参照を行うクラスでは、定義する前に1つのクラスを参照する必要があります。

## <a name="syntax"></a>構文

```
/vmb
/vmg
```

## <a name="remarks"></a>解説

また、コード内で [pointers_to_members](../../preprocessor/pointers-to-members.md) または [継承キーワード](../../cpp/inheritance-keywords.md) を使用して、ポインター表現を指定することもできます。

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
