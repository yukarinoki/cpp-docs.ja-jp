---
description: '詳細情報:/Zc: throwingNew (operator new がスローされると仮定)'
title: '/Zc: throwingNew (new 演算子のスローの仮定)'
ms.date: 03/01/2018
f1_keywords:
- throwingNew
- /Zc:throwingNew
helpviewer_keywords:
- -Zc compiler options (C++)
- throwingNew
- Assume operator new Throws
- /Zc compiler options (C++)
- Zc compiler options (C++)
ms.assetid: 20ff0101-9677-4d83-8c7b-8ec9ca49f04f
ms.openlocfilehash: 83a78c62328853bdaf9515b55bef72503d166b58
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97271201"
---
# <a name="zcthrowingnew-assume-operator-new-throws"></a>/Zc: throwingNew (new 演算子のスローの仮定)

**/Zc: throwingNew** オプションを指定すると、コンパイラはの呼び出しを最適化して `operator new` 、null ポインターの戻り値のチェックをスキップします。 このオプションは、およびカスタムアロケーターのすべてのリンクされた実装が C++ 標準に準拠し、割り当てエラーが発生した場合にスローすることをコンパイラに指示し `operator new` ます。 既定では、Visual Studio では、コンパイラ pessimistically は、これらの呼び出しに対して null チェック (**/zc: throwingNew-**) を生成します。これは、ユーザーがをスローしない実装にリンク `operator new` したり、null ポインターを返すカスタムアロケータールーチンを記述したりできるためです。

## <a name="syntax"></a>構文

> **/Zc: throwingNew**[ **-** ]

## <a name="remarks"></a>解説

ISO C++ 98 以降、標準では、メモリ割り当てが失敗したときに既定の [演算子 new](../../standard-library/new-operators.md#op_new) がスローするように指定されてい `std::bad_alloc` ます。 Visual Studio 6.0 までの Visual C++ バージョンでは、割り当てエラー時に null ポインターが返されました。 Visual Studio 2002 以降では、 `operator new` 標準に準拠し、エラーが発生した場合にをスローします。 以前の割り当てスタイルを使用するコードをサポートするために、Visual Studio では、 `operator new` エラーが発生したときに null ポインターを返す nothrownew でのリンク可能実装を提供しています。 既定では、コンパイラは、これらの古いスタイルのアロケーターが障害発生時にすぐにクラッシュするのを防ぐために、防御的な null チェックも生成します。 **/Zc: throwingNew** オプションは、すべてのリンクされたメモリアロケーターが標準に準拠していると仮定して、これらの null チェックを省略するようにコンパイラに指示します。 これは `operator new` 、型の追加パラメーターを使用して宣言され、 `std::nothrow_t` 明示的な指定を持つ明示的な非スローオーバーロードには適用されません **`noexcept`** 。

概念的には、フリーストアにオブジェクトを作成するために、コンパイラはメモリを割り当て、そのコンストラクターを呼び出してメモリを初期化するコードを生成します。 MSVC コンパイラは、通常、このコードが非対応の非スローアロケーターにリンクされるかどうかを判断できないため、既定では、コンストラクターを呼び出す前にも null チェックが生成されます。 これにより、スローされない割り当てが失敗した場合に、コンストラクター呼び出しで null ポインターの逆参照が発生するのを防ぐことができます。 ほとんどの場合、これらのチェックは不要です。これは、既定のアロケーターによって null ポインターが返される代わりにスローされるため `operator new` です。 このチェックでは、残念ながら副作用もあります。 コードサイズが肥大化し、分岐予測をオーバーフローし、初期化されたオブジェクトからの devirtualization や const 伝達など、他の便利なコンパイラ最適化が妨げられています。 チェックは、 *nothrownew* にリンクするコード、またはカスタムの非準拠の実装を持つコードをサポートするためにのみ存在し `operator new` ます。 非準拠を使用しない場合は `operator new` 、 **/Zc: throwingNew** を使用してコードを最適化することをお勧めします。

**/Zc: throwingNew** オプションは、既定ではオフになっており、 [/permissive-](permissive-standards-conformance.md)オプションの影響を受けません。

リンク時のコード生成 (LTCG) を使用してコンパイルする場合は、 **/zc: throwingNew** を指定する必要はありません。 LTCG を使用してコードをコンパイルすると、コンパイラは、既定の準拠実装が使用されているかどうかを検出でき `operator new` ます。 その場合、コンパイラは null チェックを自動的に終了します。 リンカーは **/ThrowingNew** フラグを検索して、の実装が準拠しているかどうかを確認し `operator new` ます。 このフラグをリンカーに指定するには、カスタム演算子の新しい実装のソースにこのディレクティブを含めます。

```cpp
#pragma comment(linker, "/ThrowingNew")
```

Visual C++ の準拠に関する問題について詳しくは、「 [Nonstandard Behavior](../../cpp/nonstandard-behavior.md)」をご覧ください。

## <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. [ **構成** ] ドロップダウンメニューから、[ **すべての構成**] を選択します。

1. [**構成プロパティ**] [  >  **C/c + +**  >  **コマンドライン**] プロパティページを選択します。

1. **/Zc: throwingNew** または **/zc: throwingNew** が含まれるように "**追加オプション**" プロパティを変更し、[ **OK]** をクリックします。

## <a name="see-also"></a>関連項目

[MSVC コンパイラ オプション](compiler-options.md)<br/>
[MSVC Compiler Command-Line 構文](compiler-command-line-syntax.md)<br/>
[/Zc (準拠)](zc-conformance.md)<br/>
[noexcept (C++)](../../cpp/noexcept-cpp.md)<br/>
[例外の仕様 (スロー) (C++)](../../cpp/exception-specifications-throw-cpp.md)<br/>
[terminate (例外)](../../standard-library/exception-functions.md#terminate)<br/>
