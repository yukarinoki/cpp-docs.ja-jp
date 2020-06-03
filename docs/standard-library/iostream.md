---
title: '&lt;iostream&gt;'
ms.date: 09/20/2017
f1_keywords:
- <iostream>
- iostream/std::cerr
- iostream/std::cin
- iostream/std::clog
- iostream/std::cout
- iostream/std::wcerr
- iostream/std::wcin
- iostream/std::wclog
- iostream/std::wcout
helpviewer_keywords:
- iostream header
ms.assetid: de5d39e1-7e77-4b55-bcd1-7c77b41515c8
ms.openlocfilehash: 03afb777dc3926284cf0dc625e94a716ecdf5413
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375343"
---
# <a name="ltiostreamgt"></a>&lt;iostream&gt;

標準ストリームに対する読み取りと書き込みを制御するオブジェクトを宣言します。 このインクルードは、多くの場合、C++ プログラムからの入出力を行う必要がある唯一のヘッダーです。

## <a name="syntax"></a>構文

```cpp
#include <iostream>
```

> [!NOTE]
> iostream \<> ライブラリでは`#include <ios>`、 `#include <streambuf>` `#include <istream>`、 `#include <ostream>` 、および ステートメントが使用されます。

## <a name="remarks"></a>解説

このオブジェクトは、次の 2 つのグループに分類されます。

- [cin](#cin)、 [cout](#cout)、 [cerr](#cerr)、および[詰まり](#clog)はバイト指向であり、従来のバイト・アット・ア・タイム転送を行います。

- [wcin](#wcin)、[wcout](#wcout)、[wcerr](#wcerr)、および [wclog](#wclog) はワイド指向で、プログラムが内部で操作するワイド文字に翻訳したり、ワイド文字から翻訳したりします。

標準入力など、ストリームに対して特定の操作を行うと、同じストリームで異なる方向の操作を実行することはできません。 したがって、たとえば[cin](#cin)と[wcin](#wcin)の両方でプログラムを同じ意味で動作させることはできません。

このヘッダーで宣言されたすべてのオブジェクトは、iostream>を含む\<翻訳単位で、定義する静的オブジェクトの前に構築されていると仮定して、独特のプロパティを共有します。 同様に、これらのオブジェクトは、定義した静的オブジェクトのデストラクターの前に破棄されないと仮定できます。 (ただし、出力ストリームはプログラムの終了時にフラッシュされます。したがって、プログラムの起動前とプログラム終了後に、標準ストリームの読み取りまたは書き込みを安全に行うことができます。

しかし、この保証は普遍的ではありません。 静的コンストラクターは、別の翻訳単位で、関数を呼び出す場合があります。 呼び出された関数は、変換単位が静的構築に含まれる順序が不確かであることを考えると、このヘッダーで宣言されたオブジェクトが構築されたとは考えられません。 このようなコンテキストでこれらのオブジェクトを使用するには、最初に [ios_base::Init](../standard-library/ios-base-class.md#init) クラスのオブジェクトを構築します。

### <a name="global-stream-objects"></a>グローバル ストリーム オブジェクト

|||
|-|-|
|[cerr](#cerr)|`cerr` グローバル ストリームを指定します。|
|[Cin](#cin)|`cin` グローバル ストリームを指定します。|
|[詰まら せる](#clog)|`clog` グローバル ストリームを指定します。|
|[cout](#cout)|`cout` グローバル ストリームを指定します。|
|[wcerr](#wcerr)|`wcerr` グローバル ストリームを指定します。|
|[ウチン](#wcin)|`wcin` グローバル ストリームを指定します。|
|[wclog](#wclog)|`wclog` グローバル ストリームを指定します。|
|[wcout](#wcout)|`wcout` グローバル ストリームを指定します。|

### <a name="cerr"></a><a name="cerr"></a>サール

オブジェクト `cerr` は、\<cstdio> で宣言されたオブジェクト `stderr` に関連付けられているストリーム バッファーへの出力を制御します。

```cpp
extern ostream cerr;
```

#### <a name="return-value"></a>戻り値

[ostream](../standard-library/ostream-typedefs.md#ostream) オブジェクト。

#### <a name="remarks"></a>解説

このオブジェクトは、バイト ストリームとして、標準エラー出力へのバッファリングされていない挿入を制御します。 オブジェクトが構築された時点で、式 `cerr.`[flags](../standard-library/ios-base-class.md#flags) `&` [unitbuf](../standard-library/ios-functions.md#unitbuf) は 0 以外で、`cerr.tie() == &cout` になります。

#### <a name="example"></a>例

```cpp
// iostream_cerr.cpp
// compile with: /EHsc
#include <iostream>
#include <fstream>

using namespace std;

void TestWide( )
{
   int i = 0;
   wcout << L"Enter a number: ";
   wcin >> i;
   wcerr << L"test for wcerr" << endl;
   wclog << L"test for wclog" << endl;
}

int main( )
{
   int i = 0;
   cout << "Enter a number: ";
   cin >> i;
   cerr << "test for cerr" << endl;
   clog << "test for clog" << endl;
   TestWide( );
}
```

### <a name="cin"></a><a name="cin"></a>Cin

`cin` グローバル ストリームを指定します。

```cpp
extern istream cin;
```

#### <a name="return-value"></a>戻り値

[istream](../standard-library/istream-typedefs.md#istream) オブジェクト。

#### <a name="remarks"></a>解説

オブジェクトは、バイト ストリームとして標準入力からの抽出を制御します。 オブジェクトが構築されると、`cin.`[tie](../standard-library/basic-ios-class.md#tie) の呼び出しは `&`[cout](#cout) を返します。

#### <a name="example"></a>例

この例では、`cin`非数字文字に渡ったときにストリームに fail ビットを設定します。 プログラムは、失敗ビットをクリアし、ストリームから無効な文字を取り除いて続行します。

```cpp
// iostream_cin.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;

int main()
{
   int x;
   cout << "enter choice:";
   cin >> x;
   while (x < 1 || x > 4)
   {
      cout << "Invalid choice, try again:";
      cin >> x;
      // not a numeric character, probably
      // clear the failure and pull off the non-numeric character
      if (cin.fail())
      {
         cin.clear();
         char c;
         cin >> c;
      }
   }
}
```

```Output
2
```

### <a name="clog"></a><a name="clog"></a>詰まら せる

`clog` グローバル ストリームを指定します。

```cpp
extern ostream clog;
```

#### <a name="return-value"></a>戻り値

[ostream](../standard-library/ostream-typedefs.md#ostream) オブジェクト。

#### <a name="remarks"></a>解説

このオブジェクトは、バイト ストリームとして、標準エラー出力へのバッファリングされている挿入を制御します。

#### <a name="example"></a>例

`clog` の使用例については、「[cerr](#cerr)」をご覧ください。

### <a name="cout"></a><a name="cout"></a>Cout

`cout` グローバル ストリームを指定します。

```cpp
extern ostream cout;
```

#### <a name="return-value"></a>戻り値

[ostream](../standard-library/ostream-typedefs.md#ostream) オブジェクト。

#### <a name="remarks"></a>解説

このオブジェクトは、バイト ストリームとして、標準出力への挿入を制御します。

#### <a name="example"></a>例

`cout` の使用例については、「[cerr](#cerr)」をご覧ください。

### <a name="wcerr"></a><a name="wcerr"></a>ウサー

`wcerr` グローバル ストリームを指定します。

```cpp
extern wostream wcerr;
```

#### <a name="return-value"></a>戻り値

[wostream](../standard-library/ostream-typedefs.md#wostream) オブジェクト。

#### <a name="remarks"></a>解説

このオブジェクトは、ワイド ストリームとして、標準エラー出力へのバッファリングされていない挿入を制御します。 オブジェクトが構築された時点で、式 `wcerr.`[flags](../standard-library/ios-base-class.md#flags) `&` [unitbuf](../standard-library/ios-functions.md#unitbuf) は 0 以外になります。

#### <a name="example"></a>例

`wcerr` の使用例については、「[cerr](#cerr)」をご覧ください。

### <a name="wcin"></a><a name="wcin"></a>ウチン

`wcin` グローバル ストリームを指定します。

```cpp
extern wistream wcin;
```

#### <a name="return-value"></a>戻り値

[wistream](../standard-library/istream-typedefs.md#wistream) オブジェクト。

#### <a name="remarks"></a>解説

オブジェクトは、ワイド ストリームとして標準入力からの抽出を制御します。 オブジェクトが構築されると、`wcin.`[tie](../standard-library/basic-ios-class.md#tie) の呼び出しは `&`[wcout](#wcout) を返します。

#### <a name="example"></a>例

`wcin` の使用例については、「[cerr](#cerr)」をご覧ください。

### <a name="wclog"></a><a name="wclog"></a>wclog

`wclog` グローバル ストリームを指定します。

```cpp
extern wostream wclog;
```

#### <a name="return-value"></a>戻り値

[wostream](../standard-library/ostream-typedefs.md#wostream) オブジェクト。

#### <a name="remarks"></a>解説

このオブジェクトは、ワイド ストリームとして、標準エラー出力へのバッファリングされている挿入を制御します。

#### <a name="example"></a>例

`wclog` の使用例については、「[cerr](#cerr)」をご覧ください。

### <a name="wcout"></a><a name="wcout"></a>wcout

`wcout` グローバル ストリームを指定します。

```cpp
extern wostream wcout;
```

#### <a name="return-value"></a>戻り値

[wostream](../standard-library/ostream-typedefs.md#wostream) オブジェクト。

#### <a name="remarks"></a>解説

このオブジェクトは、ワイド ストリームとして、標準出力への挿入を制御します。

#### <a name="example"></a>例

`wcout` の使用例については、「[cerr](#cerr)」をご覧ください。

`wcout` ステートメントの `CString` インスタンスは、次の例に示されているように `const wchar_t*` にキャストする必要があります。

```cpp
CString cs("meow");

wcout <<(const wchar_t*) cs <<endl;
```

詳細については、「[CString の基本操作](../atl-mfc-shared/basic-cstring-operations.md)」をご覧ください。

## <a name="see-also"></a>関連項目

[ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)\
[C++ 標準ライブラリにおけるスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[iostream プログラミング](../standard-library/iostream-programming.md)\
[ioストリームの規約](../standard-library/iostreams-conventions.md)
