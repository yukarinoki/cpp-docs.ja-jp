---
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
ms.openlocfilehash: b52ba70607a5214a6aa28f04cdded0b19a56b2f6
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373541"
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

|Constructor|説明|
|-|-|
|[ostrstream](#ostrstream)|`ostrstream` 型のオブジェクトを構築します。|

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

## <a name="ostrstreamfreeze"></a><a name="freeze"></a>オストストリーム::フリーズ

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

を使用する例については、 [strstream::freeze](../standard-library/strstreambuf-class.md#freeze)を参照`freeze`してください。

## <a name="ostrstreamostrstream"></a><a name="ostrstream"></a>オストストリーム::オストストリーム

`ostrstream` 型のオブジェクトを構築します。

```cpp
ostrstream();

ostrstream(char* ptr,
    streamsize count,
    ios_base::openmode _Mode = ios_base::out);
```

### <a name="parameters"></a>パラメーター

*Ptr*\
バッファーです。

*カウント*\
バッファーのサイズ (バイト単位)。

*_Mode*\
バッファーの入出力モード。 詳細については、[ios_base::openmode](../standard-library/ios-base-class.md#openmode) をご覧ください。

### <a name="remarks"></a>解説

両方のコンストラクターは、 [ostream](../standard-library/ostream-typedefs.md#ostream)(**sb**)`sb`を呼び出して基本クラス[を](../standard-library/strstreambuf-class.md)初期化します。 最初のコンストラクターも、`sb`を呼`strstreambuf`び出して初期化します。 2 番目のコンストラクターは、次のどちらかの方法で基本クラスを初期化します。

- `_Mode`  &  **ios_base::app**== 0`ptr`の場合、要素の配列の最初の`count`要素を指定し、コンストラクタ`strstreambuf`が`ptr`呼`count`び`ptr`出す ( , ) 。

- それ以外`ptr`の`ptr`場合は、最初の要素が によって指定される C 文字列を含む count 要素の配列の最初の`strstreambuf`要素`ptr`を`count`指定`ptr` + `strlen`し`ptr`、コンストラクターが呼び出す ( , , ( ) 。

## <a name="ostrstreampcount"></a><a name="pcount"></a>オストストリーム::pカウント

被制御シーケンスに書き込まれる要素の数を返します。

```cpp
streamsize pcount() const;
```

### <a name="return-value"></a>戻り値

被制御シーケンスに書き込まれる要素の数。

### <a name="remarks"></a>解説

このメンバー関数は[、rdbuf](#rdbuf) -> [の pcount](../standard-library/strstreambuf-class.md#pcount)を返します。

### <a name="example"></a>例

`pcount` の使用例は、[strstream::pcount](../standard-library/strstreambuf-class.md#pcount) をご覧ください。

## <a name="ostrstreamrdbuf"></a><a name="rdbuf"></a>オストストリーム::rdbuf

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

## <a name="ostrstreamstr"></a><a name="str"></a>オストストリーム::str

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

[オストリーム](../standard-library/ostream-typedefs.md#ostream)\
[C++ 標準ライブラリにおけるスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[iostream プログラミング](../standard-library/iostream-programming.md)\
[ioストリームの規約](../standard-library/iostreams-conventions.md)
