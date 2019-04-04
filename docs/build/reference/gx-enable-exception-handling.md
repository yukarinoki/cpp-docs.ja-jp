---
title: /GX (例外処理の有効化)
ms.date: 11/04/2016
f1_keywords:
- /gx
helpviewer_keywords:
- exception handling, enabling
- /GX compiler option [C++]
- -GX compiler option [C++]
- cl.exe compiler, exception handling
- enable exception handling compiler option [C++]
- GX compiler option [C++]
ms.assetid: 933b43ba-de77-4ff8-a48b-7074de90bc1c
ms.openlocfilehash: 43be8f6d0f080f0d85568ce5b089751fc68f0e8e
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2019
ms.locfileid: "57815464"
---
# <a name="gx-enable-exception-handling"></a>/GX (例外処理の有効化)

非推奨。 使用して宣言された関数であるという前提を使用して同期例外処理できるように`extern "C"`例外はスローされません。

## <a name="syntax"></a>構文

```
/GX
```

## <a name="remarks"></a>Remarks

**/GX**は非推奨とされます。 相当するものを使用して、 [/EHsc](eh-exception-handling-model.md)オプションを使用します。 非推奨のコンパイラ オプションの一覧は、、**非推奨とされた削除済みのコンパイラ オプション**セクション[Compiler Options Listed by Category](compiler-options-listed-by-category.md)を参照してください。

既定では、 **/EHsc**と等価の **/GX**、Visual Studio 開発環境を使用してコンパイルする場合は適用されます。 コマンド ライン ツールを使用すると例外処理を指定しません。 これは、相当の**では/GX-** します。

詳細については、[C++ 例外処理](../../cpp/cpp-exception-handling.md)を参照してください。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境において、このコンパイラ オプションを設定する方法

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での設定の C++ コンパイラとビルド プロパティ](../working-with-project-properties.md)を参照してください。

1. ナビゲーション ウィンドウで、**構成プロパティ**、 **C/C++**、**コマンドライン**します。

1. **[追加のオプション]** ボックスにコンパイラ オプションを入力します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>

## <a name="see-also"></a>関連項目

[MSVC コンパイラ オプション](compiler-options.md)<br/>
[MSVC コンパイラ コマンドラインの構文](compiler-command-line-syntax.md)<br/>
[/EH (例外処理モデル)](eh-exception-handling-model.md)
