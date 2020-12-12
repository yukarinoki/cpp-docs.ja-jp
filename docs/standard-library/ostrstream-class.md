---
description: '詳細情報: ostrstream クラス'
title: ostrstream クラス
ms.date: 11/04/2016
f1_keywords:
- strstream/std::ostrstream::freeze
- strstream/std::ostrstream::pcount
- strstream/std::ostrstream::rdbuf
- strstream/std::ostrstream::str
helpviewer_keywords:
- std::ostrstream [C++], freeze
- std::ostrstream [C++], pcount
- std::ostrstream [C++], rdbuf
- std::ostrstream [C++], str
ms.assetid: e2e34679-b266-4728-a8e1-8eda5d400e46
ms.openlocfilehash: 9966f044d48aa762d681bafcfc22441f7124c9a8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97305144"
---
# <a name="ostrstream-class"></a>ostrstream クラス

クラス [strstreambuf](../standard-library/strstreambuf-class.md) のストリーム バッファーへの、要素とエンコードされたオブジェクトの挿入を制御するオブジェクトを表します。

## <a name="syntax"></a>構文

```cpp
class ostrstream : public ostream
```

## <a name="remarks"></a>解説

このオブジェクトは、クラス `strstreambuf` のオブジェクトを格納します。

> [!NOTE]
> このクラスは非推奨とされます。 代わりに、[ostringstream](../standard-library/sstream-typedefs.md#ostringstream) または [wostringstream](../standard-library/sstream-typedefs.md#wostringstream) を使用することを検討します。

### <a name="constructors"></a>コンストラクター

|コンストラクター|説明|
|-|-|
|[ostrstream](#ostrstream)|`ostrstream` 型のオブジェクトを構築します。|

### <a name="member-functions"></a>メンバー関数

|メンバー関数|説明|
|-|-|
|[あせん](#freeze)|ストリーム バッファーの操作により、ストリーム バッファーを使用不可にします。|
|[pcount](#pcount)|被制御シーケンスに書き込まれる要素の数を返します。|
|[rdbuf](#rdbuf)|ストリームの関連付けられた `strstreambuf` オブジェクトへのポインターを返します。|
|[str](#str)|[freeze](../standard-library/strstreambuf-class.md#freeze) を呼び出し、被制御シーケンスの先頭へのポインターを返します。|

## <a name="requirements"></a>要件

**ヘッダー:**\<strstream>

**名前空間:** std

## <a name="ostrstreamfreeze"></a><a name="freeze"></a> ostrstream:: freeze

ストリーム バッファーの操作により、ストリーム バッファーを使用不可にします。

```cpp
void freeze(bool _Freezeit = true);
```

### <a name="parameters"></a>パラメーター

*_Freezeit*\
**`bool`** ストリームを固定するかどうかを示す。

### <a name="remarks"></a>解説

このメンバー関数は、 [rdbuf](#rdbuf)  ->  [freeze](../standard-library/strstreambuf-class.md#freeze)(_ *Freezeit*) を呼び出します。

### <a name="example"></a>例

の使用例については、「 [strstream:: freeze](../standard-library/strstreambuf-class.md#freeze) 」を参照してください `freeze` 。

## <a name="ostrstreamostrstream"></a><a name="ostrstream"></a> ostrstream:: ostrstream

`ostrstream` 型のオブジェクトを構築します。

```cpp
ostrstream();

ostrstream(char* ptr,
    streamsize count,
    ios_base::openmode _Mode = ios_base::out);
```

### <a name="parameters"></a>パラメーター

*ポインター*\
バッファーです。

*数*\
バッファーのサイズ (バイト単位)。

*_Mode*\
バッファーの入出力モード。 詳細については、[ios_base::openmode](../standard-library/ios-base-class.md#openmode) をご覧ください。

### <a name="remarks"></a>解説

どちらのコンストラクターも、 [ostream](../standard-library/ostream-typedefs.md#ostream)(**sb**) を呼び出すことによって基底クラスを初期化します。ここで、 `sb` は [strstreambuf](../standard-library/strstreambuf-class.md)クラスの格納されているオブジェクトです。 最初のコンストラクターは、を `sb` 呼び出すことによっても初期化し `strstreambuf` ます。 2 番目のコンストラクターは、次のどちらかの方法で基本クラスを初期化します。

- `_Mode`  &  **Ios_base:: app**= = 0 の場合は、 `ptr` 要素の配列の最初の要素を指定する必要があり、 `count` コンストラクターは `strstreambuf` ( `ptr` , `count` ,) を呼び出し `ptr` ます。

- それ以外の場合、は、 `ptr` 最初の要素がによって指定された C 文字列を含む count 要素の最初の要素を指定する必要があり `ptr` ます。また、コンストラクターは `strstreambuf` ( `ptr` , `count` , `ptr`  +  `strlen` ( `ptr` )) を呼び出します。

## <a name="ostrstreampcount"></a><a name="pcount"></a> ostrstream::p 数

被制御シーケンスに書き込まれる要素の数を返します。

```cpp
streamsize pcount() const;
```

### <a name="return-value"></a>戻り値

被制御シーケンスに書き込まれる要素の数。

### <a name="remarks"></a>解説

このメンバー関数は、 [rdbuf](#rdbuf)  ->  [pcount](../standard-library/strstreambuf-class.md#pcount)を返します。

### <a name="example"></a>例

`pcount` の使用例は、[strstream::pcount](../standard-library/strstreambuf-class.md#pcount) をご覧ください。

## <a name="ostrstreamrdbuf"></a><a name="rdbuf"></a> ostrstream:: rdbuf

ストリームの関連付けられた strstreambuf オブジェクトへのポインターを返します。

```cpp
strstreambuf *rdbuf() const
```

### <a name="return-value"></a>戻り値

ストリームの関連付けられた strstreambuf オブジェクトへのポインター。

### <a name="remarks"></a>解説

このメンバー関数は、型の格納されているストリームバッファーのアドレスを `pointer` [strstreambuf](../standard-library/strstreambuf-class.md)に返します。

### <a name="example"></a>例

`rdbuf` の使用例は、[strstreambuf::pcount](../standard-library/strstreambuf-class.md#pcount) をご覧ください。

## <a name="ostrstreamstr"></a><a name="str"></a> ostrstream:: str

[freeze](../standard-library/strstreambuf-class.md#freeze) を呼び出し、被制御シーケンスの先頭へのポインターを返します。

```cpp
char *str();
```

### <a name="return-value"></a>戻り値

被制御シーケンスの先頭へのポインター。

### <a name="remarks"></a>解説

このメンバー関数は、 [rdbuf](#rdbuf)  ->  [str](../standard-library/strstreambuf-class.md#str)を返します。

### <a name="example"></a>例

を使用するサンプルについては、「 [strstream:: str](../standard-library/strstreambuf-class.md#str) 」を参照してください `str` 。

## <a name="see-also"></a>関連項目

[ostream](../standard-library/ostream-typedefs.md#ostream)\
[C++ 標準ライブラリのスレッドセーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[iostream プログラミング](../standard-library/iostream-programming.md)\
[iostreams の規則](../standard-library/iostreams-conventions.md)
