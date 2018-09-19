---
title: -await (コルーチン サポートを有効にする) |Microsoft Docs
ms.custom: ''
ms.date: 08/15/2017
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /await
- -await
dev_langs:
- C++
helpviewer_keywords:
- /await enable coroutine support [C++]
- -await enable coroutine support [C++]
- await enable coroutine support [C++]
ms.assetid: 302c8e69-09b6-4c58-bcdd-0a6a8713a8df
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5da401f940a39c135ba0b64571b6330a42fed796
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45725518"
---
# <a name="await-enable-coroutine-support"></a>/await (コルーチン サポートを有効にする)

使用して、 **/await**コルーチンのコンパイラ サポートを有効にするコンパイラ オプション。

## <a name="syntax"></a>構文

> /await と一緒に使う

## <a name="remarks"></a>Remarks

**/Await**コンパイラ オプションにより、C++ コルーチンとキーワードのコンパイラ サポート**co_await**、 **co_yield**、および**co_return**. このオプションの既定値はオフです。 Visual Studio でのコルーチンのサポートについては、次を参照してください。、 [Visual Studio チームのブログ](https://blogs.msdn.microsoft.com/vcblog/category/coroutine/)します。 コルーチンの標準提案書の詳細については、次を参照してください。 [N4628 ワーキング ドラフト、コルーチンの C++ 拡張機能の技術仕様](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/n4628.pdf)します。

**/Await**オプションは、Visual Studio 2015 以降を使用できます。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの開く**プロパティ ページ** ダイアログ ボックス。

2. **構成プロパティ**、展開、 **C/C++** フォルダーを選択し、**コマンド ライン**プロパティ ページ。

3. 入力、 **/await**コンパイラ オプションで、**追加オプション**ボックス。 選択**OK**または**適用**変更を保存します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>

## <a name="see-also"></a>関連項目

[コンパイラ オプション](../../build/reference/compiler-options.md)<br/>
[コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)