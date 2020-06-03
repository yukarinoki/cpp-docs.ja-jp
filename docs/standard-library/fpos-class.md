---
title: fpos クラス
ms.date: 03/27/2019
f1_keywords:
- iosfwd/std::fpos
- iosfwd/std::fpos::seekpos
- iosfwd/std::fpos::state
- iosfwd/std::fpos::operator streamoff
helpviewer_keywords:
- std::fpos [C++]
- std::fpos [C++], seekpos
- std::fpos [C++], state
ms.assetid: ffd0827c-fa34-47f4-b10e-5cb707fcde47
ms.openlocfilehash: 7d60a31e69e8a1ad82086f715cac6dde064d1fac
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81359201"
---
# <a name="fpos-class"></a>fpos クラス

クラス テンプレートは、任意のストリーム内の任意のファイル位置インジケーターを復元するために必要なすべての情報を格納できるオブジェクトを記述します。 fpos\< **St**> クラスのオブジェクトには、実質的に 2 個以上のメンバー オブジェクトが格納されます。

- [streamoff](../standard-library/ios-typedefs.md#streamoff) 型のバイト オフセット。

- 通常`St``mbstate_t`、クラス basic_filebufのオブジェクトで使用する変換状態です。

[basic_filebuf](../standard-library/basic-filebuf-class.md) クラスのオブジェクトで使用するために、`fpos_t` 型の任意のファイル位置も格納できます。 ただし、ファイル サイズが制限された環境では、`streamoff` と `fpos_t` が区別されずに使用される場合があります。 状態依存のエンコードを使用したストリームがない環境では、実際に `mbstate_t` が使用されていない場合があります。 したがって、格納されるメンバー オブジェクトの数が異なる場合があります。

## <a name="syntax"></a>構文

```cpp
template <class Statetype>
class fpos
```

### <a name="parameters"></a>パラメーター

*ステートタイプ*\
状態情報。

### <a name="constructors"></a>コンストラクター

|Constructor|説明|
|-|-|
|[fpos](#fpos)|ストリーム内の位置 (オフセット) に関する情報を格納するオブジェクトを作成します。|

### <a name="member-functions"></a>メンバー関数

|メンバー関数|説明|
|-|-|
|[seekpos](#seekpos)|C++ 標準ライブラリのみによって内部的に使用されます。 このメソッドをコードから呼び出さないでください。|
|[状態](#state)|変換状態を設定または返します。|

### <a name="operators"></a>オペレーター

|演算子|説明|
|-|-|
|[演算子!=](#op_neq)|ファイル位置インジケーターが等しくないかどうかをテストします。|
|[演算子+](#op_add)|ファイル位置インジケーターをインクリメントします。|
|[演算子 +=](#op_add_eq)|ファイル位置インジケーターをインクリメントします。|
|[演算子-](#operator-)|ファイル位置インジケーターをデクリメントします。|
|[演算子-=](#operator-_eq)|ファイル位置インジケーターをデクリメントします。|
|[演算子==](#op_eq_eq)|ファイル位置インジケーターが等しいかどうかをテストします。|
|[operator streamoff](#op_streamoff)|`fpos` 型のオブジェクトを `streamoff` 型のオブジェクトにキャストします。|

## <a name="requirements"></a>必要条件

**ヘッダー:** \<ios>

**名前空間:** std

## <a name="fposfpos"></a><a name="fpos"></a>フポス::fpos

ストリーム内の位置 (オフセット) に関する情報を格納するオブジェクトを作成します。

```cpp
fpos(streamoff _Off = 0);

fpos(Statetype _State, fpos_t _Filepos);
```

### <a name="parameters"></a>パラメーター

*_Off*\
ストリームへのオフセット。

*_state*\
`fpos` オブジェクトの開始状態。

*_Filepos*\
ストリームへのオフセット。

### <a name="remarks"></a>解説

最初のコンストラクターは、オフセット *_Off*ファイルの先頭を基準にして、初期変換状態 (重要な場合) を格納します。 *_Off*が -1 の場合、結果のオブジェクトは無効なストリーム位置を表します。

2 番目のコンストラクターは、ゼロ オフセットを格納し、オブジェクト*は _State。*

## <a name="fposoperator"></a><a name="op_neq"></a>fpos::演算子!

ファイル位置インジケーターが等しくないかどうかをテストします。

```cpp
bool operator!=(const fpos<Statetype>& right) const;
```

### <a name="parameters"></a>パラメーター

*そうです*\
比較するファイル位置インジケーター。

### <a name="return-value"></a>戻り値

ファイル位置インジケーターが等しくない場合は **true**。それ以外の場合は **false**。

### <a name="remarks"></a>解説

このメンバー関数は、`!(*this == right)` を返します。

### <a name="example"></a>例

```cpp
// fpos_op_neq.cpp
// compile with: /EHsc
#include <fstream>
#include <iostream>

int main( )
{
   using namespace std;

   fpos<int> pos1, pos2;
   ifstream file;
   char c;

   // Compare two fpos object
   if ( pos1 != pos2 )
      cout << "File position pos1 and pos2 are not equal" << endl;
   else
      cout << "File position pos1 and pos2 are equal" << endl;

   file.open( "fpos_op_neq.txt" );
   file.seekg( 0 );   // Goes to a zero-based position in the file
   pos1 = file.tellg( );
   file.get( c);
   cout << c << endl;

   // Increment pos1
   pos1 += 1;
   file.get( c );
   cout << c << endl;

   pos1 = file.tellg( ) - fpos<int>( 2);
   file.seekg( pos1 );
   file.get( c );
   cout << c << endl;

   // Increment pos1
   pos1 = pos1 + fpos<int>( 1 );
   file.get(c);
   cout << c << endl;

   pos1 -= fpos<int>( 2 );
   file.seekg( pos1 );
   file.get( c );
   cout << c << endl;

   file.close( );
}
```

## <a name="fposoperator"></a><a name="op_add"></a>fpos::オペレーター+

ファイル位置インジケーターをインクリメントします。

```cpp
fpos<Statetype> operator+(streamoff _Off) const;
```

### <a name="parameters"></a>パラメーター

*_Off*\
ファイル位置インジケーターをインクリメントするオフセット。

### <a name="return-value"></a>戻り値

ファイル内の位置。

### <a name="remarks"></a>解説

このメンバー関数は、**fpos(\*this) +=** `_Off` を返します。

### <a name="example"></a>例

`operator+` の使用例については、[operator!=](#op_neq) を参照してください。

## <a name="fposoperator"></a><a name="op_add_eq"></a>fpos::演算子+=

ファイル位置インジケーターをインクリメントします。

```cpp
fpos<Statetype>& operator+=(streamoff _Off);
```

### <a name="parameters"></a>パラメーター

*_Off*\
ファイル位置インジケーターをインクリメントするオフセット。

### <a name="return-value"></a>戻り値

ファイル内の位置。

### <a name="remarks"></a>解説

メンバー関数は、格納されているオフセット メンバー オブジェクトに *_Off*を追加し、**\*この値を**返します。 ファイル内の位置を特定する場合、結果は一般に状態依存エンコーディングを持たないバイナリ ストリームについてのみ有効です。

### <a name="example"></a>例

`operator+=` の使用例については、[operator!=](#op_neq) を参照してください。

## <a name="fposoperator-"></a><a name="operator-"></a>fpos::演算子-

ファイル位置インジケーターをデクリメントします。

```cpp
streamoff operator-(const fpos<Statetype>& right) const;

fpos<Statetype> operator-(streamoff _Off) const;
```

### <a name="parameters"></a>パラメーター

*そうです*\
ファイルの位置。

*_Off*\
ストリームのオフセット。

### <a name="return-value"></a>戻り値

最初のメンバー関数は `(streamoff)*this - (streamoff) right` を返します。 2 番目のメンバー関数は `fpos(*this) -= _Off` を返します。

### <a name="example"></a>例

`operator-` の使用例については、[operator!=](#op_neq) を参照してください。

## <a name="fposoperator-"></a><a name="operator-_eq"></a>fpos::演算子- =

ファイル位置インジケーターをデクリメントします。

```cpp
fpos<Statetype>& operator-=(streamoff _Off);
```

### <a name="parameters"></a>パラメーター

*_Off*\
ストリームのオフセット。

### <a name="return-value"></a>戻り値

このメンバー関数は、`fpos(*this) -= _Off` を返します。

### <a name="remarks"></a>解説

ファイル内の位置を特定する場合、結果は一般に状態依存エンコーディングを持たないバイナリ ストリームについてのみ有効です。

### <a name="example"></a>例

`operator-=` の使用例については、[operator!=](#op_neq) を参照してください。

## <a name="fposoperator"></a><a name="op_eq_eq"></a>fpos::演算子==

ファイル位置インジケーターが等しいかどうかをテストします。

```cpp
bool operator==(const fpos<Statetype>& right) const;
```

### <a name="parameters"></a>パラメーター

*そうです*\
比較するファイル位置インジケーター。

### <a name="return-value"></a>戻り値

ファイル位置インジケーターが等しい場合は **true**。それ以外の場合は **false**。

### <a name="remarks"></a>解説

このメンバー関数は、`(streamoff)*this == (streamoff)right` を返します。

### <a name="example"></a>例

`operator+=` の使用例については、[operator!=](#op_neq) を参照してください。

## <a name="fposoperator-streamoff"></a><a name="op_streamoff"></a>fpos::オペレーターストリームオフ

`fpos` 型のオブジェクトを `streamoff` 型のオブジェクトにキャストします。

```cpp
operator streamoff() const;
```

### <a name="remarks"></a>解説

このメンバー関数は、格納されたオフセット メンバー オブジェクト、および `fpos_t` メンバー オブジェクトの一部として格納された追加のオフセットを返します。

### <a name="example"></a>例

```cpp
// fpos_op_streampos.cpp
// compile with: /EHsc
#include <ios>
#include <iostream>
#include <fstream>

int main( )
{
   using namespace std;
   streamoff s;
   ofstream file( "rdbuf.txt");

   fpos<mbstate_t> f = file.tellp( );
   // Is equivalent to ..
   // streampos f = file.tellp( );
   s = f;
   cout << s << endl;
}
```

```Output
0
```

## <a name="fposseekpos"></a><a name="seekpos"></a>フポス::シーポス

このメソッドは、C++ 標準ライブラリのみによって内部的に使用されます。 このメソッドをコードから呼び出さないでください。

```cpp
fpos_t seekpos() const;
```

## <a name="fposstate"></a><a name="state"></a>fpos::状態

変換状態を設定または返します。

```cpp
Statetype state() const;

void state(Statetype _State);
```

### <a name="parameters"></a>パラメーター

*_state*\
新しい変換状態。

### <a name="return-value"></a>戻り値

変換状態。

### <a name="remarks"></a>解説

最初のメンバー関数は、メンバー オブジェクトに`St`格納されている値を返します。 2 番目のメンバー関数は *、メンバー*オブジェクトに_Stateを`St`格納します。

### <a name="example"></a>例

```cpp
// fpos_state.cpp
// compile with: /EHsc
#include <ios>
#include <iostream>
#include <fstream>

int main() {
   using namespace std;
   streamoff s;
   ifstream file( "fpos_state.txt" );

   fpos<mbstate_t> f = file.tellg( );
   char ch;
   while ( !file.eof( ) )
      file.get( ch );
   s = f;
   cout << f.state( ) << endl;
   f.state( 9 );
   cout << f.state( ) << endl;
}
```

## <a name="see-also"></a>関連項目

[C++ 標準ライブラリにおけるスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[iostream プログラミング](../standard-library/iostream-programming.md)\
[ioストリームの規約](../standard-library/iostreams-conventions.md)
