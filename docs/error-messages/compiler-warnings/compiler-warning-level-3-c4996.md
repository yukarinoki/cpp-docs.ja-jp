---
title: コンパイラの警告 (レベル 3) C4996
description: コンパイラの警告 C4996 が発生する理由と、その対処方法について説明します。
ms.date: 07/09/2020
f1_keywords:
- C4996
helpviewer_keywords:
- C4996
ms.assetid: 926c7cc2-921d-43ed-ae75-634f560dd317
ms.openlocfilehash: 9f834c548b2a6b291304bdbf0082659577bfd694
ms.sourcegitcommit: 80c8a512b361bd84e38958beb1a1bf6db7434021
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2020
ms.locfileid: "86180982"
---
# <a name="compiler-warning-level-3-c4996"></a>コンパイラの警告 (レベル 3) C4996

コードでは、*非推奨*とマークされている関数、クラスメンバー、変数、または typedef を使用します。 シンボルは、 [`__declspec(deprecated)`](../../cpp/deprecated-cpp.md) 修飾子または c++ 14 属性を使用して非推奨とされ [`[[deprecated]]`](../../cpp/attributes.md) ます。 実際の C4996 警告メッセージは、 `deprecated` 宣言の修飾子または属性によって指定されます。

> [!IMPORTANT]
> この警告は、常に、シンボルを宣言するヘッダーファイルの作成者からの意図的なメッセージです。 結果を理解することなく、非推奨のシンボルを使用しないでください。

## <a name="remarks"></a>解説

Visual Studio ライブラリの多くの関数、メンバー関数、テンプレート関数、およびグローバル変数は*非推奨*とされます。 POSIX や Microsoft 固有の関数などの一部は、現在、優先名が異なるため非推奨とされます。 一部の C ランタイムライブラリ関数は安全ではなく、より安全なバリアントがあるため、非推奨とされます。 他のユーザーは廃止されているため、非推奨となりました。 廃止されたメッセージには、通常、非推奨の関数またはグローバル変数の代替候補が含まれています。

## <a name="turn-off-the-warning"></a>警告をオフにする

C4996 の問題を解決するには、通常、コードを変更することをお勧めします。 代わりに、推奨される関数とグローバル変数を使用します。 移植性のために既存の関数または変数を使用する必要がある場合は、警告をオフにすることができます。

### <a name="turn-off-the-warning-for-a-specific-line-of-code"></a>特定のコード行の警告をオフにする

特定のコード行に対して警告をオフにするには、 [`warning`](../../preprocessor/warning.md) プラグマを使用し `#pragma warning(suppress : 4996)` ます。

### <a name="turn-off-the-warning-within-a-file"></a>ファイル内の警告をオフにする

ファイル内で次のすべての警告をオフにするには、警告プラグマを使用し `#pragma warning(disable : 4996)` ます。

### <a name="turn-off-the-warning-in-command-line-builds"></a>コマンドラインビルドで警告をオフにする

コマンドラインビルドで警告をグローバルにオフにするには、 [`/wd4996`](../../build/reference/compiler-option-warning-level.md) コマンドラインオプションを使用します。

### <a name="turn-off-the-warning-for-a-project-in-visual-studio"></a>Visual Studio でプロジェクトの警告をオフにする

Visual Studio IDE でプロジェクト全体の警告をオフにするには、次のようにします。

1. プロジェクトの [**プロパティページ**] ダイアログを開きます。 [プロパティページ] ダイアログの使用方法の詳細については、「[プロパティページ](../../build/reference/property-pages-visual-cpp.md)」を参照してください。

1. [**構成プロパティ**] [  >  **C/c + +**]  >  **[詳細設定**] プロパティページを選択します。

1. [**特定の警告を無効**にする] プロパティを編集して追加 *`4996`* します。 **[OK]** を選択して変更を適用します。

### <a name="disable-the-warning-using-preprocessor-macros"></a>プリプロセッサマクロを使用して警告を無効にする

また、プリプロセッサマクロを使用して、ライブラリで使用されている特定の特定のクラスの非推奨の警告を無効にすることもできます。 これらのマクロについて以下に説明します。

Visual Studio でプリプロセッサマクロを定義するには、次のようにします。

1. プロジェクトの [**プロパティページ**] ダイアログを開きます。 [プロパティページ] ダイアログの使用方法の詳細については、「[プロパティページ](../../build/reference/property-pages-visual-cpp.md)」を参照してください。

1. [**構成プロパティ] > C/c + + > プリプロセッサ**] の順に展開します。

1. [**プリプロセッサの定義**] プロパティで、マクロ名を追加します。 **[OK]** を選んで保存し、プロジェクトをリビルドします。

特定のソースファイルでのみマクロを定義するには、 `#define EXAMPLE_MACRO_NAME` ヘッダーファイルを含む行の前になどの行を追加します。

次に、C4996 の警告とエラーの一般的な原因をいくつか示します。

## <a name="posix-function-names"></a>POSIX 関数名

**`The POSIX name for this item is deprecated. Instead, use the ISO C and C++ conformant name:`** _`new-name.`_ **`See online help for details.`**

Microsoft は、一部の POSIX および Microsoft 固有のライブラリ関数を、予約済みおよびグローバル実装定義名に対する C99 および C++ 03 制約に準拠するように名前変更しました。 *関数自体ではなく、名前のみが非推奨とされ*ます。 ほとんどの場合、準拠する名前を作成するために、関数名に先頭のアンダースコアが追加されています。 コンパイラは、元の関数名に対して非推奨の警告を発行し、優先名を提案します。

この問題を解決するには、通常、推奨される関数名を代わりに使用するようにコードを変更することをお勧めします。 ただし、更新された名前は Microsoft 固有です。 移植性のために既存の関数名を使用する必要がある場合は、これらの警告をオフにすることができます。 これらの関数は、ライブラリ内の元の名前の下でも使用できます。

これらの関数の非推奨の警告をオフにするには、プリプロセッサマクロを定義し **`_CRT_NONSTDC_NO_WARNINGS`** ます。 このマクロは、コマンドラインでオプションを指定することによって定義でき `/D_CRT_NONSTDC_NO_WARNINGS` ます。

## <a name="unsafe-crt-library-functions"></a>Unsafe CRT ライブラリ関数

**`This function or variable may be unsafe. Consider using`** _`safe-version`_ **`instead. To disable deprecation, use _CRT_SECURE_NO_WARNINGS. See online help for details.`**

Microsoft では、セキュリティが強化されたバージョンを使用できるため、一部の CRT および C++ 標準ライブラリ関数およびグローバル変数は非推奨となりました。 非推奨の関数のほとんどでは、バッファーへの読み取りまたは書き込みアクセスがチェックされません。 誤用によって、セキュリティ上の深刻な問題が発生する可能性があります。 コンパイラは、これらの関数は使用されなくなったとの警告を発し、優先関数を提案します。

この問題を解決するには、代わりに関数または変数を使用することをお勧め *`safe-version`* します。 場合によっては、移植性や下位互換性の理由ではできないことがあります。 コード内でバッファーの上書きまたは過度な読み取りが発生しないことを慎重に確認してください。 その後、警告をオフにすることができます。

CRT でこれらの関数の非推奨の警告をオフにするには、を定義 **`_CRT_SECURE_NO_WARNINGS`** します。

非推奨のグローバル変数に関する警告をオフにするには、を定義 **`_CRT_SECURE_NO_WARNINGS_GLOBALS`** します。

これらの非推奨の関数とグローバルの詳細については、「CRT および安全なライブラリの[セキュリティ機能](../../c-runtime-library/security-features-in-the-crt.md) [: C++ 標準ライブラリ](../../standard-library/safe-libraries-cpp-standard-library.md)」を参照してください。

## <a name="unsafe-standard-library-functions"></a>安全でない標準ライブラリ関数

**`'std::`** *`function_name`* **`::_Unchecked_iterators::_Deprecate' Call to std::`** *`function_name`* **`with parameters that may be unsafe - this call relies on the caller to check that the passed values are correct. To disable this warning, use -D_SCL_SECURE_NO_WARNINGS. See documentation on how to use Visual C++ 'Checked Iterators'`**

Visual Studio 2015 では、特定の C++ 標準ライブラリのテンプレート関数ではパラメーターが正しいかどうかがチェックされないため、この警告はデバッグビルドで表示されます。 多くの場合、コンテナーの境界を確認するために関数で使用できる情報が不足していることが原因です。 または、反復子が関数で不適切に使用されている可能性があります。 この警告は、これらの関数を識別するのに役立ちます。これは、プログラムに重大なセキュリティホールがある可能性があるためです。 詳細については、「チェックを行う[反復子](../../standard-library/checked-iterators.md)」を参照してください。

たとえば、この警告は、プレーン配列ではなく、要素ポインターをに渡すと、デバッグモードで表示され `std::copy` ます。 この問題を解決するには、適切に宣言された配列を使用して、ライブラリが配列の範囲を確認し、境界のチェックを実行できるようにします。

```cpp
// C4996_copyarray.cpp
// compile with: cl /c /W4 /D_DEBUG C4996_copyarray.cpp
#include <algorithm>

void example(char const * const src) {
    char dest[1234];
    char * pdest3 = dest + 3;
    std::copy(src, src + 42, pdest3); // C4996
    std::copy(src, src + 42, dest);   // OK, copy can tell that dest is 1234 elements
}
```

C++ 14 では、いくつかの標準ライブラリアルゴリズムが "デュアル範囲" バージョンに更新されました。 2つの範囲のバージョンを使用する場合、2番目の範囲は必要な範囲チェックを行います。

```cpp
// C4996_containers.cpp
// compile with: cl /c /W4 /D_DEBUG C4996_containers.cpp
#include <algorithm>

bool example(
    char const * const left,
    const size_t leftSize,
    char const * const right,
    const size_t rightSize)
{
    bool result = false;
    result = std::equal(left, left + leftSize, right); // C4996
    // To fix, try this form instead:
    // result = std::equal(left, left + leftSize, right, right + rightSize); // OK
    return result;
}
```

この例では、標準ライブラリを使用して反復子の使用法を確認する方法をいくつか示します。また、チェックをオフにした場合には危険な場合があります。

```cpp
// C4996_standard.cpp
// compile with: cl /EHsc /W4 /MDd C4996_standard.cpp
#include <algorithm>
#include <array>
#include <iostream>
#include <iterator>
#include <numeric>
#include <string>
#include <vector>

using namespace std;

template <typename C> void print(const string& s, const C& c) {
    cout << s;

    for (const auto& e : c) {
        cout << e << " ";
    }

    cout << endl;
}

int main()
{
    vector<int> v(16);
    iota(v.begin(), v.end(), 0);
    print("v: ", v);

    // OK: vector::iterator is checked in debug mode
    // (i.e. an overrun triggers a debug assertion)
    vector<int> v2(16);
    transform(v.begin(), v.end(), v2.begin(), [](int n) { return n * 2; });
    print("v2: ", v2);

    // OK: back_insert_iterator is marked as checked in debug mode
    // (i.e. an overrun is impossible)
    vector<int> v3;
    transform(v.begin(), v.end(), back_inserter(v3), [](int n) { return n * 3; });
    print("v3: ", v3);

    // OK: array::iterator is checked in debug mode
    // (i.e. an overrun triggers a debug assertion)
    array<int, 16> a4;
    transform(v.begin(), v.end(), a4.begin(), [](int n) { return n * 4; });
    print("a4: ", a4);

    // OK: Raw arrays are checked in debug mode
    // (i.e. an overrun triggers a debug assertion)
    // NOTE: This applies only when raw arrays are
    // given to C++ Standard Library algorithms!
    int a5[16];
    transform(v.begin(), v.end(), a5, [](int n) { return n * 5; });
    print("a5: ", a5);

    // WARNING C4996: Pointers cannot be checked in debug mode
    // (i.e. an overrun triggers undefined behavior)
    int a6[16];
    int * p6 = a6;
    transform(v.begin(), v.end(), p6, [](int n) { return n * 6; });
    print("a6: ", a6);

    // OK: stdext::checked_array_iterator is checked in debug mode
    // (i.e. an overrun triggers a debug assertion)
    int a7[16];
    int * p7 = a7;
    transform(v.begin(), v.end(),
        stdext::make_checked_array_iterator(p7, 16),
        [](int n) { return n * 7; });
    print("a7: ", a7);

    // WARNING SILENCED: stdext::unchecked_array_iterator
    // is marked as checked in debug mode, but it performs no checking,
    // so an overrun triggers undefined behavior
    int a8[16];
    int * p8 = a8;
    transform( v.begin(), v.end(),
        stdext::make_unchecked_array_iterator(p8),
        [](int n) { return n * 8; });
    print("a8: ", a8);
}
```

コードでバッファーオーバーランエラーが発生しないことを確認した場合は、この警告をオフにすることができます。 これらの関数の警告をオフにするには、を定義 **`_SCL_SECURE_NO_WARNINGS`** します。

## <a name="checked-iterators-enabled"></a>チェックを行う反復子有効

`_ITERATOR_DEBUG_LEVEL`また、が1または2として定義されている場合に、チェックを行う反復子を使用しないと、C4996 も発生する可能性があります。 これは、デバッグモードのビルドでは既定で2に設定され、リテールビルドの場合は0に設定されます。 詳細については、「チェックを行う[反復子](../../standard-library/checked-iterators.md)」を参照してください。

```cpp
// C4996_checked.cpp
// compile with: /EHsc /W4 /MDd C4996_checked.cpp
#define _ITERATOR_DEBUG_LEVEL 2

#include <algorithm>
#include <iterator>

using namespace std;
using namespace stdext;

int main() {
    int a[] = { 1, 2, 3 };
    int b[] = { 10, 11, 12 };
    copy(a, a + 3, b + 1);   // C4996
    // try the following line instead:
    // copy(a, a + 3, checked_array_iterator<int *>(b, 3));   // OK
}
```

## <a name="unsafe-mfc-or-atl-code"></a>Unsafe MFC または ATL コード

C4996 は、セキュリティ上の理由から非推奨とされた MFC 関数または ATL 関数を使用した場合に発生する可能性があります。

この問題を解決するには、代わりに更新された関数を使用するようにコードを変更することを強くお勧めします。

これらの警告を抑制する方法の詳細については、「」を参照してください [`_AFX_SECURE_NO_WARNINGS`](../../mfc/reference/diagnostic-services.md#afx_secure_no_warnings) 。

## <a name="obsolete-crt-functions-and-variables"></a>廃止された CRT 関数と変数

**`This function or variable has been superseded by newer library or operating system functionality. Consider using`** *`new_item`* **`instead. See online help for details.`**

一部のライブラリ関数およびグローバル変数は非推奨とされるため使用されていません。 これらの関数および変数は、将来のバージョンのライブラリでは削除される可能性があります。 コンパイラは、これらの項目は使用されなくなったとの警告を発行し、優先すべき代替項目を提案します。

この問題を解決するには、推奨される関数または変数を使用するようにコードを変更することをお勧めします。

これらの項目の非推奨の警告をオフにするには、を定義 **`_CRT_OBSOLETE_NO_WARNINGS`** します。 詳しくは、非推奨の関数または変数のドキュメントをご覧ください。

## <a name="marshaling-errors-in-clr-code"></a>CLR コードのマーシャリングエラー

C4996 は、CLR マーシャリングライブラリを使用するときにも発生する可能性があります。 この場合、C4996 はエラーであり、警告ではありません。 このエラーは、を使用し [`marshal_as`](../../dotnet/marshal-as.md) て、 [ `marshal_context` クラス](../../dotnet/marshal-context-class.md)を必要とする2つのデータ型の間で変換を行う場合に発生します。 また、マーシャリングライブラリが変換をサポートしていない場合にも、このエラーが発生することがあります。 マーシャリングライブラリの詳細については、「 [C++ におけるマーシャリングの概要](../../dotnet/overview-of-marshaling-in-cpp.md)」を参照してください。

この例では、をに変換するコンテキストがマーシャリングライブラリに必要であるため、C4996 が生成され `System::String` `const char *` ます。

```cpp
// C4996_Marshal.cpp
// compile with: /clr
// C4996 expected
#include <stdlib.h>
#include <string.h>
#include <msclr\marshal.h>

using namespace System;
using namespace msclr::interop;

int main() {
   String^ message = gcnew String("Test String to Marshal");
   const char* result;
   result = marshal_as<const char*>( message );
   return 0;
}
```

## <a name="example-user-defined-deprecated-function"></a>例: ユーザー定義の非推奨の関数

`deprecated`特定の関数の使用が推奨されなくなったときに、独自のコードで属性を使用して、呼び出し元に警告することができます。 この例では、C4996 は、非推奨の関数が宣言されている行と、関数が使用されている行の2つの場所で生成されます。

```cpp
// C4996.cpp
// compile with: /W3
// C4996 warning expected
#include <stdio.h>

// #pragma warning(disable : 4996)
void func1(void) {
   printf_s("\nIn func1");
}

[[deprecated]]
void func1(int) {
   printf_s("\nIn func2");
}

int main() {
   func1();
   func1(1);    // C4996
}
```
