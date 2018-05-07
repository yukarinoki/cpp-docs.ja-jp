---
title: コンパイラの警告 (レベル 3) C4996 |Microsoft ドキュメント
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
ms.openlocfilehash: a6af8a8ff3cde50ea8b196e7f293874998547ec0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-3-c4996"></a>コンパイラの警告 (レベル 3) C4996

非推奨の宣言をコンパイラが検出しました。 **この警告は、常に、ライブラリまたは結果を理解することがなく、非推奨のシンボルを使用しないで含まれているヘッダー ファイルの作成者から意図的なメッセージです。** 実際の警告メッセージは、deprecation 修飾子または宣言のサイトにある属性によって指定されます。 

これらは、C ランタイム ライブラリと標準のライブラリが、排他的なリストではないによって生成される一般的な C4996 メッセージです。 リンクまたは警告をオフにするにまたは、問題を解決する方法をお読みです。 

- [このアイテムの POSIX 名は使用されなくなりました。代わりに、ISO C および C++ に準拠する名前を使用: *new_name*です。詳しくは、オンライン ヘルプをご覧ください。](#posix-function-names)

- [この関数または変数が安全でない可能性があります。使用を検討して*safe_version*代わりにします。廃止予定機能を無効にするには、 \_CRT\_SECURE\_いいえ\_警告します。詳しくは、オンライン ヘルプをご覧ください。](#unsafe-crt-library-functions)

- [' std::*function_name*::\_未チェック\_反復子::\_Deprecate' std への呼び出し::*function_name*に安全でない可能性がありますパラメーターを使用してこの呼び出しが依存しています呼び出し元が渡された値が正しいことを確認します。この警告を無効にするには、-D_SCL_SECURE_NO_WARNINGS を使用します。Visual C '反復子のチェック' を使用する方法のドキュメントを参照してください。](#unsafe-standard-library-functions)

- [この関数または変数は、新しいライブラリまたはオペレーティング システムの機能が提供されています。使用を検討して*new_item*代わりにします。詳しくは、オンライン ヘルプをご覧ください。](#obsolete-crt-functions-and-variables)

## <a name="cause"></a>原因

C4996 は、関数または変数としてマークされている、コンパイラが検出したときに発生[廃止](../../cpp/deprecated-cpp.md)を使用して、`__declspec(deprecated)`修飾子は、関数、クラス メンバーまたは c++ 14 のある typedef にアクセスしようとするまたは[ \[\[廃止\]\] ](../../cpp/attributes.md)属性。 使用することができます、`__declspec(deprecated)`修飾子または`[[deprecated]]`ライブラリまたはヘッダー ファイルは使用されなくなった関数、変数、メンバー、または typedef、クライアントに警告する を自分で属性します。

## <a name="remarks"></a>コメント

多くの関数、メンバー関数、テンプレート関数、および Visual Studio でライブラリ内のグローバル変数とマークされて*廃止*です。 これらの関数が推奨されなくなった、可能性があります別の優先名がある可能性があります安全でないことやより安全なバリアントがあるため古い可能性がありますか。 多くの deprecation メッセージには、非推奨の関数やグローバル変数の代わりに候補が含まれます。

この問題を修正するには、通常をお勧め、推奨される安全なまたは更新された関数とグローバル変数の代わりに使用するコードを変更します。 移植性上の理由から、既存の関数または変数を使用する必要がある場合、警告はオフにすることができます。

### <a name="to-turn-the-warning-off-without-fixing-the-issue"></a>問題を修正することがなく、警告をオフに設定する

使用して特定のコード行に対する警告を無効にすることができます、[警告](../../preprocessor/warning.md)プラグマ、`#pragma warning(suppress : 4996)`です。 することも、警告をオフ、ファイル内で警告プラグマを使用して`#pragma warning(disable : 4996)`です。

オフにできます警告グローバル コマンド ライン ビルドを使用して、 **/wd4996**コマンド ライン オプションです。

Visual Studio IDE でプロジェクト全体に対する警告をオフにします。

- 開く、**プロパティ ページ**プロジェクトのダイアログ。 プロパティ ページ ダイアログを使用する方法については、次を参照してください。[プロパティ ページ](../../ide/property-pages-visual-cpp.md)です。
- 選択、**構成プロパティ**、 **C/C++**、**詳細**ページ。
- 編集、**特定の警告を無効にする**プロパティを追加する`4996`です。 選択**OK**して変更を適用します。

特定の特定のクラス ライブラリの使用廃止警告の無効にするにプリプロセッサ マクロを使用することもできます。 これらのマクロは次のとおりです。

Visual Studio でプリプロセッサ マクロを定義します。

- 開く、**プロパティ ページ**プロジェクトのダイアログ。 プロパティ ページ ダイアログを使用する方法については、次を参照してください。[プロパティ ページ](../../ide/property-pages-visual-cpp.md)です。
- 展開**構成プロパティ > C と C++ > プリプロセッサ**です。
- **プリプロセッサの定義**プロパティ、マクロ名を追加します。 **[OK]** を選んで保存し、プロジェクトをリビルドします。

マクロを定義する、特定のソース ファイル内でだけなどの追加行`#define EXAMPLE_MACRO_NAME`ヘッダー ファイルが含まれるすべての行の前にします。

## <a name="specific-c4996-messages"></a>特定の C4996 メッセージ

C4996 警告とエラーの一般的な原因のいくつか示します。

### <a name="posix-function-names"></a>POSIX 関数名

**このアイテムの POSIX 名は使用されなくなりました。代わりに、ISO C および C++ に準拠する名前を使用:** *new_name*です。 **詳細については、オンライン ヘルプを参照してください。**

Microsoft は C99 と c++ 03 の規則をグローバル関数の実装定義の名前に準拠するよう CRT の一部の POSIX 関数の名前を変更します。 元の POSIX 名のみが推奨されず、関数自体ではありません。 ほとんどの場合、標準準拠の名前を作成するため POSIX 関数名の先頭にアンダースコアが追加されています。 コンパイラは、元の関数名の廃止警告を発行し、優先の名前を示します。

この問題を修正するには、通常お勧めに推奨される関数名の代わりに使用するコードを変更します。 ただし、更新された名前は、Microsoft 固有の仕様です。 移植性のための既存の関数名を使用する必要がある場合は、これらの警告を無効にすることができます。 POSIX 関数は、元の名前の下にあるライブラリで引き続き使用できます。

これらの関数の廃止警告をオフにプリプロセッサ マクロを定義して **\_CRT\_NONSTDC\_いいえ\_警告**です。 コマンドラインでこのマクロを定義するには、オプションを含めることによって`/D_CRT_NONSTDC_NO_WARNINGS`です。


### <a name="unsafe-crt-library-functions"></a>安全でない CRT ライブラリ関数

 **この関数または変数が安全でない可能性があります。使用を検討して** *safe_version* **代わりにします。廃止予定機能を無効にするには、 \_CRT\_SECURE\_いいえ\_警告します。詳しくは、オンライン ヘルプをご覧ください。**

 Microsoft では、いくつかの CRT および C++ 標準ライブラリ関数とより安全なバージョンを優先するためのグローバル使用は推奨します。 ほとんどの場合では、非推奨の関数は、未チェックの読み取りまたは重大なセキュリティの問題につながることが、バッファーへの書き込みアクセスを許可します。 コンパイラは、これらの関数は使用されなくなったとの警告を発し、優先関数を提案します。

 この問題を解決することをお勧め関数または変数を使用する*safe_version*代わりにします。 バッファーが上書きのことはできませんまたは overread、コードで発生するが、コードの移植性の理由を変更ことはできませんのことを確認した場合は、警告を無効にすることができます。
 
 これらの関数は CRT で廃止警告をオフに定義 **\_CRT\_SECURE\_いいえ\_警告**です。 非推奨のグローバル変数に関する警告をオフにするには、次のように定義します。  **\_CRT\_SECURE\_いいえ\_警告\_GLOBALS**です。 これらの非推奨の関数とグローバル変数の詳細については、次を参照してください。 [CRT のセキュリティ機能](../../c-runtime-library/security-features-in-the-crt.md)と[安全なライブラリ: C++ 標準ライブラリ](../../standard-library/safe-libraries-cpp-standard-library.md)です。

### <a name="unsafe-standard-library-functions"></a>安全でない標準ライブラリ関数

__' std::__*function_name*__::\_未チェック\_反復子::\_Deprecate' の呼び出しに std::__*function_name***安全でない可能性がありますパラメーターを使用して、この呼び出しが渡された値が正しいことを確認する呼び出し元に依存します。この警告を無効にするには、-d を使用して\_SCL\_SECURE\_いいえ\_警告します。Visual C '反復子のチェック' を使用する方法のドキュメントを参照してください。**

特定の C++ 標準ライブラリ テンプレート関数はパラメーターが正しいことを確認しないために、デバッグ ビルドでこの警告が表示されます。 ほとんどの場合、これは反復子がありません正しく関数と共に使用する、または十分な情報がある関数で、コンテナーの境界をチェックするためです。 重大なセキュリティ ホール、プログラム内のソースがありますので、この警告はこれらの関数の使用を識別するのに役立ちます。 詳細については、「 [Checked Iterators](../../standard-library/checked-iterators.md)」を参照してください。

要素ポインターを渡す場合など、この警告がデバッグ モードで表示されます`std::copy`プレーンな配列の代わりにします。 この問題を解決するには、ライブラリが配列の範囲を確認し、範囲チェックを実行できるよう、適切に宣言された配列を使用します。

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

標準ライブラリのいくつかのアルゴリズムは、c++ 14 で「デュアル範囲」バージョンに更新されました。 デュアル範囲のバージョンを使用する場合、2 番目の範囲は、必要な範囲のチェックを提供します。

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

この例は、標準ライブラリが反復子の使用率を確認するいくつかの他の方法を示します。 ときにオンになっていない使用法が危険な可能性があります。

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

コードがバッファー オーバーランこの警告をトリガーする、標準ライブラリ関数のエラーを持たないを確認した場合は、この警告をオフにします。 これらの関数の警告をオフに、次のように定義します。  **\_SCL\_SECURE\_いいえ\_警告**です。

### <a name="checked-iterators-enabled"></a>Checked 反復子が有効になっています。

C4996 でコンパイルすると、反復子を使用しない場合にも発生することができます`_ITERATOR_DEBUG_LEVEL`1 または 2 として定義します。 デバッグ モードのビルド、既定では 2 に、製品版ビルドでは 0 に設定されます。 詳細については、「 [Checked Iterators](../../standard-library/checked-iterators.md) 」を参照してください。

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

C4996 は、セキュリティ上の理由から使用されなくなった MFC または ATL 関数を使用する場合にも発生することができます。

この問題を解決するには、強くお勧めの更新された関数を代わりに使用するコードを変更します。

これらの警告を抑制する方法については、次を参照してください。[無効](../../mfc/reference/diagnostic-services.md#afx_secure_no_warnings)です。

### <a name="obsolete-crt-functions-and-variables"></a>古い CRT 関数および変数

**この関数または変数は、新しいライブラリまたはオペレーティング システムの機能が提供されています。使用を検討して** *new_item* **代わりにします。詳しくは、オンライン ヘルプをご覧ください。**

一部のライブラリ関数およびグローバル変数は非推奨とされるため使用されていません。 これらの関数および変数は、将来のバージョンのライブラリでは削除される可能性があります。 コンパイラは、これらの項目は使用されなくなったとの警告を発行し、優先すべき代替項目を提案します。

この問題を解決するには、推奨される関数または変数を使用するコードを変更するをお勧めします。

これらの項目の廃止警告をオフに定義 **\_CRT\_OBSOLETE\_いいえ\_警告**です。 詳しくは、非推奨の関数または変数のドキュメントをご覧ください。

### <a name="marshalling-errors-in-clr-code"></a>CLR コードのマーシャリング エラー

C4996 は、CLR のマーシャ リング ライブラリを使用する場合にも発生することができます。 この場合、C4996 はエラーであり、警告ではありません。 使用すると、このエラーが発生[marshal_as](../../dotnet/marshal-as.md)を必要とする 2 つのデータ型の間で変換する、 [marshal_context クラス](../../dotnet/marshal-context-class.md)です。 マーシャ リング ライブラリが変換をサポートしていない場合にも、このエラーを受信できます。 マーシャリング ライブラリについて詳しくは、「 [Overview of Marshaling in C++](../../dotnet/overview-of-marshaling-in-cpp.md)」をご覧ください。

この例では、マーシャ リング ライブラリに変換するときにコンテキストが必要であるため C4996 が生成されます、`System::String`を`const char *`です。

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

独自のコードで非推奨属性を使用すると、不要になった特定の機能の使用を推奨するときに、呼び出し元を警告します。 この例では、非推奨の関数が宣言されている行と関数が使用されている行は、C4996 が生成されます。

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
