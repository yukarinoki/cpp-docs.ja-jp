---
title: 文字列リテラルと文字リテラル (C++) |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- R
dev_langs:
- C++
helpviewer_keywords:
- L constant
- escape sequences
- Null strings, null-terminated strings
- literal strings, C++
- Null strings
- string literals, syntax
- string literals
- literal strings
- strings [C++], string literals
- NULL, character constant
- wide characters, strings
ms.assetid: 61de8f6f-2714-4e7b-86b6-a3f885d3b9df
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 79ec82ec00e912d597cfeda608e1b77cf08ab4e8
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/02/2018
ms.locfileid: "39466944"
---
# <a name="string-and-character-literals--c"></a>文字列リテラルと文字リテラル (C++)
C++ はさまざまな文字列と文字型をサポートし、これらの型のリテラル値を表す方法を提供しています。 ソース コードでは、文字セットを使用して文字リテラルと文字列リテラルの内容を表現します。 ユニバーサル文字名とエスケープ文字を使用すると、基本ソース文字セットのみを使用してあらゆる文字列を表現できます。 未加工文字列リテラルを使用すると、エスケープ文字の使用を避けられるとともに、全種類の文字列リテラルを表すことができます。 余分な構築または変換手順を実行することなく、std::string リテラルを作成することもできます。  
  
```cpp  
#include <string>  
using namespace std::string_literals; // enables s-suffix for std::string literals  
  
int main()  
{  
    // Character literals  
    auto c0 =   'A'; // char  
    auto c1 = u8'A'; // char  
    auto c2 =  L'A'; // wchar_t  
    auto c3 =  u'A'; // char16_t  
    auto c4 =  U'A'; // char32_t  
  
    // String literals  
    auto s0 =   "hello"; // const char*  
    auto s1 = u8"hello"; // const char*, encoded as UTF-8  
    auto s2 =  L"hello"; // const wchar_t*  
    auto s3 =  u"hello"; // const char16_t*, encoded as UTF-16  
    auto s4 =  U"hello"; // const char32_t*, encoded as UTF-32  
  
    // Raw string literals containing unescaped \ and "  
    auto R0 =   R"("Hello \ world")"; // const char*  
    auto R1 = u8R"("Hello \ world")"; // const char*, encoded as UTF-8  
    auto R2 =  LR"("Hello \ world")"; // const wchar_t*  
    auto R3 =  uR"("Hello \ world")"; // const char16_t*, encoded as UTF-16  
    auto R4 =  UR"("Hello \ world")"; // const char32_t*, encoded as UTF-32  
  
    // Combining string literals with standard s-suffix  
    auto S0 =   "hello"s; // std::string  
    auto S1 = u8"hello"s; // std::string  
    auto S2 =  L"hello"s; // std::wstring  
    auto S3 =  u"hello"s; // std::u16string  
    auto S4 =  U"hello"s; // std::u32string  
  
    // Combining raw string literals with standard s-suffix  
    auto S5 =   R"("Hello \ world")"s; // std::string from a raw const char*  
    auto S6 = u8R"("Hello \ world")"s; // std::string from a raw const char*, encoded as UTF-8  
    auto S7 =  LR"("Hello \ world")"s; // std::wstring from a raw const wchar_t*  
    auto S8 =  uR"("Hello \ world")"s; // std::u16string from a raw const char16_t*, encoded as UTF-16  
    auto S9 =  UR"("Hello \ world")"s; // std::u32string from a raw const char32_t*, encoded as UTF-32  
}  
```  
  
 文字列リテラルは、プレフィックスを省略することも、 `u8`、 `L`、 `u`、または  `U` プレフィックスを使用することもできます。これらは、それぞれ、ナロー文字 (単一バイトまたは複数バイト)、UTF-8、ワイド文字 (UCS-2 または UTF-16)、UTF-16、UTF-32 エンコーディングを表します。 未加工文字列リテラルは、上記のエンコーディングの未加工バージョンとして `R`、 `u8R`、 `LR`、 `uR` 、 `UR` プレフィックスを使用できます。  一時的なまたは静的な std::string の値を作成するには、文字列リテラルまたは未加工文字列リテラルを `s` サフィックスと一緒に使用できます。 詳しくは、後述する「文字列リテラル」をご覧ください。 詳細については、基本ソース文字セット、ユニバーサル文字名、および拡張コードページからの文字を使用して、ソース コードを参照してください[文字セット](../cpp/character-sets.md)します。  
  
## <a name="character-literals"></a>文字リテラル  
 *文字リテラル* は、定数文字で構成されます。 これは単一引用符で囲んだ文字によって表されます。 文字リテラルの 5 つの種類があります。  
  
-   型の通常の文字リテラル**char**など `'a'`  
  
-   型の utf-8 文字リテラル**char**など `u8'a'`  
  
-   `wchar_t`型のワイド文字リテラル。たとえば `L'a'`  
  
-   型の utf-16 文字リテラル`char16_t`など `u'a'`  
  
-   型の utf-32 文字リテラル`char32_t`など `U'a'`  
  
 文字リテラルに使用する文字、予約文字の円記号を除く、任意の文字があります ('\\')、単一引用符 (')、または改行します。 予約文字は、エスケープ シーケンスを使用して指定することができます。 型が文字を保持するのに十分な大きさであれば、文字はユニバーサル文字名を使用して指定することができます。  
  
### <a name="encoding"></a>エンコード  
 文字リテラルが異なる方法でエンコードされた、プレフィックスのベースします。  
  
-   プレフィックスのないリテラル文字は、通常の文字リテラルです。 通常の文字をリテラル値を 1 つの文字を含むシーケンスをエスケープまたは、実行文字セットで表現できるユニバーサル文字名が、実行文字セット エンコードの数値に相当する値。 1 つ以上の文字、エスケープ シーケンス、またはユニバーサル文字名を含む通常文字リテラルは、*多文字リテラル*します。 多文字リテラル、または、実行文字セットで表現できない通常の文字リテラルは、条件付きでサポートが int 型とその値は実装定義です。  
  
-   L のプレフィックスで始まる文字リテラルは、ワイド文字リテラルです。 1 つの文字、エスケープ シーケンス、またはユニバーサル文字名を含むワイド文字リテラルの値が文字リテラルで表現されていない場合を除き、設定実行ワイド文字のエンコードの数値に等しい値が、実行ワイド文字は、この場合、値は、実装定義に設定します。 複数の文字、エスケープ シーケンス、またはユニバーサル文字名を含むワイド文字リテラルの値は、実装で定義されます。  
  
-   U8 プレフィックスで始まる文字リテラルは、utf-8 文字リテラルです。 Utf-8 文字リテラルの値を 1 つの文字を含むシーケンスをエスケープまたは (C0 コントロールと基本的なラテン文字に対応する 1 つの utf-8 コード単位で表すことができる場合、ユニバーサル文字名がその ISO 10646 のコード ポイント値と等しい値を持つUnicode ブロックの場合)。 値は、1 つの utf-8 コード単位で表すことができない、プログラムは正しくない形式をします。 Utf-8 文字リテラルの 1 つ以上の文字、エスケープ シーケンス、またはユニバーサル文字名を格納しているが、不適切な形式です。  
  
-   U プレフィックスで始まる文字リテラルは、utf-16 の文字リテラルです。 Utf-16 文字をリテラル値を 1 つの文字を含むシーケンスをエスケープまたは (基本的な多言語配置平面に対応する 1 つの utf-16 コード単位で表すことができる場合、ユニバーサル文字名は ISO 10646 のコード ポイント値に等しい値を持つ). 値は、1 つの utf-16 コード単位で表すことができない、プログラムは正しくない形式をします。 Utf-16 文字が 1 つ以上の文字、エスケープ シーケンス、またはユニバーサル文字名を含むリテラルは、不適切な形式です。  
  
-   U プレフィックスで始まる文字リテラルは、utf-32 文字リテラルです。 ユニバーサル文字名は、その ISO 10646 のコード ポイント値と等しい値を持つまたは utf-32 文字リテラルの値を 1 つの文字を含むシーケンスをエスケープします。 Utf-8 文字リテラルの 1 つ以上の文字、エスケープ シーケンス、またはユニバーサル文字名を格納しているが、不適切な形式です。  
  
###  <a name="bkmk_Escape"></a> エスケープ シーケンス  
 エスケープ シーケンスには、単純、8 進数、16 進数という 3 つの種類があります。 エスケープ シーケンスとして次のいずれかを使用できます。  
  
|値|エスケープ シーケンス|[値]|エスケープ シーケンス|  
|-----------|---------------------|-----------|---------------------|  
|改行|\n|円記号|\\\|  
|水平タブ|\t|疑問符|? または \\?|  
|垂直タブ|\v|単一引用符 (')|\\'|  
|バックスペース|\b|二重引用符 (")|\\"|  
|キャリッジ リターン|\r|null 文字|\0|  
|フォーム フィード|\f|8 進数|\ooo|  
|警告 (ベル)|\a|16 進数|\xhhh|  
  
 次のコードでは、通常の文字リテラルを使用するエスケープ文字の例を示します。 同じエスケープ シーケンス構文は、他の文字のリテラル型に有効です。  
  
```cpp  
#include <iostream>  
using namespace std;  
  
int main() {  
    char newline = '\n';  
    char tab = '\t';  
    char backspace = '\b';  
    char backslash = '\\';  
    char nullChar = '\0';  
  
    cout << "Newline character: " << newline << "ending" << endl; // Newline character:  
                                                                  //  ending  
    cout << "Tab character: " << tab << "ending" << endl; // Tab character : ending  
    cout << "Backspace character: " << backspace << "ending" << endl; // Backspace character : ending  
    cout << "Backslash character: " << backslash << "ending" << endl; // Backslash character : \ending  
    cout << "Null character: " << nullChar << "ending" << endl; //Null character:  ending  
}  
```  
  
 **Microsoft 固有の仕様**  
  
 (プレフィックスのないもの) から通常の文字をリテラル値を作成するには、コンパイラは、文字または 32 ビット整数で指定した 8 ビット値に単一引用符の間の文字のシーケンスに変換します。 リテラル内の複数の文字に対応するバイトが、必要に応じて、上位から下位に入力されます。 作成する、 **char**値をコンパイラは下位バイトを取得します。 作成する、 **wchar_t**または`char16_t`値、コンパイラは下位ワードを取得します。 割り当てられたバイトまたはワードを上回るビットが設定された場合、コンパイラは結果が切り捨てられることを警告します。  
  
```cpp  
char c0    = 'abcd';    // C4305, C4309, truncates to 'd'  
wchar_t w0 = 'abcd';    // C4305, C4309, truncates to '\x6364'  
```  
  
 8 進数のエスケープ シーケンスは、円記号を前置した最大 3 桁の 8 進数のシーケンスです。 見かけ上 4 桁以上を含む 8 進数のエスケープ シーケンスの動作は、3 桁の 8 進数シーケンスの後ろに文字としての桁が続くものとして扱われます。これは、想定外の結果につながる可能性があります。 例えば:  
  
```cpp  
char c1 = '\100';   // '@'  
char c2 = '\1000';  // C4305, C4309, truncates to '0'   
```  
  
 見かけ上 8 進数以外の文字を含むエスケープ シーケンスは、最後の 8 進数文字までは 8 進数シーケンスとして評価され、その後に残りの文字が続くものと見なされます。 例えば:  
  
```cpp  
char c3 = '\009';   // '9'  
char c4 = '\089';   // C4305, C4309, truncates to '9'  
char c5 = '\qrs';   // C4129, C4305, C4309, truncates to 's'  
```  
  
 16 進数のエスケープ シーケンスは、円記号と `x`を前置した 16 進数のシーケンスです。 16 進数の数字を含まないエスケープ シーケンスでは、"16 進型リテラルには、少なくとも 1 桁の 16 進数が必要です" という C2153 コンパイラ エラーが発生します。 先行 0 は無視されます。 見かけ上 16 進数文字と 16 進数以外の文字を含むエスケープ シーケンスは、最後の 16 進数文字までは 16 進数のエスケープ シーケンスとして評価され、その後に 16 進数以外の文字が続くものと見なされます。   通常または u8 プレフィックス付き文字リテラル、最上位の 16 進数の値は 0 xff までです。 L プレフィックス付きまたは u プレフィックス付きワイド文字リテラルでは、最大の 16 進値は 0xFFFF です。 U プレフィックス付きワイド文字リテラルでは、最大の 16 進値は 0xFFFFFFFF です。  
  
```cpp  
char c6 = '\x0050'; // 'P'  
char c7 = '\x0pqr'; // C4305, C4309, truncates to 'r'  
```  
  
 `L` プレフィックス付きワイド文字リテラルに複数の文字が含まれている場合は、最初の文字から値が取得されます。 通常と同じ文字リテラルの動作とは異なり、それに続く文字が無視されます。  
  
```cpp  
wchar_t w1 = L'\100';   // L'@'  
wchar_t w2 = L'\1000';  // C4066 L'@', 0 ignored   
wchar_t w3 = L'\009';   // C4066 L'\0', 9 ignored  
wchar_t w4 = L'\089';   // C4066 L'\0', 89 ignored  
wchar_t w5 = L'\qrs';   // C4129, C4066 L'q' escape, rs ignored  
wchar_t w6 = L'\x0050'; // L'P'  
wchar_t w7 = L'\x0pqr'; // C4066 L'\0', pqr ignored  
```  
  
 **Microsoft 固有の仕様はここまで**  
  
 円記号 (\\) 行の末尾には、行連結文字です。 円記号が文字リテラルとして表示されるようにするには、円記号を 2 つ並べて (`\\`) 入力する必要があります。 行連結文字について詳しくは、「 [Phases of Translation](../preprocessor/phases-of-translation.md)」をご覧ください。  
  
###  <a name="bkmk_UCN"></a> ユニバーサル文字名  
 文字リテラルとネイティブ (未加工ではない) 文字列リテラルでは、ユニバーサル文字名であらゆる文字を表すことができます。  ユニバーサル文字名は、プレフィックス \U の後ろに 8 桁の Unicode コード ポイントが続く形式、または、プレフィックス \u の後ろに 4 桁の Unicode コード ポイントが続く形式です。 正しい形式のユニバーサル文字名を作成するには、それぞれ、8 桁または 4 桁のすべてが存在する必要があります。  
  
```cpp  
char u1 = 'A';          // 'A'  
char u2 = '\101';       // octal, 'A'   
char u3 = '\x41';       // hexadecimal, 'A'  
char u4 = '\u0041';     // \u UCN 'A'  
char u5 = '\U00000041'; // \U UCN 'A'  
```  
  
 **サロゲート ペア**  
  
 ユニバーサル文字名は、サロゲート コード ポイントの範囲 D800 ～ DFFF 内の値をエンコードできません。 Unicode サロゲート ペアの場合は、 `\UNNNNNNNN`を使用してユニバーサル文字名を指定します。ここで、NNNNNNNN は文字用の 8 桁のコード ポイントです。 コンパイラは、必要に応じて、サロゲート ペアを生成します。  
  
 C++03 では、ユニバーサル文字名で表現できたのは文字のサブセットに過ぎず、許可されていた一部のユニバーサル文字名は実際には正しい Unicode 文字を表していませんでした。 これは、C++11 の標準で修正されました。 C++11 では、文字リテラルと文字列リテラルの両方と識別子でユニバーサル文字名を使用できます。  ユニバーサル文字名の詳細については、次を参照してください。[文字セット](../cpp/character-sets.md)します。 Unicode について詳しくは、「 [Unicode](http://msdn.microsoft.com/library/dd374081\(v=vs.85\).aspx)」をご覧ください。 サロゲート ペアについて詳しくは、「 [サロゲート ペアと補助文字](http://msdn.microsoft.com/library/dd374069\(v=vs.85\).aspx)」をご覧ください。  
  
## <a name="string-literals"></a>文字列リテラル  
 文字列リテラルは文字のシーケンスを表し、その全体が、null で終わる文字列を形成します。 文字列は二重引用符で囲む必要があります。 文字列リテラルの種類は次のとおりです。  
  
### <a name="narrow-string-literals"></a>ナロー文字列リテラル  
 ナロー文字列リテラルは型のプレフィックスなしの二重引用符で区切られ、null で終わる配列`const char[n]`n はバイトの配列の長さです。 ナロー文字列リテラルには、二重引用符 (`"`)、円記号 (`\`)、または改行文字を除く、任意のグラフィック文字を含めることができます。 ナロー文字列リテラルには、上記のエスケープ シーケンスと、1 バイトに収まるユニバーサル文字名を含めることもできます。  
  
```cpp  
const char *narrow = "abcd";  
  
// represents the string: yes\no  
const char *escaped = "yes\\no";  
```  
  
#### <a name="utf-8-encoded-strings"></a>UTF-8 でエンコードされた文字列  
  
 Utf-8 でエンコードされた文字列が型の u8 プレフィックス付き、二重引用符で区切られ、null で終わる配列`const char[n]`n はエンコードされたバイト配列の長さです。 u8 プレフィックス付き文字列リテラルには、二重引用符 (`"`)、円記号 (`\`)、または改行文字を除く、任意のグラフィック文字を含めることができます。 u8 プレフィックス付き文字列リテラルには、上記のエスケープ シーケンスと、任意のユニバーサル文字名を含めることもできます。  
  
```cpp  
const char* str1 = u8"Hello World";  
const char* str2 = u8"\U0001F607 is O:-)";  
```  
  
### <a name="wide-string-literals"></a>ワイド文字列リテラル  
 ワイド文字列リテラルは定数の null で終わる配列**wchar_t**が付いている '`L`'、二重引用符 (")、円記号を除く任意のグラフィック文字が含まれています (\\)、または改行文字。 ワイド文字列リテラルには、上記のエスケープ シーケンスと、任意のユニバーサル文字名を含めることができます。  
  
```cpp  
const wchar_t* wide = L"zyxw";  
const wchar_t* newline = L"hello\ngoodbye";  
```  
  
#### <a name="char16t-and-char32t-c11"></a>char16_t および char32_t (C++11)  
  
 C++11 では、移植可能な `char16_t` (16 ビット Unicode) および `char32_t` (32 ビット Unicode) 文字型が導入されています。  
  
```cpp  
auto s3 = u"hello"; // const char16_t*  
auto s4 = U"hello"; // const char32_t*  
```  
  
### <a name="raw-string-literals-c11"></a>未加工の文字列リテラル (C++11)  
 未加工文字列リテラルが null で終わる配列: 任意の文字型-、二重引用符 (")、円記号を含む、任意のグラフィック文字を格納している (\\)、または改行文字。 未加工文字列リテラルは、文字クラスを使用する正規表現や、HTML 文字列、XML 文字列でよく使用されます。 例については、次の記事を参照してください: [c++ 11 に関する Bjarne Stroustrup の FAQ](http://go.microsoft.com/fwlink/p/?linkid=401172)します。  
  
```cpp  
// represents the string: An unescaped \ character  
const char* raw_narrow = R"(An unescaped \ character)";  
const wchar_t* raw_wide = LR"(An unescaped \ character)";  
const char*       raw_utf8  = u8R"(An unescaped \ character)";  
const char16_t* raw_utf16 = uR"(An unescaped \ character)";  
const char32_t* raw_utf32 = UR"(An unescaped \ character)";  
```  
  
 区切り記号は、16 文字以下のユーザー定義のシーケンスです。未加工の文字列リテラルを囲む左かっこの直前および右かっこの直後に配置されます。  たとえば、 `R"abc(Hello"\()abc"` では、区切り記号シーケンスが `abc` で、文字列コンテンツが `Hello"\(`です。 区切り記号を使用することで、二重引用符とかっこの両方を含む未加工の文字列の曖昧さを解消できます。 次のコードではコンパイラ エラーが発生します。  
  
```cpp  
// meant to represent the string: )"  
const char* bad_parens = R"()")";  // error C2059  
```  
  
 しかし、区切り文字を使用することで、エラーは解決します。  
  
```cpp  
const char* good_parens = R"xyz()")xyz";  
```  
  
 次のソースでは、改行 (エスケープ文字ではない) を含む未加工リテラルを作成できます。  
  
```cpp  
// represents the string: hello  
//goodbye  
const wchar_t* newline = LR"(hello  
goodbye)";  
```  
  
### <a name="stdstring-literals-c14"></a>std::string リテラル (C++14)  
 std::string リテラルは、( `s` サフィックスが付いた) "xyx"s として表されるユーザー定義リテラルの標準ライブラリの実装です (下記参照)。 このような種類の文字列リテラルにより、指定されるプレフィックスによって型 std::string、std::wstring、std::u32string、または std::u16string の一時オブジェクトが生成されます。 プレフィックスを使用しないと、上記のように、std::string が生成されます。 L"xyz"s は std::wstring を生成します。 u"xyz"s は [std::u16string](../standard-library/string-typedefs.md#u16string)を生成し、U"xyz"s は [std::u32string](../standard-library/string-typedefs.md#u32string)を生成します。  
  
```cpp  
//#include <string>  
//using namespace std::string_literals;  
string str{ "hello"s };  
string str2{ u8"Hello World" };  
wstring str3{ L"hello"s };  
u16string str4{ u"hello"s };  
u32string str5{ U"hello"s };  
```  
  
 s サフィックスは、未加工の文字列リテラルにも使用できます。  
  
```cpp  
u32string str6{ UR"(She said "hello.")"s };  
```  
  
 std::string リテラルは、名前空間で定義されている`std::literals::string_literals`で、\<文字列 > ヘッダー ファイル。 `std::literals::string_literals`、および `std::literals` はいずれも [インライン名前空間](../cpp/namespaces-cpp.md)として宣言されているため、 `std::literals::string_literals` は名前空間 `std`に直接属しているかのように処理されます。  
  
### <a name="size-of-string-literals"></a>文字列リテラルのサイズ  
 ANSI char の\*文字列とその他の 1 バイト エンコーディング (いない utf-8) 文字列リテラルのサイズをバイト単位では、終端の null 文字の 1 を足した数の文字の数。 その他すべての文字列型の場合、サイズと文字数に厳密な関係はありません。 UTF-8 は最大 4 つの char 型の要素を使用していくつかの *コード単位*をエンコードします。UTF-16 でエンコードされた char16_t や wchar_t では、1 つの *コード単位*をエンコードするために 2 つの要素 (合計 4 バイト) を使用できます。   この例では、ワイド文字列リテラルのサイズがバイト単位で表示されます。  
  
```cpp  
const wchar_t* str = L"Hello!";  
const size_t byteSize = (wcslen(str) + 1) * sizeof(wchar_t);  
```  
  
 注意して`strlen()`と`wcslen()`サイズが文字列型の要素のサイズと等しく、終端の null 文字のサイズが含まれていません 1 バイト文字を\*wchar_t に 2 つのバイトの文字列\*または char16_t\*。文字列、および char32_t は 4 バイト\*文字列。  
  
 文字列リテラルの最大長は 65535 バイトです。 この制限は、ナローとワイドの両方の文字列リテラルに適用されます。  
  
### <a name="modifying-string-literals"></a>文字列リテラルの変更  
 文字列リテラル (std:string リテラルは含まない) は定数であるため、変更を試みると (たとえば str[2] = 'A') コンパイラ エラーが発生します。  
  
 **Microsoft 固有の仕様**  
  
 非定数へのポインターを初期化するために、文字列リテラルを使用する Visual C で**char**または**wchar_t**します。 この操作は C99 コードでは使用できますが、C++98 では非推奨とされており、C++11 では削除されています。 文字列を変更すると、この例のようにアクセス違反が発生します。  
  
```cpp  
wchar_t* str = L"hello";  
str[2] = L'a'; // run-time error: access violation  
```  
  
 リテラル文字列を変換を non_const 文字ポインターを設定するときにエラーを生成するコンパイラが発生することができます、 [/Zc:strictStrings (文字列リテラルの型変換の無効化)](../build/reference/zc-strictstrings-disable-string-literal-type-conversion.md)コンパイラ オプション。 標準に準拠した移植可能なコードの場合にこれをお勧めします。 また、使用することをお勧め、**自動**正しい (const) 型に解決されるため、文字列をリテラル初期化ポインターを宣言するキーワード。 たとえば、このコード例ではコンパイル時に文字列リテラルへの書き込みの試みがキャッチされます。  
  
```cpp  
auto str = L"hello";  
str[2] = L'a'; // C3892: you cannot assign to a variable that is const.  
```  
  
 場合によっては、実行可能ファイルの領域を節約するために、同じ文字列リテラルをプールできます。 文字列リテラルのプールでは、各参照が文字列リテラルの各インスタンスを指すのではなく、コンパイラにより、特定の文字列リテラルへのすべての参照がメモリ内の同じ場所を指します。 文字列プールを有効にするには、 [/GF](../build/reference/gf-eliminate-duplicate-strings.md) コンパイラ オプションを使用します。  
  
 **End Microsoft Specific**  
  
### <a name="concatenating-adjacent-string-literals"></a>隣接する文字列リテラルの連結  
 隣接するワイド文字列リテラルまたはナロー文字列リテラルは連結されます。 次の宣言は、  
  
```cpp  
char str[] = "12" "34";  
```  
  
 次の宣言と同じです。  
  
```cpp  
char atr[] = "1234";  
```  
  
 次の宣言も同じです。  
  
```cpp  
char atr[] =  "12\  
34";  
```  
  
 埋め込みの 16 進数エスケープ コードを使用して文字列リテラルを指定すると、予期しない結果が生じることがあります。 次の例では、ASCII 文字 5 の後に文字列 f、i、v、および e を含む文字列リテラルを作成しようとしています。  
  
```cpp  
"\x05five"  
```  
  
 実際の結果は、16 進数値 5F (アンダースコアの ASCII コード) に文字列 i、v、および e が続きます。 次のいずれかの方法で正しい結果を得られます。  
  
```cpp  
"\005five"     // Use octal literal.  
"\x05" "five"  // Use string splicing.  
```  
  
 std::string リテラルは std::string 型であるため、 [basic_string](../standard-library/basic-string-class.md) 型に定義された + 演算子と連結できます。 隣接する文字列リテラルと同じ方法で連結することもできます。 いずれの場合も、次のように文字列のエンコードとサフィックスは一致していなければなりません。  
  
```cpp  
auto x1 = "hello" " " " world"; // OK  
auto x2 = U"hello" " " L"world"; // C2308: disagree on prefix  
auto x3 = u8"hello" " "s u8"world"s; // OK, agree on prefixes and suffixes  
auto x4 = u8"hello" " "s u8"world"z; // C3688, disagree on suffixes  
```  
  
### <a name="string-literals-with-universal-character-names"></a>ユニバーサル文字名を持つ文字列リテラル  
 ネイティブ (未加工でない) 文字列リテラルは、ユニバーサル文字名が文字列型の 1 つ以上の文字としてエンコードできる限り、ユニバーサル文字名を使用して任意の文字を表すことができます。  たとえば、拡張文字を表すユニバーサル文字名は、ANSI コード ページ内のナロー文字列でエンコードすることはできませんが、一部のマルチバイト コード ページ内のナロー文字列、UTF-8 文字列、またはワイド文字列でエンコードすることができます。 C++ 11 で Unicode のサポートは、char16_t によって拡張された\*と char32_t\*文字列型。  
  
```cpp  
// ASCII smiling face  
const char*     s1 = ":-)";    
  
// UTF-16 (on Windows) encoded WINKING FACE (U+1F609)  
const wchar_t*  s2 = L"😉 = \U0001F609 is ;-)";    
  
// UTF-8  encoded SMILING FACE WITH HALO (U+1F607)  
const char*     s3 = u8"😇 = \U0001F607 is O:-)";  
  
// UTF-16 encoded SMILING FACE WITH OPEN MOUTH (U+1F603)  
const char16_t* s4 = u"😃 = \U0001F603 is :-D";  
  
// UTF-32 encoded SMILING FACE WITH SUNGLASSES (U+1F60E)  
const char32_t* s5 = U"😎 = \U0001F60E is B-)";  
```  
  
## <a name="see-also"></a>関連項目  
 [文字セット](../cpp/character-sets.md)   
 [数値、ブール値、およびポインターのリテラル](../cpp/numeric-boolean-and-pointer-literals-cpp.md)   
 [ユーザー定義リテラル](../cpp/user-defined-literals-cpp.md)