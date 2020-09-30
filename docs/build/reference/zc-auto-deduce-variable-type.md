---
title: /Zc:auto (変数の型の推測)
ms.date: 02/28/2018
f1_keywords:
- /Zc:auto
helpviewer_keywords:
- -Zc compiler options (C++)
- Deduce variable type (C++)
- /Zc compiler options (C++)
- Zc compiler options (C++)
ms.assetid: 5f5bc102-44c3-4688-bbe1-080594dcee5c
ms.openlocfilehash: 6bb1c8f2b14c483cbd46ecb6534a33db020e23e0
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/29/2020
ms.locfileid: "91502831"
---
# <a name="zcauto-deduce-variable-type"></a>`/Zc:auto` (変数の型の推測)

**`/Zc:auto`** コンパイラオプションは、 [ `auto` キーワード](../../cpp/auto-cpp.md)を使用して変数を宣言する方法をコンパイラに指示します。 既定のオプションであるを指定した場合、 **`/Zc:auto`** コンパイラは初期化式から宣言された変数の型を推測します。 を指定すると **`/Zc:auto-`** 、コンパイラは変数を自動ストレージクラスに割り当てます。

## <a name="syntax"></a>構文

> **`/Zc:auto`**[**`-`**]

## <a name="remarks"></a>注釈

C++ 標準では、キーワードの元の意味と改訂された意味が定義されて **`auto`** います。 Visual Studio 2010 より前では、キーワードは自動ストレージクラスの変数を宣言しています。つまり、ローカルの有効期間を持つ変数です。 Visual Studio 2010 以降では、キーワードは、宣言の初期化式から変数の型を推測します。 **`/Zc:auto`** コンパイラがキーワードの改訂された意味を使用するようにコンパイラに指示するには、コンパイラオプションを使用し **`auto`** ます。 **`/Zc:auto`** 既定では、このオプションはオンになっています。 オプションでは、 [`/permissive-`](permissive-standards-conformance.md) の既定の設定は変更されません **`/Zc:auto`** 。

キーワードの使用が **`auto`** 現在のコンパイラオプションと矛盾している場合、コンパイラは適切な診断メッセージを発行し **`/Zc:auto`** ます。 詳細については、「 [ `auto` キーワード](../../cpp/auto-cpp.md)」を参照してください。 Visual C++ の準拠に関する問題の詳細については、「 [非標準動作](../../cpp/nonstandard-behavior.md)」を参照してください。

### <a name="to-set-this-compiler-option-in-visual-studio"></a>このコンパイラ オプションを Visual Studio で使用するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. [**構成プロパティ**] [  >  **C/c + +**  >  **コマンドライン**] プロパティページを選択します。

1. **`/Zc:auto`** **`/Zc:auto-`** [**追加オプション:** ] ペインにまたはを追加します。

## <a name="see-also"></a>関連項目

[`/Zc` 互換性](zc-conformance.md)<br/>
[`auto` キーワード](../../cpp/auto-cpp.md)
