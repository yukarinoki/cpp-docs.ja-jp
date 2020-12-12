---
description: '詳細情報:/Zc: sizedDealloc (グローバルサイズの割り当て解除関数の有効化)'
title: '/Zc: sizedDealloc (グローバルサイズ割り当て解除関数の有効化)'
ms.date: 03/06/2018
f1_keywords:
- sizedDealloc
- /Zc:sizedDealloc
helpviewer_keywords:
- -Zc compiler options (C++)
- sizedDealloc
- Enable Global Sized Deallocation Functions
- /Zc compiler options (C++)
- Zc compiler options (C++)
ms.assetid: 3a73ace0-4d36-420a-b699-0ca6fc0dd134
ms.openlocfilehash: 4e40355dc3c61f725ca9996dc4c91c0604866fe4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97269069"
---
# <a name="zcsizeddealloc-enable-global-sized-deallocation-functions"></a>/Zc: sizedDealloc (グローバルサイズ割り当て解除関数の有効化)

**/Zc: sizedDealloc** コンパイラオプションは、 `operator delete` `operator delete[]` `size_t` オブジェクトのサイズが使用可能な場合に型の2番目のパラメーターを持つグローバルまたは関数を優先的に呼び出すようにコンパイラに指示します。 これらの関数は、パラメーターを使用して `size_t` デアロケーターのパフォーマンスを最適化することができます。

## <a name="syntax"></a>構文

> **/Zc: sizedDealloc**[ **-** ]

## <a name="remarks"></a>解説

C++ 11 標準では、静的メンバー関数を定義 `operator delete` し、 `operator delete[]` 2 番目のパラメーターを受け取ることができ `size_t` ます。 通常、これらは、オブジェクトのより効率的なアロケーターと deallocators を実装するために、 [operator new](../../cpp/new-operator-cpp.md) 関数と組み合わせて使用されます。 ただし、C++ 11 では、グローバルスコープで同じ割り当て解除関数のセットが定義されていませんでした。 C++ 11 では、型の2番目のパラメーターを持つグローバルな割り当て解除関数 `size_t` は、配置削除関数と見なされます。 これらは、サイズ引数を渡すことによって明示的に呼び出す必要があります。

C++ 14 標準では、コンパイラの動作が変更されます。 グローバルなを定義し、 `operator delete` `operator delete[]` 型の2番目のパラメーターを受け取ると `size_t` 、コンパイラは、メンバースコープのバージョンが呼び出されず、オブジェクトのサイズが使用可能になったときに、これらの関数を呼び出すことを推奨します。 コンパイラは、サイズ引数を暗黙的に渡します。 1つの引数のバージョンは、割り当てが解除されているオブジェクトのサイズをコンパイラが判断できない場合に呼び出されます。 それ以外の場合は、通常、を呼び出すために使用する解放関数のバージョンを選択するための規則が適用されます。 グローバル関数の呼び出しは、スコープ解決演算子 ( `::` ) を解放関数呼び出しに付加することによって明示的に指定できます。

既定では、Visual Studio 2015 以降の Visual C++ は、この C++ 14 標準動作を実装します。 これを明示的に指定するには、 **/zc: sizedDealloc** コンパイラオプションを設定します。 これは、互換性に影響する可能性のある変更を表します。 以前の動作を保持するには、 **/zc: sizedDealloc-** オプションを使用します。たとえば、コードで型の2番目のパラメーターを使用する配置削除演算子を定義する場合など `size_t` です。 型の2番目のパラメーターを持つグローバル解放関数の既定の Visual Studio ライブラリ実装では、 `size_t` 単一のパラメーターバージョンが呼び出されます。 コードで単一パラメーターのグローバル演算子 delete と operator delete [] のみを指定した場合、グローバルサイズ解放関数の既定のライブラリ実装では、グローバル関数が呼び出されます。

**/Zc: sizedDealloc** コンパイラオプションは、既定でオンになっています。 [/Permissive-](permissive-standards-conformance.md)オプションは、 **/Zc: sizedDealloc** には影響しません。

Visual C++ の準拠に関する問題について詳しくは、「 [Nonstandard Behavior](../../cpp/nonstandard-behavior.md)」をご覧ください。

## <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. [ **構成** ] ドロップダウンメニューから、[ **すべての構成**] を選択します。

1. [**構成プロパティ**] [  >  **C/c + +**  >  **コマンドライン**] プロパティページを選択します。

1. **/Zc: sizeddealloc** または **/Zc: sizeddealloc** が含まれるように "**追加オプション**" プロパティを変更し、[ **OK]** を選択します。

## <a name="see-also"></a>関連項目

[MSVC コンパイラ オプション](compiler-options.md)<br/>
[MSVC Compiler Command-Line 構文](compiler-command-line-syntax.md)<br/>
[/Zc (準拠)](zc-conformance.md)<br/>
