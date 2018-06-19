---
title: fpos クラス | Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- iosfwd/std::fpos
- iosfwd/std::fpos::seekpos
- iosfwd/std::fpos::state
- iosfwd/std::fpos::operator streamoff
dev_langs:
- C++
helpviewer_keywords:
- std::fpos [C++]
- std::fpos [C++], seekpos
- std::fpos [C++], state
ms.assetid: ffd0827c-fa34-47f4-b10e-5cb707fcde47
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 15c7d7babe1112bbfcc80485d54d5a4a005b4dfc
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
ms.locfileid: "33848636"
---
# <a name="fpos-class"></a>fpos クラス

このテンプレート クラスは、システム内の任意のファイル位置インジケーターを復元するために必要なすべての情報を格納できるオブジェクトを表します。 fpos\<**St**> クラスのオブジェクトには、実質的に 2 個以上のメンバー オブジェクトが格納されます。

- [streamoff](../standard-library/ios-typedefs.md#streamoff) 型のバイト オフセット。

- basic_filebuf クラスのオブジェクトで使用するための **St** 型の変換状態 (通常は `mbstate_t`)。

[basic_filebuf](../standard-library/basic-filebuf-class.md) クラスのオブジェクトで使用するために、`fpos_t` 型の任意のファイル位置も格納できます。 ただし、ファイル サイズが制限された環境では、`streamoff` と `fpos_t` が区別されずに使用される場合があります。 状態依存のエンコードを使用したストリームがない環境では、実際に `mbstate_t` が使用されていない場合があります。 したがって、格納されるメンバー オブジェクトの数が異なる場合があります。

## <a name="syntax"></a>構文

```cpp
template <class Statetype>
class fpos
```

### <a name="parameters"></a>パラメーター

*Statetype*状態情報。

### <a name="constructors"></a>コンストラクター

|コンストラクター|説明|
|-|-|
|[fpos](#fpos)|ストリーム内の位置 (オフセット) に関する情報を格納するオブジェクトを作成します。|

### <a name="member-functions"></a>メンバー関数

|メンバー関数|説明|
|-|-|
|[seekpos](#seekpos)|C++ 標準ライブラリのみによって内部的に使用されます。 このメソッドをコードから呼び出さないでください。|
|[state](#state)|変換状態を設定または返します。|

### <a name="operators"></a>演算子

|演算子|説明|
|-|-|
|[operator!=](#op_neq)|ファイル位置インジケーターが等しくないかどうかをテストします。|
|[operator+](#op_add)|ファイル位置インジケーターをインクリメントします。|
|[operator+=](#op_add_eq)|ファイル位置インジケーターをインクリメントします。|
|[operator-](#operator-)|ファイル位置インジケーターをデクリメントします。|
|[operator-=](#operator-_eq)|ファイル位置インジケーターをデクリメントします。|
|[operator==](#op_eq_eq)|ファイル位置インジケーターが等しいかどうかをテストします。|
|[operator streamoff](#op_streamoff)|`fpos` 型のオブジェクトを `streamoff` 型のオブジェクトにキャストします。|

## <a name="requirements"></a>要件

**ヘッダー:** \<ios>

**名前空間:** std

## <a name="fpos"></a>  fpos::fpos

ストリーム内の位置 (オフセット) に関する情報を格納するオブジェクトを作成します。

```cpp
fpos(streamoff _Off = 0);

fpos(Statetype _State, fpos_t _Filepos);
```

### <a name="parameters"></a>パラメーター

`_Off` ストリームへのオフセット。

`_State` 最初の状態、`fpos`オブジェクト。

*_Filepos*ストリームへのオフセット。

### <a name="remarks"></a>コメント

最初のコンストラクターは、ファイルの先頭に対するオフセット `_Off` を初期の変換状態で格納します (必要に応じて)。 `_Off` が -1 の場合、結果として得られるオブジェクトは無効なストリーム位置を表します。

2 番目のコンストラクターは、ゼロ オフセットとオブジェクト `_State` を格納します。

## <a name="op_neq"></a>  fpos::operator!=

ファイル位置インジケーターが等しくないかどうかをテストします。

```cpp
bool operator!=(const fpos<Statetype>& right) const;
```

### <a name="parameters"></a>パラメーター

`right` 比較するファイル位置インジケーター。

### <a name="return-value"></a>戻り値

ファイル位置インジケーターが等しくない場合は **true**。それ以外の場合は **false**。

### <a name="remarks"></a>コメント

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

## <a name="op_add"></a>  fpos::operator+

ファイル位置インジケーターをインクリメントします。

```cpp
fpos<Statetype> operator+(streamoff _Off) const;
```

### <a name="parameters"></a>パラメーター

`_Off` ファイル位置インジケーターをインクリメントするオフセットです。

### <a name="return-value"></a>戻り値

ファイル内の位置。

### <a name="remarks"></a>コメント

このメンバー関数は、**fpos(\*this) +=** `_Off` を返します。

### <a name="example"></a>例

`operator+` の使用例については、[operator!=](#op_neq) を参照してください。

## <a name="op_add_eq"></a>  fpos::operator+=

ファイル位置インジケーターをインクリメントします。

```cpp
fpos<Statetype>& operator+=(streamoff _Off);
```

### <a name="parameters"></a>パラメーター

`_Off` ファイル位置インジケーターをインクリメントするオフセットです。

### <a name="return-value"></a>戻り値

ファイル内の位置。

### <a name="remarks"></a>コメント

メンバー関数は、格納されたオフセット メンバー オブジェクトに `_Off` を追加し、**\*this** を返します。 ファイル内の位置を特定する場合、結果は一般に状態依存エンコーディングを持たないバイナリ ストリームについてのみ有効です。

### <a name="example"></a>例

`operator+=` の使用例については、[operator!=](#op_neq) を参照してください。

## <a name="fpos__operator-"></a>  fpos::operator-

ファイル位置インジケーターをデクリメントします。

```cpp
streamoff operator-(const fpos<Statetype>& right) const;

fpos<Statetype> operator-(streamoff _Off) const;
```

### <a name="parameters"></a>パラメーター

`right` ファイルの位置。

`_Off` ストリームのオフセットです。

### <a name="return-value"></a>戻り値

最初のメンバー関数は `(streamoff)*this - (streamoff) right` を返します。 2 番目のメンバー関数は `fpos(*this) -= _Off` を返します。

### <a name="example"></a>例

`operator-` の使用例については、[operator!=](#op_neq) を参照してください。

## <a name="fpos__operator-_eq"></a>  fpos::operator-=

ファイル位置インジケーターをデクリメントします。

```cpp
fpos<Statetype>& operator-=(streamoff _Off);
```

### <a name="parameters"></a>パラメーター

`_Off` ストリームのオフセットです。

### <a name="return-value"></a>戻り値

このメンバー関数は、`fpos(*this) -= _Off` を返します。

### <a name="remarks"></a>コメント

ファイル内の位置を特定する場合、結果は一般に状態依存エンコーディングを持たないバイナリ ストリームについてのみ有効です。

### <a name="example"></a>例

`operator-=` の使用例については、[operator!=](#op_neq) を参照してください。

## <a name="op_eq_eq"></a>  fpos::operator==

ファイル位置インジケーターが等しいかどうかをテストします。

```cpp
bool operator==(const fpos<Statetype>& right) const;
```

### <a name="parameters"></a>パラメーター

`right` 比較するファイル位置インジケーター。

### <a name="return-value"></a>戻り値

ファイル位置インジケーターが等しい場合は **true**。それ以外の場合は **false**。

### <a name="remarks"></a>コメント

このメンバー関数は、`(streamoff)*this == (streamoff)right` を返します。

### <a name="example"></a>例

`operator+=` の使用例については、[operator!=](#op_neq) を参照してください。

## <a name="op_streamoff"></a>  fpos::operator streamoff

`fpos` 型のオブジェクトを `streamoff` 型のオブジェクトにキャストします。

```cpp
operator streamoff() const;
```

### <a name="remarks"></a>コメント

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

## <a name="seekpos"></a>  fpos::seekpos

このメソッドは、C++ 標準ライブラリのみによって内部的に使用されます。 このメソッドをコードから呼び出さないでください。

```cpp
fpos_t seekpos() const;
```

## <a name="state"></a>  fpos::state

変換状態を設定または返します。

```cpp
Statetype state() const;

void state(Statetype _State);
```

### <a name="parameters"></a>パラメーター

`_State` 新しい変換状態。

### <a name="return-value"></a>戻り値

変換状態。

### <a name="remarks"></a>コメント

最初のメンバー関数は、**St** メンバー オブジェクトに格納されている値を返します。 2 番目のメンバー関数は、`_State`St**メンバー オブジェクトに** を格納します。

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

[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[iostream プログラミング](../standard-library/iostream-programming.md)<br/>
[iostreams の規則](../standard-library/iostreams-conventions.md)<br/>
