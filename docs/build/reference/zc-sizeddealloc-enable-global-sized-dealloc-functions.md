---
title: /Zc:sizedDealloc (有効にするグローバル サイズ割り当て解除関数) |Microsoft ドキュメント
ms.custom: ''
ms.date: 03/06/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- sizedDealloc
- /Zc:sizedDealloc
dev_langs:
- C++
helpviewer_keywords:
- -Zc compiler options (C++)
- sizedDealloc
- Enable Global Sized Deallocation Functions
- /Zc compiler options (C++)
- Zc compiler options (C++)
ms.assetid: 3a73ace0-4d36-420a-b699-0ca6fc0dd134
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0a912b87240ad37e29cade077b7a93aa1e7886a6
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="zcsizeddealloc-enable-global-sized-deallocation-functions"></a>/Zc:sizedDealloc (有効にするグローバル サイズ割り当て解除関数)

**/Zc:sizedDealloc**コンパイラ オプションを優先的にグローバルで呼び出すコンパイラに指示`operator delete`または`operator delete[]`を型の 2 番目のパラメーターを持つ関数`size_t`オブジェクトのサイズが使用可能な場合です。 これらの関数は使用して、`size_t`デアロケーター パフォーマンスを最適化するパラメーターです。

## <a name="syntax"></a>構文

> **/Zc:sizedDealloc**[**-**]

## <a name="remarks"></a>コメント

C++ 11 標準では、静的メンバー関数を定義することがあります`operator delete`と`operator delete[]`をすぐに、`size_t`パラメーター。 通常これらと組み合わせて使用されます[new 演算子](../../cpp/new-operator-cpp.md)効率のアロケーターとオブジェクトのデアロケーターを実装する関数。 ただし、c++ 11 では、グローバル スコープで解放関数の同等のセットは定義しませんでした。 C++ 11、グローバルの割り当て解除を持つ関数型の 2 番目のパラメーターで`size_t`配置 delete 関数と見なされます。 必要があります明示的に呼び出すことが、サイズ引数を渡すことによってです。

標準の c++ 14 では、コンパイラの動作を変更します。 グローバル定義するときに`operator delete`と`operator delete[]`型の 2 番目のパラメーターを受け取る`size_t`コンパイラではメンバーのスコープのバージョンが呼び出されないと、オブジェクトのサイズが使用可能なときに、これらの関数を呼び出すが優先されます。 コンパイラは、暗黙的にサイズの引数を渡します。 1 つの引数のバージョンは、コンパイラは、割り当てが解除されて、オブジェクトのサイズを判断できない場合と呼ばれます。 それ以外の場合、deallocation 関数を呼び出すためのバージョンを選択するため、通常のルールが引き続き適用されます。 スコープ解決演算子を付加することによって、グローバル関数への呼び出しを明示的に指定することがあります (`::`)、deallocation 関数の呼び出しにします。

既定では、Visual C の Visual Studio 2015 以降では、この c++ 14 標準動作を実装します。 設定してこの明示的に指定することがあります、 **/Zc:sizedDealloc**コンパイラ オプション。 これを表します。 可能性のある重大な変更です。 使用して、 **/Zc:sizedDealloc-** コードは、型の 2 番目のパラメーターを使用する配置 delete 演算子を定義する場合など、従来の動作を保持するオプション`size_t`です。 型の 2 番目のパラメーターを持つグローバル deallocation 関数の既定の Visual Studio ライブラリ実装`size_t`パラメーターを 1 つのバージョンを呼び出します。 コードの提供のみ単一パラメーター グローバル delete 演算子と演算子 delete、グローバル サイズの割り当て解除機能の既定のライブラリの実装は、グローバル関数を呼び出します。

**/Zc:sizedDealloc**コンパイラ オプションは既定でオンです。 [寛容/-](permissive-standards-conformance.md)オプションには影響しません **/Zc:sizedDealloc**です。

Visual C++ の準拠に関する問題について詳しくは、「 [Nonstandard Behavior](../../cpp/nonstandard-behavior.md)」をご覧ください。

## <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。

1. **構成**ドロップダウン メニューで、選択**すべて構成**です。

1. 選択、**構成プロパティ** > **C/C++** > **コマンドライン**プロパティ ページ。

1. 変更、**追加オプション**含めるプロパティを **/Zc:sizedDealloc**または **/Zc:sizedDealloc-** を選択し**OK**です。

## <a name="see-also"></a>関連項目

[コンパイラ オプション](../../build/reference/compiler-options.md)<br/>
[コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)<br/>
[/Zc (準拠)](../../build/reference/zc-conformance.md)<br/>
