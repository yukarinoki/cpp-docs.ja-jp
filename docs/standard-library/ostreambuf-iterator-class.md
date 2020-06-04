---
title: ostreambuf_iterator Class
ms.date: 11/04/2016
f1_keywords:
- streambuf/std::ostreambuf_iterator
- iterator/std::ostreambuf_iterator::char_type
- iterator/std::ostreambuf_iterator::ostream_type
- iterator/std::ostreambuf_iterator::streambuf_type
- iterator/std::ostreambuf_iterator::traits_type
- iterator/std::ostreambuf_iterator::failed
helpviewer_keywords:
- std::ostreambuf_iterator [C++]
- std::ostreambuf_iterator [C++], char_type
- std::ostreambuf_iterator [C++], ostream_type
- std::ostreambuf_iterator [C++], streambuf_type
- std::ostreambuf_iterator [C++], traits_type
- std::ostreambuf_iterator [C++], failed
ms.assetid: dad1e624-2f45-4e94-8887-a885e95f9071
ms.openlocfilehash: 8e9fa10888b511ad2a500f64faf610dc7dd5ba03
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373560"
---
# <a name="ostreambuf_iterator-class"></a>ostreambuf_iterator Class

ostreambuf_iteratorクラス テンプレートは、抽出**演算子>>** を使用して出力ストリームに連続した文字要素を書き込む出力反復子オブジェクトを表します。 `ostreambuf_iterator` は、出力ストリームに挿入されるオブジェクトの型がジェネリック型ではなく文字である点が、[ostream_iterator クラス](../standard-library/ostream-iterator-class.md)のオブジェクトとは異なります。

## <a name="syntax"></a>構文

```cpp
template <class CharType = char class Traits = char_traits <CharType>>
```

### <a name="parameters"></a>パラメーター

*Chartype*\
ostreambuf_iterator の文字型を表す型。 この引数は省略可能で、既定値は**char**です。

*特徴*\
ostreambuf_iterator の文字型を表す型。 この引数は省略可能であり、既定値は `char_traits`\< *CharType>* です。

## <a name="remarks"></a>解説

ostreambuf_iterator クラスは出力反復子の要件を満たす必要があります。 アルゴリズムは `ostreambuf_iterator` を使用して出力ストリームに直接書き込むことができます。 このクラスは、生の (フォーマットされていない) I/O ストリームに文字の形式でアクセスできる低レベルのストリームの反復子を提供し、高レベルのストリーム反復子に関連付けられたバッファリングや文字変換をバイパスすることができます。

### <a name="constructors"></a>コンストラクター

|Constructor|説明|
|-|-|
|[ostreambuf_iterator](#ostreambuf_iterator_ostreambuf_iterator)|出力ストリームに文字を書き込むために初期化された `ostreambuf_iterator` を構築します。|

### <a name="typedefs"></a>Typedefs

|種類の名前。|説明|
|-|-|
|[char_type](#char_type)|`ostreambuf_iterator` の文字型を提供する型。|
|[ostream_type](#ostreambuf_iterator_ostream_type)|`ostream_iterator` のストリーム型を提供する型。|
|[streambuf_type](#streambuf_type)|`ostreambuf_iterator` のストリーム型を提供する型。|
|[traits_type](#traits_type)|`ostream_iterator` の文字特性型を提供する型。|

### <a name="member-functions"></a>メンバー関数

|メンバー関数|説明|
|-|-|
|[失敗 しました](#failed)|出力ストリーム バッファーへの挿入の失敗をテストします。|

### <a name="operators"></a>オペレーター

|演算子|説明|
|-|-|
|[演算子*](#op_star)|出力\*`i` = `x`反復式 を実装するために使用される逆参照演算子 。|
|[演算子++](#op_add_add)|操作が呼び出される前に示したものと同じオブジェクトに `ostreambuf_iterator` を返す、実質的な機能を持たないインクリメント演算子。|
|[演算子=](#op_eq)|この演算子は、関連付けられているストリーム バッファーに文字を挿入します。|

## <a name="requirements"></a>必要条件

**ヘッダー:** \<iterator>

**名前空間:** std

## <a name="ostreambuf_iteratorchar_type"></a><a name="char_type"></a>ostreambuf_iterator::char_type

`ostreambuf_iterator` の文字型を提供する型。

```cpp
typedef CharType char_type;
```

### <a name="remarks"></a>解説

この型は、テンプレート パラメーター `CharType` のシノニムです。

### <a name="example"></a>例

```cpp
// ostreambuf_iterator_char_type.cpp
// compile with: /EHsc
#include <iterator>
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;

   typedef ostreambuf_iterator<char>::char_type CHT1;
   typedef ostreambuf_iterator<char>::traits_type CHTR1;

   // ostreambuf_iterator for stream cout
   // with new line delimiter:
    ostreambuf_iterator< CHT1, CHTR1> charOutBuf ( cout );

   // Standard iterator interface for writing
   // elements to the output streambuf:
   cout << "The characters written to the output stream\n"
        << " by charOutBuf are: ";
*charOutBuf = 'O';
   charOutBuf++;
*charOutBuf = 'U';
   charOutBuf++;
*charOutBuf = 'T';
   charOutBuf++;
   cout << "." << endl;
}
/* Output:
The characters written to the output stream
by charOutBuf are: OUT.
*/
```

## <a name="ostreambuf_iteratorfailed"></a><a name="failed"></a>ostreambuf_iterator::失敗しました

出力ストリーム バッファーへの挿入の失敗をテストします。

```cpp
bool failed() const throw();
```

### <a name="return-value"></a>戻り値

これまでに出力ストリーム バッファーへの挿入が失敗していない場合は、**true**。そうでない場合は、**false**。

### <a name="remarks"></a>解説

このメンバー関数は、これまでのメンバー `operator=` の使用で、**subf**_-> `sputc` の呼び出しが **eof** を返した場合、**true** を返します。

### <a name="example"></a>例

```cpp
// ostreambuf_iterator_failed.cpp
// compile with: /EHsc
#include <iterator>
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;

   // ostreambuf_iterator for stream cout
   ostreambuf_iterator<char> charOut ( cout );

*charOut = 'a';
   charOut ++;
*charOut  = 'b';
   charOut ++;
*charOut = 'c';
   cout << " are characters output individually." << endl;

   bool b1 = charOut.failed ( );
   if (b1)
       cout << "At least one insertion failed." << endl;
   else
       cout << "No insertions failed." << endl;
}
/* Output:
abc are characters output individually.
No insertions failed.
*/
```

## <a name="ostreambuf_iteratoroperator"></a><a name="op_star"></a>ostreambuf_iterator::演算子\*

出力反復演算子\**i* = *x*を実装するために使用される非機能的な逆参照演算子。

```cpp
ostreambuf_iterator<CharType, Traits>& operator*();
```

### <a name="return-value"></a>戻り値

ostreambuf 反復子オブジェクト。

### <a name="remarks"></a>解説

この演算子は、出力反復\*演算子式 i *x* = *x*内でのみ機能し、ストリーム バッファーに文字を出力します。 ostreambuf反復器に適用され、反復器を返します。反復は**反復を**返す。 ** \***

### <a name="example"></a>例

```cpp
// ostreambuf_iterator_op_deref.cpp
// compile with: /EHsc
#include <iterator>
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;

   // ostreambuf_iterator for stream cout
   // with new line delimiter
   ostreambuf_iterator<char> charOutBuf ( cout );

   // Standard iterator interface for writing
   // elements to the output stream
   cout << "Elements written to output stream:" << endl;
*charOutBuf = 'O';
   charOutBuf++;   // no effect on iterator position
*charOutBuf = 'U';
*charOutBuf = 'T';
}
/* Output:
Elements written to output stream:
OUT
*/
```

## <a name="ostreambuf_iteratoroperator"></a><a name="op_add_add"></a>ostreambuf_iterator::演算子++

操作が呼び出される前に示したものと同じ文字に ostream 反復子を返す、実質的な機能を持たないインクリメント演算子。

```cpp
ostreambuf_iterator<CharType, Traits>& operator++();
ostreambuf_iterator<CharType, Traits>& operator++(int);
```

### <a name="return-value"></a>戻り値

最初に示された文字または、`ostreambuf_iterator`\< **CharType**, **Traits**> に変換できる実装定義のオブジェクトへの参照。

### <a name="remarks"></a>解説

この演算子は、出力反復式\**i* = i*x*を実装するために使用されます。

### <a name="example"></a>例

```cpp
// ostreambuf_iterator_op_incr.cpp
// compile with: /EHsc
#include <iterator>
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;

   // ostreambuf_iterator for stream cout
   // with new line delimiter
   ostreambuf_iterator<char> charOutBuf ( cout );

   // Standard iterator interface for writing
   // elements to the output stream
   cout << "Elements written to output stream:" << endl;
*charOutBuf = 'O';
   charOutBuf++;      // No effect on iterator position
*charOutBuf = 'U';
*charOutBuf = 'T';
}
/* Output:
Elements written to output stream:
OUT
*/
```

## <a name="ostreambuf_iteratoroperator"></a><a name="op_eq"></a>ostreambuf_iterator::演算子=

この演算子は、関連付けられているストリーム バッファーに文字を挿入します。

```cpp
ostreambuf_iterator<CharType, Traits>& operator=(CharType _Char);
```

### <a name="parameters"></a>パラメーター

*_Char*\
ストリーム バッファーに挿入する文字。

### <a name="return-value"></a>戻り値

ストリーム バッファーに挿入された文字への参照。

### <a name="remarks"></a>解説

出力ストリームへの書き込み用の出力反復式\* *i* = *x*を実装するために使用される代入演算子。

### <a name="example"></a>例

```cpp
// ostreambuf_iterator_op_assign.cpp
// compile with: /EHsc
#include <iterator>
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;

   // ostreambuf_iterator for stream cout
   // with new line delimiter
   ostreambuf_iterator<char> charOutBuf ( cout );

   // Standard iterator interface for writing
   // elements to the output stream
   cout << "Elements written to output stream:" << endl;
*charOutBuf = 'O';
   charOutBuf++;      // No effect on iterator position
*charOutBuf = 'U';
*charOutBuf = 'T';
}
/* Output:
Elements written to output stream:
OUT
*/
```

## <a name="ostreambuf_iteratorostreambuf_iterator"></a><a name="ostreambuf_iterator_ostreambuf_iterator"></a>ostreambuf_iterator::ostreambuf_iterator

出力ストリームに文字を書き込むために初期化された `ostreambuf_iterator` を構築します。

```cpp
ostreambuf_iterator(streambuf_type* strbuf) throw();
ostreambuf_iterator(ostream_type& Ostr) throw();
```

### <a name="parameters"></a>パラメーター

*ストルブフ*\
出力ストリームバッファー ポインターを初期化するために使用される出力 streambuf オブジェクト。

*Ostr*\
出力ストリームバッファー ポインターを初期化するために使用される出力ストリーム オブジェクト。

### <a name="remarks"></a>解説

最初のコンストラクターは、出力ストリーム バッファー ポインターを*strbuf*で初期化します。

2 番目のコンストラクターは、出力ストリームバッファー ポインターを `Ostr`. `rdbuf`. 格納されたポインターは null ポインターでない必要があります。

### <a name="example"></a>例

```cpp
// ostreambuf_iteratorOstreambuf_iterator.cpp
// compile with: /EHsc
#include <iterator>
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;

   // ostreambuf_iterator for stream cout
   ostreambuf_iterator<char> charOut ( cout );

*charOut = 'O';
   charOut ++;
*charOut  = 'U';
   charOut ++;
*charOut = 'T';
   cout << " are characters output individually." << endl;

   ostreambuf_iterator<char> strOut ( cout );
   string str = "These characters are being written to the output stream.\n ";
   copy ( str.begin ( ), str. end ( ), strOut );
}
/* Output:
OUT are characters output individually.
These characters are being written to the output stream.
*/
```

## <a name="ostreambuf_iteratorostream_type"></a><a name="ostreambuf_iterator_ostream_type"></a>ostreambuf_iterator::ostream_type

`ostream_iterator` のストリーム型を提供する型。

```cpp
typedef basicOstream<CharType, Traits> ostream_type;
```

### <a name="remarks"></a>解説

型は`basicOstream`\<**CharType**、特性の同義語**です**>

### <a name="example"></a>例

`ostream_type` を宣言して使用する方法の例については、[ostreambuf_iterator](#ostreambuf_iterator_ostreambuf_iterator) に関するセクションをご覧ください。

## <a name="ostreambuf_iteratorstreambuf_type"></a><a name="streambuf_type"></a>ostreambuf_iterator::streambuf_type

`ostreambuf_iterator` のストリーム型を提供する型。

```cpp
typedef basic_streambuf<CharType, Traits> streambuf_type;
```

### <a name="remarks"></a>解説

型は`basic_streambuf`\<**CharType**の同義語であり、文字**型**char に特化`streambuf`すると I/O バッファーのストリーム クラスである**traits**>。

### <a name="example"></a>例

`streambuf_type` を宣言して使用する方法の例については、[ostreambuf_iterator](#ostreambuf_iterator_ostreambuf_iterator) に関するセクションをご覧ください。

## <a name="ostreambuf_iteratortraits_type"></a><a name="traits_type"></a>ostreambuf_iterator::traits_type

`ostream_iterator` の文字特性型を提供する型。

```cpp
typedef Traits traits_type;
```

### <a name="remarks"></a>解説

この型は、テンプレート パラメーター `Traits` のシノニムです。

### <a name="example"></a>例

```cpp
// ostreambuf_iterator_traits_type.cpp
// compile with: /EHsc
#include <iterator>
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;

   typedef ostreambuf_iterator<char>::char_type CHT1;
   typedef ostreambuf_iterator<char>::traits_type CHTR1;

   // ostreambuf_iterator for stream cout
   // with new line delimiter:
    ostreambuf_iterator< CHT1, CHTR1> charOutBuf ( cout );

   // Standard iterator interface for writing
   // elements to the output streambuf:
   cout << "The characters written to the output stream\n"
        << " by charOutBuf are: ";
*charOutBuf = 'O';
   charOutBuf++;
*charOutBuf = 'U';
   charOutBuf++;
*charOutBuf = 'T';
   charOutBuf++;
   cout << "." << endl;
}
/* Output:
The characters written to the output stream
by charOutBuf are: OUT.
*/
```

## <a name="see-also"></a>関連項目

[\<反復器>](../standard-library/iterator.md)\
[C++ 標準ライブラリにおけるスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[C++ 標準ライブラリ リファレンス](../standard-library/cpp-standard-library-reference.md)
