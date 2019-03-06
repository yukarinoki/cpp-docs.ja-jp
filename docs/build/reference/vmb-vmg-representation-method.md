---
title: /vmb、-vmg (表現方法)
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
ms.openlocfilehash: 9bb355635181c3db53e1171aaf18cd665e6504ae
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57426356"
---
# <a name="vmb-vmg-representation-method"></a>/vmb、/vmg (処理形式)

コンパイラはクラスのメンバーを指すポインターを使用するメソッドを選択します。

使用 **/vmb 処理形式**クラスのメンバーへのポインターを宣言する前に常にクラスを定義するかどうか。

使用 **/vmg**クラスを定義する前に、クラスのメンバーへのポインターを宣言します。 この必要性は、相互に参照する 2 つの異なるクラスにメンバーを定義する場合に発生します。 このような相互に参照元のクラスでは、その前に 1 つのクラスを参照する必要があります。

## <a name="syntax"></a>構文

```
/vmb
/vmg
```

## <a name="remarks"></a>Remarks

使用することも[pointers_to_members](../../preprocessor/pointers-to-members.md)または[継承キーワード](../../cpp/inheritance-keywords.md)をコードにポインター表現を指定します。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境において、このコンパイラ オプションを設定する方法

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[プロジェクトのプロパティの操作](../../ide/working-with-project-properties.md)」を参照してください。

1. **[C/C++]** フォルダーをクリックします。

1. **[コマンド ライン]** プロパティ ページをクリックします。

1. **[追加のオプション]** ボックスにコンパイラ オプションを入力します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>

## <a name="see-also"></a>関連項目

[コンパイラ オプション](../../build/reference/compiler-options.md)<br/>
[コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)
