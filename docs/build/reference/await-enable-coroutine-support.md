---
title: /await (コルーチン サポートを有効にする)
ms.date: 08/15/2017
f1_keywords:
- /await
- -await
helpviewer_keywords:
- /await enable coroutine support [C++]
- -await enable coroutine support [C++]
- await enable coroutine support [C++]
ms.assetid: 302c8e69-09b6-4c58-bcdd-0a6a8713a8df
ms.openlocfilehash: e3f7359b60e1ba22c2646cecfd35b827919ae033
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50590434"
---
# <a name="await-enable-coroutine-support"></a>/await (コルーチン サポートを有効にする)

使用して、 **/await**コルーチンのコンパイラ サポートを有効にするコンパイラ オプション。

## <a name="syntax"></a>構文

> /await と一緒に使う

## <a name="remarks"></a>Remarks

**/Await**コンパイラ オプションにより、C++ コルーチンとキーワードのコンパイラ サポート**co_await**、 **co_yield**、および**co_return**. このオプションの既定値はオフです。 Visual Studio でのコルーチンのサポートについては、次を参照してください。、 [Visual Studio チームのブログ](https://blogs.msdn.microsoft.com/vcblog/category/coroutine/)します。 コルーチンの標準提案書の詳細については、次を参照してください。 [N4628 ワーキング ドラフト、コルーチンの C++ 拡張機能の技術仕様](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/n4628.pdf)します。

**/Await**オプションは、Visual Studio 2015 以降を使用できます。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境において、このコンパイラ オプションを設定する方法

1. プロジェクトの開く**プロパティ ページ** ダイアログ ボックス。

1. **構成プロパティ**、展開、 **C/C++** フォルダーを選択し、**コマンド ライン**プロパティ ページ。

1. 入力、 **/await**コンパイラ オプションで、**追加オプション**ボックス。 選択**OK**または**適用**変更を保存します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>

## <a name="see-also"></a>関連項目

[コンパイラ オプション](../../build/reference/compiler-options.md)<br/>
[コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)
