---
title: -vmb、-vmg (表現方法) |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /vmb
- /vmg
dev_langs:
- C++
helpviewer_keywords:
- vmb compiler option [C++]
- -vmg compiler option [C++]
- vmg compiler option [C++]
- -vmb compiler option [C++]
- /vmb compiler option [C++]
- representation method compiler options [C++]
- /vmg compiler option [C++]
ms.assetid: ecdb391c-7dab-40b1-916b-673d10889fd4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a95081dfb417711002039727b04d1916c5fe0a14
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45720578"
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