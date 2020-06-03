---
title: strstream クラス
ms.date: 11/04/2016
f1_keywords:
- strstream/std::strstream::freeze
- strstream/std::strstream::pcount
- strstream/std::strstream::rdbuf
- strstream/std::strstream::str
helpviewer_keywords:
- std::strstream [C++], freeze
- std::strstream [C++], pcount
- std::strstream [C++], rdbuf
- std::strstream [C++], str
ms.assetid: 63f3be31-9e36-42b1-9715-a474a5997e2a
ms.openlocfilehash: 047b7e9d7fdece75137980b013d43abf1d5e3ec3
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376615"
---
# <a name="strstream-class"></a>strstream クラス

クラス [strstreambuf](../standard-library/strstreambuf-class.md) のストリーム バッファーを使用して、要素とエンコードされたオブジェクトの挿入と抽出を制御するオブジェクトを表します。

## <a name="syntax"></a>構文

```cpp
class strstream : public iostream
```

## <a name="remarks"></a>解説

このオブジェクトは、クラス `strstreambuf` のオブジェクトを格納します。

> [!NOTE]
> このクラスは非推奨とされます。 代わりに、[stringstream](../standard-library/sstream-typedefs.md#stringstream) または [wstringstream](../standard-library/sstream-typedefs.md#wstringstream) を使用することを検討してください。

### <a name="constructors"></a>コンストラクター

|Constructor|説明|
|-|-|
|[ストストリーム](#strstream)|`strstream` 型のオブジェクトを構築します。|

### <a name="member-functions"></a>メンバー関数

|メンバー関数|説明|
|-|-|
|[凍結](#freeze)|ストリーム バッファーの操作により、ストリーム バッファーを使用不可にします。|
|[pcount](#pcount)|被制御シーケンスに書き込まれる要素の数を返します。|
|[rdbuf](#rdbuf)|ストリームの関連付けられた `strstreambuf` オブジェクトへのポインターを返します。|
|[Str](#str)|[freeze](../standard-library/strstreambuf-class.md#freeze) を呼び出し、被制御シーケンスの先頭へのポインターを返します。|

## <a name="requirements"></a>必要条件

**ヘッダー:** \<strstream>

**名前空間:** std

## <a name="strstreamfreeze"></a><a name="freeze"></a>ストストリーム::フリーズ

ストリーム バッファーの操作により、ストリーム バッファーを使用不可にします。

```cpp
void freeze(bool _Freezeit = true);
```

### <a name="parameters"></a>パラメーター

*_Freezeit*\
ストリームを凍結するかどうかを示す**bool。**

### <a name="remarks"></a>解説

メンバー関数は[rdbuf](#rdbuf) -> [のフリーズ](../standard-library/strstreambuf-class.md#freeze)(_ *Freezeit)* を呼び出します。

### <a name="example"></a>例

を使用する例については、 [strstreambuf::freeze](../standard-library/strstreambuf-class.md#freeze)を参照`freeze`してください。

## <a name="strstreampcount"></a><a name="pcount"></a>ストストリーム::pカウント

被制御シーケンスに書き込まれる要素の数を返します。

```cpp
streamsize pcount() const;
```

### <a name="return-value"></a>戻り値

被制御シーケンスに書き込まれる要素の数。

### <a name="remarks"></a>解説

このメンバー関数は[、rdbuf](#rdbuf) -> [の pcount](../standard-library/strstreambuf-class.md#pcount)を返します。

### <a name="example"></a>例

pcount の使用例は、[strstreambuf::pcount](../standard-library/strstreambuf-class.md#pcount) をご覧ください。

## <a name="strstreamrdbuf"></a><a name="rdbuf"></a>ストストリーム::rdbuf

ストリームの関連付けられた strstreambuf オブジェクトへのポインターを返します。

```cpp
strstreambuf *rdbuf() const
```

### <a name="return-value"></a>戻り値

ストリームの関連付けられた strstreambuf オブジェクトへのポインター。

### <a name="remarks"></a>解説

このメンバー関数は、格納された型`pointer`のストリーム バッファーのアドレスを[strstreambuf](../standard-library/strstreambuf-class.md)に返します。

### <a name="example"></a>例

`rdbuf` の使用例は、[strstreambuf::pcount](../standard-library/strstreambuf-class.md#pcount) をご覧ください。

## <a name="strstreamstr"></a><a name="str"></a>ストストリーム::str

[freeze](../standard-library/strstreambuf-class.md#freeze) を呼び出し、被制御シーケンスの先頭へのポインターを返します。

```cpp
char *str();
```

### <a name="return-value"></a>戻り値

被制御シーケンスの先頭へのポインター。

### <a name="remarks"></a>解説

メンバ関数は[rdbuf](#rdbuf) -> [str](../standard-library/strstreambuf-class.md#str)を返します。

### <a name="example"></a>例

を使用するサンプルについては、 [strstreambuf::str](../standard-library/strstreambuf-class.md#str)を参照`str`してください。

## <a name="strstreamstrstream"></a><a name="strstream"></a>ストストリーム::ストストリーム

`strstream` 型のオブジェクトを構築します。

```cpp
strstream();

strstream(char* ptr,
    streamsize count,
    ios_base::openmode _Mode = ios_base::in | ios_base::out);
```

### <a name="parameters"></a>パラメーター

*カウント*\
バッファーのサイズ。

*_Mode*\
バッファーの入出力モード。 詳細については、[ios_base::openmode](../standard-library/ios-base-class.md#openmode) をご覧ください。

*Ptr*\
バッファーです。

### <a name="remarks"></a>解説

どちらのコンストラクターも、 クラス[strstreambuf](../standard-library/strstreambuf-class.md)の格納されたオブジェクトである`sb` [streambuf](../standard-library/streambuf-typedefs.md#streambuf)( **sb**) を呼び出して基本クラスを初期化します。 最初のコンストラクターも`sb`[strstreambuf](../standard-library/strstreambuf-class.md#strstreambuf)を呼び出して初期化します。 2 番目のコンストラクターは、次のどちらかの方法で基本クラスを初期化します。

- `_Mode`  &  **ios_base::app**== 0 の場合 *、ptr*は要素の配列の`count`最初の要素を指定する`strstreambuf`必要`ptr`があり`count`、`ptr`コンストラクタは ( , ) を呼び出します。

- それ以外の場合 *、ptr*は、最初の要素が*ptr*によって指定される C 文字列を含む count 要素の配列`strstreambuf`の`ptr`最初`count`の`ptr` + `strlen`要素`ptr`を指定する必要があり、コンストラクターは ( , , ) を呼び出します。

## <a name="see-also"></a>関連項目

[Iostream](../standard-library/istream-typedefs.md#iostream)\
[C++ 標準ライブラリにおけるスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[iostream プログラミング](../standard-library/iostream-programming.md)\
[ioストリームの規約](../standard-library/iostreams-conventions.md)
