---
title: '/Zc: noexcepttypes (c++ 17 noexcept ルール)'
ms.date: 11/14/2017
f1_keywords:
- /Zc:noexceptTypes
helpviewer_keywords:
- /Zc:noexceptTypes
- Zc:noexceptTypes
- -Zc:noexceptTypes
ms.assetid: 1cbf7e3c-0f82-4f91-84dd-612bcf26d2c6
ms.openlocfilehash: 28e06f54049d36262134b6be7eadb0e6e5349a45
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2019
ms.locfileid: "57812110"
---
# <a name="zcnoexcepttypes-c17-noexcept-rules"></a>/Zc: noexcepttypes (c++ 17 noexcept ルール)

標準の c++ 17 で`throw()`のエイリアスとして`noexcept`、削除`throw(<type list>)`と`throw(...)`、でき、特定の種類を含める`noexcept`。 C++ 14 またはそれ以前に準拠したコードでのさまざまなソースの互換性の問題が生じる。 **/Zc: noexcepttypes**オプションは、c++ 17 標準に適合するを指定したり、c++ 17 モードでコードがコンパイルされるときに、c++ 14 と以前の動作を許可します。

## <a name="syntax"></a>構文

> **/Zc:noexceptTypes**[-]

## <a name="remarks"></a>Remarks

ときに、 **/zc: noexcepttypes**オプションを指定すると、コンパイラは、標準の c++ 17 に準拠しているし、処理[throw()](../../cpp/exception-specifications-throw-cpp.md)のエイリアスとして[noexcept](../../cpp/noexcept-cpp.md)を削除します`throw(<type list>)`。と`throw(...)`、特定の種類を含めることができ`noexcept`します。 **/Zc: noexcepttypes**場合オプションは使用のみ[/std:c + + 17](std-specify-language-standard-version.md)または[/std:latest](std-specify-language-standard-version.md)を有効にします。 **/Zc: noexcepttypes** ISO C 17 標準に準拠するように既定で有効です。 [/Permissive -](permissive-standards-conformance.md)オプションには影響しません **/zc: noexcepttypes**します。 指定することで、このオプションをオフに **/Zc:noexceptTypes-** の c++ 14 動作に戻す`noexcept`とき **/std::C + + 17**または **/std::latest**が指定されてです。

C コンパイラで Visual Studio 2017 バージョン 15.5 以降では、c++ 17 モードでの宣言で複数の一致しない例外の指定を診断または、 [/permissive -](permissive-standards-conformance.md)オプションを指定します。

この例では、例外の指定子で宣言ときの動作、 **/zc: noexcepttypes**オプションを設定するか、または無効になっています。 動作を設定するを使用してコンパイル`cl /EHsc /W4 noexceptTypes.cpp`します。 無効になっているときの動作を表示するを使用してコンパイル`cl /EHsc /W4 /Zc:noexceptTypes- noexceptTypes.cpp`します。

```cpp
// noexceptTypes.cpp
// Compile by using: cl /EHsc /W4 noexceptTypes.cpp
// Compile by using: cl /EHsc /W4 /Zc:noexceptTypes- noexceptTypes.cpp

void f() throw();    // equivalent to void f() noexcept;
void f() { }         // warning C5043
void g() throw(...); // warning C5040

struct A
{
    virtual void f() throw();
};

struct B : A
{
    virtual void f() { } // error C2694
};
```

既定の設定を使用して、コンパイル時に **/zc: noexcepttypes**サンプルには、表示されている警告が生成されます。 コードを更新するには、次の使用を代わりに。

```cpp
void f() noexcept;
void f() noexcept { }
void g() noexcept(false);

struct A
{
    virtual void f() noexcept;
};

struct B : A
{
    virtual void f() noexcept { }
};
```

Visual C++ の準拠に関する問題について詳しくは、「 [Nonstandard Behavior](../../cpp/nonstandard-behavior.md)」をご覧ください。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境において、このコンパイラ オプションを設定する方法

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での設定の C++ コンパイラとビルド プロパティ](../working-with-project-properties.md)を参照してください。

1. 選択、**構成プロパティ** > **C/C++** > **コマンドライン**プロパティ ページ。

1. 変更、**追加オプション**含めるプロパティを **/zc: noexcepttypes**または **/Zc:noexceptTypes-** 選び、 **OK**します。

## <a name="see-also"></a>関連項目

[/Zc (準拠)](zc-conformance.md)<br/>
[noexcept](../../cpp/noexcept-cpp.md)<br/>
[例外の仕様 (スロー)](../../cpp/exception-specifications-throw-cpp.md)
