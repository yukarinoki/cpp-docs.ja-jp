---
title: static_assert
ms.date: 11/04/2016
f1_keywords:
- static_assert_cpp
helpviewer_keywords:
- C++ keywords, static_assert
- C2338
- assertions [C++], static_assert
- static_assert
ms.assetid: 28dd3668-e78c-4de8-ba68-552084743426
ms.openlocfilehash: d5ef1ba45001a2b1a3ee1f2da46f66224857b070
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50668976"
---
# <a name="staticassert"></a>static_assert

コンパイル時にソフトウェアのアサーションをテストします。 コンパイラに指定されたメッセージが表示されますが提供され、コンパイル エラー C2338; で失敗した場合、指定された定数式が FALSE の場合それ以外の場合、宣言には影響はありません。

## <a name="syntax"></a>構文

```
static_assert( constant-expression, string-literal );

static_assert( constant-expression ); // Visual Studio 2017 and later
```

#### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*constant-expression*|ブール型に変換できる整数定数式。<br /><br /> 式の評価結果が 0 の場合 (false)、*文字列リテラル*パラメーターが表示され、コンパイル エラーで失敗します。 式が 0 以外の値 (true) の場合、 **static_assert**宣言が影響を与えません。|
|*string-literal*|場合に表示するメッセージを*定数式*パラメーターが 0 です。 メッセージが内の文字の文字列、[基本文字セット](../c-language/ascii-character-set.md); は、コンパイラのではなく、[マルチバイトまたはワイド文字](../c-language/multibyte-and-wide-characters.md)します。|

## <a name="remarks"></a>Remarks

*定数式*のパラメーターを**static_assert**宣言を表します、*ソフトウェアのアサーション*します。 ソフトウェアのアサーションは、プログラムの特定位置にある true となるはずの条件を指定します。 条件が true の場合、 **static_assert**宣言が影響を与えません。 アサーションは失敗し、条件が false の場合は、コンパイラは、メッセージを表示します。*文字列リテラル*パラメーター、およびエラーと、コンパイルは失敗します。 Visual Studio 2017 以降では、文字列リテラル パラメーターは省略可能です。

**Static_assert**宣言はコンパイル時にソフトウェアのアサーションをテストします。 これに対し、 [assert マクロ、_assert、_wassert](../c-runtime-library/reference/assert-macro-assert-wassert.md)マクロは、実行時にソフトウェアのアサーションをテストし、領域または時間の実行時のコストが生じます。 **Static_assert**宣言がテンプレート引数に含まれるため、テンプレートをデバッグするために特に便利ですが、*定数式*パラメーター。

コンパイラは、 **static_assert**の宣言が検出されたときに、構文エラーを宣言します。 コンパイラは、評価、*定数式*テンプレート パラメーターに依存しない場合にすぐには、パラメーター。 それ以外の場合、コンパイラは、評価、*定数式*パラメーターは、テンプレートがインスタンス化される場合。 その結果、コンパイラは、宣言を検出したときに一度、テンプレートがインスタンス化されたときに再度、診断メッセージを発行することがあります。

使用することができます、 **static_assert**名前空間、クラス、またはブロック スコープにキーワードを指定します。 (、 **Static_assert**場合でも、これはされていない新しい名前をプログラムに名前空間スコープで使用できるため、キーワードは宣言では技術的です)。

## <a name="description"></a>説明

次の例では、 **static_assert**宣言は名前空間スコープを持ちます。 コンパイラは `void *` 型のサイズがわかっているので、式は直ちに評価されます。

## <a name="example"></a>例

```cpp
static_assert(sizeof(void *) == 4, "64-bit code generation is not supported.");
```

## <a name="description"></a>説明

次の例では、 **static_assert**宣言はクラス スコープを持ちます。 **Static_assert**テンプレート パラメーターがあることを確認、*プレーンな古いデータ*(POD) 型。 コンパイラは、 **static_assert**宣言が宣言されると、評価されないときに、*定数式*までパラメーター、 `basic_string` でクラステンプレートがインスタンス化`main()`.

## <a name="example"></a>例

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

次の例では、 **static_assert**宣言はブロック スコープを持ちます。 **Static_assert** VMPage 構造体のサイズが、システムの仮想メモリ pagesize と等しいことを確認します。

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
[#error ディレクティブ (C/C++)](../preprocessor/hash-error-directive-c-cpp.md)<br/>
[assert マクロ、_assert、_wassert](../c-runtime-library/reference/assert-macro-assert-wassert.md)<br/>
[テンプレート](../cpp/templates-cpp.md)<br/>
[ASCII 文字セット](../c-language/ascii-character-set.md)<br/>
[宣言と定義](declarations-and-definitions-cpp.md)