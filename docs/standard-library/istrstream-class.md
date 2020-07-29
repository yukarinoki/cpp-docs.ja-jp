---
title: istrstream クラス
ms.date: 11/04/2016
f1_keywords:
- strstream/std::istrstream::rdbuf
- strstream/std::istrstream::str
helpviewer_keywords:
- istrstream class
ms.assetid: c2d41c75-bd2c-4437-bd77-5939ce1b97af
ms.openlocfilehash: 37118772f7cefd6f380ceb01908da55500ee7ab5
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87228233"
---
# <a name="istrstream-class"></a>istrstream クラス

クラス [strstreambuf](../standard-library/strstreambuf-class.md) のストリーム バッファーからの、要素とエンコードされたオブジェクトの抽出を制御するオブジェクトを表します。

## <a name="syntax"></a>構文

```cpp
class istrstream : public istream
```

## <a name="remarks"></a>解説

このオブジェクトは、クラス `strstreambuf` のオブジェクトを格納します。

> [!NOTE]
> このクラスは非推奨とされます。 代わりに、[istringstream](../standard-library/sstream-typedefs.md#istringstream) または [wistringstream](../standard-library/sstream-typedefs.md#wistringstream) を使用することを検討してください。

### <a name="constructors"></a>コンストラクター

|コンストラクター|[説明]|
|-|-|
|[istrstream](#istrstream)|`istrstream` 型のオブジェクトを構築します。|

### <a name="member-functions"></a>メンバー関数

|メンバー関数|説明|
|-|-|
|[rdbuf](#rdbuf)|ストリームの関連付けられた `strstreambuf` オブジェクトへのポインターを返します。|
|[引数](#str)|[freeze](../standard-library/strstreambuf-class.md#freeze) を呼び出し、被制御シーケンスの先頭へのポインターを返します。|

## <a name="requirements"></a>必要条件

**ヘッダー:**\<strstream>

**名前空間:** std

## <a name="istrstreamistrstream"></a><a name="istrstream"></a>istrstream:: istrstream

`istrstream` 型のオブジェクトを構築します。

```cpp
explicit istrstream(
    const char* ptr);

explicit istrstream(
    char* ptr);

istrstream(
    const char* ptr,
    streamsize count);

istrstream(
    char* ptr,
    int count);
```

### <a name="parameters"></a>パラメーター

*数*\
バッファーの長さ (*ptr*)。

*ポインター*\
バッファーが初期化されているコンテンツ。

### <a name="remarks"></a>解説

すべてのコンストラクターは、 [istream](../standard-library/istream-typedefs.md#istream)(**sb**) を呼び出すことによって基底クラスを初期化します。ここで、 `sb` は[strstreambuf](../standard-library/strstreambuf-class.md)クラスの格納されているオブジェクトです。 最初の2つのコンストラクターは、を `sb` 呼び出すことによっても初期化し `strstreambuf( ( const char *) ptr, 0 )` ます。 残りの2つのコンストラクターは、を代わりに呼び出し `strstreambuf( ( const char *) ptr, count )` ます。

## <a name="istrstreamrdbuf"></a><a name="rdbuf"></a>istrstream:: rdbuf

ストリームの関連付けられた strstreambuf オブジェクトへのポインターを返します。

```cpp
strstreambuf *rdbuf() const
```

### <a name="return-value"></a>戻り値

ストリームの関連付けられた strstreambuf オブジェクトへのポインター。

### <a name="remarks"></a>解説

このメンバー関数は、ポインター型の格納されたストリーム バッファーのアドレスを [strstreambuf](../standard-library/strstreambuf-class.md) に返します。

### <a name="example"></a>例

`rdbuf` の使用例は、[strstreambuf::pcount](../standard-library/strstreambuf-class.md#pcount) をご覧ください。

## <a name="istrstreamstr"></a><a name="str"></a>istrstream:: str

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

[istream](../standard-library/istream-typedefs.md#istream)\
[C++ 標準ライブラリのスレッドセーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[iostream プログラミング](../standard-library/iostream-programming.md)\
[iostreams の規則](../standard-library/iostreams-conventions.md)
