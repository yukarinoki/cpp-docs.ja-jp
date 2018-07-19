---
title: /Zc:throwingNew (想定演算子の新しいスロー) |Microsoft ドキュメント
ms.custom: ''
ms.date: 03/01/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- throwingNew
- /Zc:throwingNew
dev_langs:
- C++
helpviewer_keywords:
- -Zc compiler options (C++)
- throwingNew
- Assume operator new Throws
- /Zc compiler options (C++)
- Zc compiler options (C++)
ms.assetid: 20ff0101-9677-4d83-8c7b-8ec9ca49f04f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f446e5c71e88be86c31e5a83ca7d23f611683af4
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32383463"
---
# <a name="zcthrowingnew-assume-operator-new-throws"></a>/Zc:throwingNew (想定演算子新しいがスローされます)

ときに、 **/Zc:throwingNew**オプションを指定すると、コンパイラでの呼び出しの最適化`operator new`戻り値の null ポインターのチェックをスキップします。 このオプションにより、すべての実装がリンクされていることを想定するコンパイラ`operator new`とカスタム アロケーターは、C++ 標準に準拠しているし、割り当ての失敗で例外がスローされます。 既定では Visual Studio で、排他生成 null チェック (**/Zc:throwingNew-**) の例外をスローしない実装を持つユーザーがリンクできるため、これら呼び出しに対する`operator new`カスタム アロケーター ルーチンを記述またはnull のポインターを返すこと。

## <a name="syntax"></a>構文

> **/Zc:throwingNew**[**-**]

## <a name="remarks"></a>コメント

ISO c++ 98 以降、標準が指定される既定値[new 演算子](../../standard-library/new-operators.md#op_new)スロー`std::bad_alloc`メモリの割り当てに失敗するとします。 バージョンの Visual Studio 6.0 まで Visual C では、割り当ての失敗時に null ポインターが返されます。 以降では、Visual Studio の 2002、`operator new`標準に準拠し、失敗した場合にスローされます。 Visual Studio がのリンク可能な実装を提供する、古い形式の割り当てを使用するコードをサポートする`operator new`nothrownew.obj と失敗した場合に null ポインターを返すにします。 既定では、コンパイラでは、エラー発生時に即時クラッシュの原因からこれらの古いスタイルのアロケーターを防ぐために守勢の null チェックも生成されます。 **/Zc:throwingNew**オプション、コンパイラはこれらの null チェック アウトのままにする、すべてメモリがリンクされていることを前提としてのアロケーターは、標準に準拠します。 これは、明示的なスローしないには適用されません`operator new`オーバー ロードは、型の他のパラメーターを使用して宣言された`std::nothrow_t`いて、明示的な`noexcept`仕様です。

概念的には、オブジェクトを作成、フリー ストアに、コンパイラが生成されますをそのメモリを割り当てるコードをメモリを初期化するために、そのコンス トラクターを呼び出すようにします。 Visual C コンパイラ通常できないことを指示のでこのコードは非適合、例外をスローしないアロケーターにリンクされるかどうか、既定ではそれも生成コンス トラクターを呼び出す前に、null チェックします。 これにより、null ポインター例外をスローしない割り当てに失敗した場合、コンス トラクターの呼び出しで逆参照します。 ほとんどの場合もこれらのチェックは、必要なため、既定`operator new`アロケーターが null ポインターを返す代わりにスローします。 チェックには、残念ながら副作用もがあります。 コードのサイズを膨張が、ブランチ予測を溢れさせて、および devirtualization など、初期化されたオブジェクトから const の伝達の他の便利コンパイラの最適化を抑制します。 チェックがサポート コードにリンクするためだけに存在*nothrownew.obj と*またはカスタム非準拠が`operator new`実装します。 非準拠を使用しない場合`operator new`を使用することをお勧め **/Zc:throwingNew**コードを最適化します。

**/Zc:throwingNew**オプションは、既定で無効として影響はありません、[寛容/-](permissive-standards-conformance.md)オプション。

リンク時コード生成 (LTCG) を使用してコンパイルする場合は指定する必要はありません **/Zc:throwingNew**です。 場合に、コンパイラが検出、コードをコンパイルするには、LTCG を使用すると、既定では、準拠している`operator new`実装を使用します。 場合は、コンパイラは自動的に null のチェック アウトはします。 リンカーの **/ThrowingNew**への通知フラグ場合の実装`operator new`準拠です。 新しいカスタム演算子を実装するため、ソースでこのディレクティブを含めることによって、リンカーには、このフラグを指定できます。

```cpp
#pragma comment(linker, "/ThrowingNew")
```

Visual C++ の準拠に関する問題について詳しくは、「 [Nonstandard Behavior](../../cpp/nonstandard-behavior.md)」をご覧ください。

## <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。

1. **構成**ドロップダウン メニューで、選択**すべて構成**です。

1. 選択、**構成プロパティ** > **C/C++** > **コマンドライン**プロパティ ページ。

1. 変更、**追加オプション**含めるプロパティを **/Zc:throwingNew**または **/Zc:throwingNew-** を選択し**OK**です。

## <a name="see-also"></a>関連項目

[コンパイラ オプション](../../build/reference/compiler-options.md)<br/>
[コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)<br/>
[/Zc (準拠)](../../build/reference/zc-conformance.md)<br/>
[noexcept (C++)](../../cpp/noexcept-cpp.md)<br/>
[例外の仕様 (スロー) (C++)](../../cpp/exception-specifications-throw-cpp.md)<br/>
[(例外) の終了します。](../../standard-library/exception-functions.md#terminate)<br/>
