---
title: istrstream クラス
ms.date: 11/04/2016
f1_keywords:
- strstream/std::istrstream::rdbuf
- strstream/std::istrstream::str
helpviewer_keywords:
- istrstream class
ms.assetid: c2d41c75-bd2c-4437-bd77-5939ce1b97af
ms.openlocfilehash: d548a8c2c47a5a345be725afdedb47524344f720
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81337522"
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

|Constructor|説明|
|-|-|
|[istrstream](#istrstream)|`istrstream` 型のオブジェクトを構築します。|

### <a name="member-functions"></a>メンバー関数

|メンバー関数|説明|
|-|-|
|[rdbuf](#rdbuf)|ストリームの関連付けられた `strstreambuf` オブジェクトへのポインターを返します。|
|[Str](#str)|[freeze](../standard-library/strstreambuf-class.md#freeze) を呼び出し、被制御シーケンスの先頭へのポインターを返します。|

## <a name="requirements"></a>必要条件

**ヘッダー:** \<strstream>

**名前空間:** std

## <a name="istrstreamistrstream"></a><a name="istrstream"></a>イズトルストリーム::イズトルストリーム

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

*カウント*\
バッファの長さ (*ptr*)

*Ptr*\
バッファーが初期化されているコンテンツ。

### <a name="remarks"></a>解説

すべてのコンストラクタは、 クラス[strstreambuf](../standard-library/strstreambuf-class.md)の格納されたオブジェクト`sb`である[istream](../standard-library/istream-typedefs.md#istream)(**sb**) を呼び出すことによって基本クラスを初期化します。 最初の 2 つのコンストラクター`sb`も、 `strstreambuf`( ( `ptr` **const** `char` \*) 、 0 を呼び出して初期化します。 残りの 2 つのコンストラクター`strstreambuf`は、 ( **const** `char` *) `ptr`, を`count`呼び出します。

## <a name="istrstreamrdbuf"></a><a name="rdbuf"></a>イズトルストリーム::rdbuf

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

## <a name="istrstreamstr"></a><a name="str"></a>イズトルストリーム::str

[freeze](../standard-library/strstreambuf-class.md#freeze) を呼び出し、被制御シーケンスの先頭へのポインターを返します。

```cpp
char *str();
```

### <a name="return-value"></a>戻り値

被制御シーケンスの先頭へのポインター。

### <a name="remarks"></a>解説

メンバ関数は[rdbuf](#rdbuf) -> [str](../standard-library/strstreambuf-class.md#str)を返します。

### <a name="example"></a>例

を使用するサンプルについては、 [strstream::str](../standard-library/strstreambuf-class.md#str)を参照`str`してください。

## <a name="see-also"></a>関連項目

[Istream](../standard-library/istream-typedefs.md#istream)\
[C++ 標準ライブラリにおけるスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[iostream プログラミング](../standard-library/iostream-programming.md)\
[ioストリームの規約](../standard-library/iostreams-conventions.md)
