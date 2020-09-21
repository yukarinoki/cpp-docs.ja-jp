---
title: static_assert
ms.date: 07/29/2019
f1_keywords:
- static_assert_cpp
helpviewer_keywords:
- assertions [C++], static_assert
- static_assert
ms.assetid: 28dd3668-e78c-4de8-ba68-552084743426
ms.openlocfilehash: b30af5fcf5d4f58143e657d84e743ef09a34e268
ms.sourcegitcommit: 72161bcd21d1ad9cc3f12261aa84a5b026884afa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2020
ms.locfileid: "90742971"
---
# <a name="static_assert"></a>static_assert

コンパイル時にソフトウェアのアサーションをテストします。 指定された定数式がの場合、指定したメッセージが指定されて **`false`** いる場合はコンパイラによって表示され、コンパイルはエラー C2338 で失敗します。それ以外の場合、宣言は無効です。

## <a name="syntax"></a>構文

```
static_assert( constant-expression, string-literal );

static_assert( constant-expression ); // C++17 (Visual Studio 2017 and later)
```

### <a name="parameters"></a>パラメーター

*定数式*\
ブール型に変換できる整数定数式。 評価された式が 0 (false) の場合は、 *文字列リテラル* パラメーターが表示され、コンパイルはエラーで失敗します。 式が0以外 (true) の場合、 **`static_assert`** 宣言は無効です。

*文字列-リテラル*\
*定数式*のパラメーターが0の場合に表示されるメッセージ。 メッセージは、コンパイラの [基本文字セット](../c-language/ascii-character-set.md) 内の文字の文字列です。つまり、 [マルチバイト文字またはワイド文字](../c-language/multibyte-and-wide-characters.md)ではありません。

## <a name="remarks"></a>注釈

宣言の *定数式* のパラメーターは、 **`static_assert`** ソフトウェアの *アサーション*を表します。 ソフトウェアのアサーションは、プログラムの特定位置にある true となるはずの条件を指定します。 条件が true の場合、 **`static_assert`** 宣言は無効です。 条件が false の場合、アサーションは失敗し、コンパイラは *文字列リテラル* パラメーターにメッセージを表示し、コンパイルはエラーで失敗します。 Visual Studio 2017 以降では、文字列リテラルパラメーターは省略可能です。

この **`static_assert`** 宣言は、コンパイル時にソフトウェアのアサーションをテストします。 これに対し、 [Assert マクロおよび _assert および _wassert 関数](../c-runtime-library/reference/assert-macro-assert-wassert.md) は、実行時にソフトウェアアサーションをテストし、領域または時間で実行時のコストを発生させることになります。 宣言は、テンプレート **`static_assert`** 引数を *定数式* のパラメーターに含めることができるため、テンプレートのデバッグに特に便利です。

**`static_assert`** 宣言が検出されると、コンパイラは構文エラーの宣言を調べます。 コンパイラは、テンプレートパラメーターに依存していない場合、 *定数式* パラメーターを直ちに評価します。 それ以外の場合、コンパイラは、テンプレートがインスタンス化されるときに *定数式* パラメーターを評価します。 その結果、コンパイラは、宣言を検出したときに一度、テンプレートがインスタンス化されたときに再度、診断メッセージを発行することがあります。

キーワードは、 **`static_assert`** 名前空間、クラス、またはブロックスコープで使用できます。 (キーワードは、 **`static_assert`** プログラムに新しい名前が導入されていない場合でも、名前空間のスコープで使用できるため、技術的には宣言です)。

## <a name="description-of-static_assert-with-namespace-scope"></a>名前空間スコープを持つ static_assert の説明

次の例では、 **`static_assert`** 宣言に名前空間スコープが含まれています。 コンパイラは `void *` 型のサイズがわかっているので、式は直ちに評価されます。

## <a name="example-of-static_assert-with-namespace-scope"></a>名前空間スコープを持つ static_assert の例

```cpp
static_assert(sizeof(void *) == 4, "64-bit code generation is not supported.");
```

## <a name="description-of-static_assert-with-class-scope"></a>クラススコープを持つ static_assert の説明

次の例では、 **`static_assert`** 宣言にクラススコープが含まれています。 は、 **`static_assert`** テンプレートパラメーターが *plain old data* (ポッド) 型であることを確認します。 コンパイラは宣言 **`static_assert`** されているときに宣言を調べますが、 *constant-expression* `basic_string` クラステンプレートがでインスタンス化されるまで、定数式のパラメーターは評価されません `main()` 。

## <a name="example-of-static_assert-with-class-scope"></a>クラススコープを持つ static_assert の例

```cpp
#include <type_traits>
#include <iosfwd>
namespace std {
template <class CharT, class Traits = std::char_traits<CharT> >
class basic_string {
    static_assert(std::is_pod<CharT>::value,
                  "Template argument CharT must be a POD type in class template basic_string");
    // ...
    };
}

struct NonPOD {
    NonPOD(const NonPOD &) {}
    virtual ~NonPOD() {}
};

int main()
{
    std::basic_string<char> bs;
}
```

## <a name="description"></a>説明

次の例では、 **`static_assert`** 宣言にブロックスコープが含まれています。 は、 **`static_assert`** VMPage 構造のサイズがシステムの仮想メモリ pagesize と同じであることを確認します。

## <a name="example"></a>例

```cpp
#include <sys/param.h> // defines PAGESIZE
class VMMClient {
public:
    struct VMPage { // ...
           };
    int check_pagesize() {
    static_assert(sizeof(VMPage) == PAGESIZE,
        "Struct VMPage must be the same size as a system virtual memory page.");
    // ...
    }
// ...
};
```

## <a name="see-also"></a>関連項目

[アサーションとユーザー指定のメッセージ (C++)](../cpp/assertion-and-user-supplied-messages-cpp.md)<br/>
[#error ディレクティブ (C/c + +)](../preprocessor/hash-error-directive-c-cpp.md)<br/>
[assert マクロ、_assert、_wassert](../c-runtime-library/reference/assert-macro-assert-wassert.md)<br/>
[テンプレート](../cpp/templates-cpp.md)<br/>
[ASCII 文字セット](../c-language/ascii-character-set.md)<br/>
[宣言と定義](declarations-and-definitions-cpp.md)
