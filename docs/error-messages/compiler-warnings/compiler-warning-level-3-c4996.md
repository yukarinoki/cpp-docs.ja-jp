---
title: コンパイラの警告 (レベル 3) C4996 |Microsoft Docs
ms.custom: ''
ms.date: 11/17/2017
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4996
dev_langs:
- C++
helpviewer_keywords:
- C4996
ms.assetid: 926c7cc2-921d-43ed-ae75-634f560dd317
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dff9f3c988e7ffdf8f15b5502bb0326e2692a128
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2018
ms.locfileid: "50079039"
---
# <a name="compiler-warning-level-3-c4996"></a>コンパイラの警告 (レベル 3) C4996

非推奨の宣言をコンパイラが検出しました。 **この警告は、常に含まれるヘッダー ファイルが、結果を検討して、非推奨のシンボルを使用しないでください、ライブラリの作成者から意図的なメッセージです。** 実際の警告メッセージは、廃止修飾子または宣言のサイトにある属性によって指定されます。

これらは、C ランタイム ライブラリと標準のライブラリが完全なリストではなくによって生成されるいくつかの一般的な C4996 メッセージです。 リンクや、警告をオフにしたり、問題を解決する方法についてお読みください。

- [このアイテムの POSIX 名が非推奨とされます。代わりに、ISO C および C++ に準拠する名前を使用: *new_name*します。詳しくは、オンライン ヘルプをご覧ください。](#posix-function-names)

- [この関数または変数が安全なない可能性があります。使用を検討して*safe_version*代わりにします。非推奨を無効にするには、 \_CRT\_SECURE\_いいえ\_警告します。詳しくは、オンライン ヘルプをご覧ください。](#unsafe-crt-library-functions)

- [' std::*function_name*::\_未チェック\_反復子::\_Deprecate' 呼び出し std::*function_name*この呼び出しが依存する安全でない可能性がありますパラメーターを使用渡された値が正しいことを確認する呼び出し元。この警告を無効にするには、-D_SCL_SECURE_NO_WARNINGS を使用します。Visual C ' Checked Iterators' を使用する方法のドキュメントを参照してください。](#unsafe-standard-library-functions)

- [この関数または変数は、新しいライブラリまたはオペレーティング システムの機能が提供されています。使用を検討して*new_item*代わりにします。詳しくは、オンライン ヘルプをご覧ください。](#obsolete-crt-functions-and-variables)

## <a name="cause"></a>原因

C4996 は、コンパイラは、関数または変数としてマークされているが発生したときに発生します[非推奨とされます](../../cpp/deprecated-cpp.md)を使用して、`__declspec(deprecated)`修飾子は、関数、クラス メンバーまたは c++ 14 の typedef にアクセスしようとするまたは[ 。\[\[非推奨とされます\]\] ](../../cpp/attributes.md)属性。 使用することができます、`__declspec(deprecated)`修飾子または`[[deprecated]]`自分で、ライブラリまたは非推奨の関数、変数、メンバー、またはの typedef には、クライアントに警告するヘッダー ファイル内の属性します。

## <a name="remarks"></a>Remarks

多くの関数、メンバー関数、テンプレート関数、および Visual Studio でライブラリ内のグローバル変数はマーク*非推奨とされます*します。 これらの関数は、可能性があります別の優先名があるが安全でないことかがより安全なバリアントでは、非推奨と古いものがありますか。 多くの非推奨メッセージには、非推奨の関数またはグローバル変数の推奨される置換が含まれます。

この問題を解決するには、通常お勧めします代わりに、推奨される安全または更新された関数とグローバル変数を使用するコードを変更します。 移植性上の理由から、既存の関数または変数を使用する必要がある場合、警告を無効にできます。

### <a name="to-turn-the-warning-off-without-fixing-the-issue"></a>問題が解決せずに、警告をオフにするには

使用して、特定の行のコードに関する警告をオフにできます、[警告](../../preprocessor/warning.md)プラグマ、`#pragma warning(suppress : 4996)`します。 することも、警告をオフ ファイル内で、警告プラグマを使用して`#pragma warning(disable : 4996)`します。

オフにできます警告グローバル コマンド ライン ビルドを使用して、 **/wd4996**コマンド ライン オプション。

Visual Studio IDE でプロジェクト全体の警告をオフにするには。

- 開く、**プロパティ ページ**プロジェクトのダイアログ。 プロパティ ページ ダイアログを使用する方法については、次を参照してください。[プロパティ ページ](../../ide/property-pages-visual-cpp.md)します。
- 選択、**構成プロパティ**、 **C/C++**、**詳細**ページ。
- 編集、**特定の警告を無効にする**プロパティを追加する`4996`します。 選択**OK**変更を適用します。

特定の特定のクラス ライブラリで使用されている非推奨に関する警告のオフにするプリプロセッサ マクロを使用することもできます。 これらのマクロは次のとおりです。

Visual Studio では、プリプロセッサ マクロを定義します。

- 開く、**プロパティ ページ**プロジェクトのダイアログ。 プロパティ ページ ダイアログを使用する方法については、次を参照してください。[プロパティ ページ](../../ide/property-pages-visual-cpp.md)します。
- 展開**構成プロパティ > [C/C++] > プリプロセッサ**します。
- **プリプロセッサの定義**プロパティ、マクロ名を追加します。 **[OK]** を選んで保存し、プロジェクトをリビルドします。

特定のソース ファイルでのみマクロを定義するには、行をなど追加`#define EXAMPLE_MACRO_NAME`ヘッダー ファイルを含む任意の行の前にします。

## <a name="specific-c4996-messages"></a>特定の C4996 メッセージ

C4996 が警告およびエラーの一般的なソースの一部を示します。

### <a name="posix-function-names"></a>POSIX 関数名

**このアイテムの POSIX 名が非推奨とされます。代わりに、ISO C および C++ に準拠する名前を使用:** *new_name*します。 **詳細については、オンライン ヘルプを参照してください。**

Microsoft は C99 と c++ 03 の規則の実装で定義されたグローバル関数名に準拠するように CRT で一部の POSIX 関数の名前を変更します。 元の POSIX 名のみの非推奨とされますが、関数自体ではありません。 ほとんどの場合、標準準拠の名前を作成するため POSIX 関数名の先頭にアンダースコアが追加されています。 コンパイラは、元の関数名の非推奨の警告を発行し、優先名を提案します。

この問題を解決するには、通常お勧めします推奨の関数名の代わりに使用するコードを変更します。 ただし、更新された名前は、Microsoft 固有です。 移植性のための既存の関数名を使用する必要がある場合は、これらの警告をオフにすることができます。 POSIX 関数は、ライブラリ、元の名前で引き続き使用できます。

これらの関数の警告をオフにするには、プリプロセッサ マクロを定義して **\_CRT\_NONSTDC\_いいえ\_警告**します。 コマンドラインでこのマクロを定義するには、オプションを含めることによって`/D_CRT_NONSTDC_NO_WARNINGS`します。

### <a name="unsafe-crt-library-functions"></a>安全でない CRT ライブラリ関数

**この関数または変数が安全なない可能性があります。使用を検討して** *safe_version* **代わりにします。非推奨を無効にするには、 \_CRT\_SECURE\_いいえ\_警告します。詳しくは、オンライン ヘルプをご覧ください。**

Microsoft には、いくつかの CRT と C++ 標準ライブラリの関数とより安全なバージョンを優先してグローバルは非推奨とされます。 ほとんどの場合では、非推奨の関数は、未チェックの読み取りまたは重大なセキュリティ問題につながる、バッファーへの書き込みアクセスを許可します。 コンパイラは、これらの関数は使用されなくなったとの警告を発し、優先関数を提案します。

この問題を解決するをお勧め関数または変数を使用する*safe_version*代わりにします。 バッファーの上書きのことはできませんまたは移植性のためのコードを変更することはできません overread して、コードで発生することを確認した場合は、警告をオフにできます。

CRT のこれらの関数の警告をオフにするには、次のように定義します。  **\_CRT\_SECURE\_いいえ\_警告**します。 非推奨のグローバル変数に関する警告をオフにするには、次のように定義します。  **\_CRT\_SECURE\_いいえ\_警告\_GLOBALS**します。 これらの非推奨の関数とグローバル変数の詳細については、次を参照してください。 [CRT のセキュリティ機能](../../c-runtime-library/security-features-in-the-crt.md)と[安全なライブラリ: C++ 標準ライブラリ](../../standard-library/safe-libraries-cpp-standard-library.md)します。

### <a name="unsafe-standard-library-functions"></a>安全でない標準ライブラリ関数

__' std::__*function_name*__::\_未チェック\_反復子::\_Deprecate' 呼び出し std::__*function_name***安全でない可能性がありますのパラメーターで、この呼び出しが渡された値が正しいことを確認する呼び出し元に依存します。この警告を無効にするには、-d を使用して\_SCL\_SECURE\_いいえ\_警告します。Visual C ' Checked Iterators' を使用する方法のドキュメントを参照してください。**

特定の C++ 標準ライブラリ テンプレート関数はパラメーターが正しいかどうかを確認しないために、デバッグ ビルドでこの警告が表示されます。 ほとんどの場合、これは十分な情報が、関数のコンテナーの範囲のチェックに利用できるため、または反復子がで使用するためいない正しく関数。 この警告は、プログラムで重大なセキュリティ ホールのソースがありますので、これらの関数の使用を識別するのに役立ちます。 詳細については、「 [Checked Iterators](../../standard-library/checked-iterators.md)」を参照してください。

要素へのポインターを渡す場合など、この警告がデバッグ モードで表示されます`std::copy`プレーンな配列の代わりにします。 この問題を解決するには、ライブラリが配列の範囲を確認し、境界チェックを実行できるように、適切に宣言された配列を使用します。

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

いくつかの標準ライブラリ アルゴリズムは、c++ 14 で「デュアル範囲」のバージョンに更新されました。 デュアル範囲のバージョンを使用する場合、2 番目の範囲は、必要な境界チェックを提供します。

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

この例は、標準ライブラリ反復子の使用状況を確認に使用できるいくつかの他の方法と使用状況のチェックを行わないが危険な可能性があります。

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

バッファー オーバーランこの警告をトリガーする標準ライブラリ関数でエラー コードことはできないことを確認した場合は、この警告をオフにしたい場合があります。 これらの関数の警告をオフに、次のように定義します。  **\_SCL\_SECURE\_いいえ\_警告**します。

### <a name="checked-iterators-enabled"></a>Checked 反復子が有効になっています。

コンパイルする場合にチェックされている反復子を使用しない場合にも C4996 `_ITERATOR_DEBUG_LEVEL` 1 または 2 として定義されています。 既定ではデバッグ モードのビルドには 2 に、製品版ビルドでは 0 に設定されます。 詳細については、「 [Checked Iterators](../../standard-library/checked-iterators.md) 」を参照してください。

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

### <a name="unsafe-mfc-or-atl-code"></a>安全でない MFC または ATL コード

C4996 は、セキュリティ上の理由から非推奨とされた MFC または ATL の関数を使用する場合にも発生します。

この問題を解決するには、強くお勧めの更新された関数を代わりに使用するコードを変更します。

これらの警告を抑制する方法については、次を参照してください。 [_AFX_SECURE_NO_WARNINGS](../../mfc/reference/diagnostic-services.md#afx_secure_no_warnings)します。

### <a name="obsolete-crt-functions-and-variables"></a>廃止された CRT 関数と変数

**この関数または変数は、新しいライブラリまたはオペレーティング システムの機能が提供されています。使用を検討して** *new_item* **代わりにします。詳しくは、オンライン ヘルプをご覧ください。**

一部のライブラリ関数およびグローバル変数は非推奨とされるため使用されていません。 これらの関数および変数は、将来のバージョンのライブラリでは削除される可能性があります。 コンパイラは、これらの項目は使用されなくなったとの警告を発行し、優先すべき代替項目を提案します。

この問題を解決するには、推奨の関数または変数を使用するコードを変更するをお勧めします。

これらの項目の警告をオフにするには、次のように定義します。  **\_CRT\_OBSOLETE\_いいえ\_警告**します。 詳しくは、非推奨の関数または変数のドキュメントをご覧ください。

### <a name="marshalling-errors-in-clr-code"></a>CLR コードのマーシャリング エラー

C4996 は、CLR マーシャ リング ライブラリを使用する場合にも発生します。 この場合、C4996 はエラーであり、警告ではありません。 このエラーは、使用するときに発生します。 [marshal_as](../../dotnet/marshal-as.md)を必要とする 2 つのデータ型の間で変換する、 [marshal_context クラス](../../dotnet/marshal-context-class.md)します。 マーシャ リング ライブラリは、変換をサポートしていない場合にも、このエラーを受信できます。 マーシャリング ライブラリについて詳しくは、「 [Overview of Marshaling in C++](../../dotnet/overview-of-marshaling-in-cpp.md)」をご覧ください。

この例では、マーシャ リング ライブラリが、コンテキストから変換する必要があるため C4996 が生成されます、`System::String`を`const char *`します。

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

## <a name="example-user-defined-deprecated-function"></a>例: ユーザー定義の非推奨機能

独自のコードで非推奨の属性を使用すると、不要になった特定の関数の使用を推奨するときに呼び出し元に警告します。 この例では、関数を使用している行と、非推奨の関数が宣言されている行の C4996 が生成されます。

```cpp
// C4996.cpp
// compile with: /W3
// C4996 warning expected
#include <stdio.h>

// #pragma warning(disable : 4996)
void func1(void) {
   printf_s("\nIn func1");
}

__declspec(deprecated) void func1(int) {
   printf_s("\nIn func2");
}

int main() {
   func1();
   func1(1);    // C4996
}
```
