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
ms.openlocfilehash: 9494f7ee2508df1971d56c94b929a7212bedb254
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62412294"
---
# <a name="strstream-class"></a>strstream クラス

クラス [strstreambuf](../standard-library/strstreambuf-class.md) のストリーム バッファーを使用して、要素とエンコードされたオブジェクトの挿入と抽出を制御するオブジェクトを表します。

## <a name="syntax"></a>構文

```cpp
class strstream : public iostream
```

## <a name="remarks"></a>Remarks

このオブジェクトは、クラス `strstreambuf` のオブジェクトを格納します。

> [!NOTE]
> このクラスは非推奨とされます。 代わりに、[stringstream](../standard-library/sstream-typedefs.md#stringstream) または [wstringstream](../standard-library/sstream-typedefs.md#wstringstream) を使用することを検討してください。

### <a name="constructors"></a>コンストラクター

|コンストラクター|説明|
|-|-|
|[strstream](#strstream)|`strstream` 型のオブジェクトを構築します。|

### <a name="member-functions"></a>メンバー関数

|メンバー関数|説明|
|-|-|
|[freeze](#freeze)|ストリーム バッファーの操作により、ストリーム バッファーを使用不可にします。|
|[pcount](#pcount)|被制御シーケンスに書き込まれる要素の数を返します。|
|[rdbuf](#rdbuf)|ストリームの関連付けられた `strstreambuf` オブジェクトへのポインターを返します。|
|[str](#str)|[freeze](../standard-library/strstreambuf-class.md#freeze) を呼び出し、被制御シーケンスの先頭へのポインターを返します。|

## <a name="requirements"></a>必要条件

**ヘッダー:** \<strstream>

**名前空間:** std

## <a name="freeze"></a>  strstream::freeze

ストリーム バッファーの操作により、ストリーム バッファーを使用不可にします。

```cpp
void freeze(bool _Freezeit = true);
```

### <a name="parameters"></a>パラメーター

*_Freezeit*<br/>
A **bool**ストリームを停止するかどうかを示します。

### <a name="remarks"></a>Remarks

メンバー関数は [rdbuf](#rdbuf) -> [freeze](../standard-library/strstreambuf-class.md#freeze)(_ *Freezeit*) を呼び出します。

### <a name="example"></a>例

参照してください[strstreambuf::freeze](../standard-library/strstreambuf-class.md#freeze)を使用する例については`freeze`します。

## <a name="pcount"></a>  strstream::pcount

被制御シーケンスに書き込まれる要素の数を返します。

```cpp
streamsize pcount() const;
```

### <a name="return-value"></a>戻り値

被制御シーケンスに書き込まれる要素の数。

### <a name="remarks"></a>Remarks

このメンバー関数は、[rdbuf](#rdbuf) -> [pcount](../standard-library/strstreambuf-class.md#pcount) を返します。

### <a name="example"></a>例

pcount の使用例は、[strstreambuf::pcount](../standard-library/strstreambuf-class.md#pcount) をご覧ください。

## <a name="rdbuf"></a>  strstream::rdbuf

ストリームの関連付けられた strstreambuf オブジェクトへのポインターを返します。

```cpp
strstreambuf *rdbuf() const
```

### <a name="return-value"></a>戻り値

ストリームの関連付けられた strstreambuf オブジェクトへのポインター。

### <a name="remarks"></a>Remarks

メンバー関数は、型の格納されたストリーム バッファーのアドレスを返します`pointer`に[strstreambuf](../standard-library/strstreambuf-class.md)します。

### <a name="example"></a>例

`rdbuf` の使用例は、[strstreambuf::pcount](../standard-library/strstreambuf-class.md#pcount) をご覧ください。

## <a name="str"></a>  strstream::str

[freeze](../standard-library/strstreambuf-class.md#freeze) を呼び出し、被制御シーケンスの先頭へのポインターを返します。

```cpp
char *str();
```

### <a name="return-value"></a>戻り値

被制御シーケンスの先頭へのポインター。

### <a name="remarks"></a>Remarks

このメンバー関数は、[rdbuf](#rdbuf) -> [str](../standard-library/strstreambuf-class.md#str) を返します。

### <a name="example"></a>例

参照してください[strstreambuf::str](../standard-library/strstreambuf-class.md#str)を使用するサンプルの`str`します。

## <a name="strstream"></a>  strstream::strstream

`strstream` 型のオブジェクトを構築します。

```cpp
strstream();

strstream(char* ptr,
    streamsize count,
    ios_base::openmode _Mode = ios_base::in | ios_base::out);
```

### <a name="parameters"></a>パラメーター

*count*<br/>
バッファーのサイズ。

*_Mode*<br/>
バッファーの入出力モード。 詳細については、[ios_base::openmode](../standard-library/ios-base-class.md#openmode) をご覧ください。

*ptr*<br/>
バッファー。

### <a name="remarks"></a>Remarks

両方のコンス トラクターを呼び出して基底クラスを初期化する[streambuf](../standard-library/streambuf-typedefs.md#streambuf)( **sb**) ここで、`sb`クラスの格納されているオブジェクトは、 [strstreambuf](../standard-library/strstreambuf-class.md)します。 最初のコンス トラクターによって初期化も`sb`呼び出して[strstreambuf](../standard-library/strstreambuf-class.md#strstreambuf)します。 2 番目のコンストラクターは、次のどちらかの方法で基本クラスを初期化します。

- 場合`_Mode`  &  **ios_base::app**し、0 を = = *ptr*の配列の最初の要素を指定する必要があります`count`要素、およびコンス トラクター呼び出し`strstreambuf`( `ptr`, `count`, `ptr`).

- それ以外の場合、 *ptr*配列の count 要素の C 文字列を含む最初の要素がで指定された最初の要素を指定する必要があります*ptr*、コンス トラクターの呼び出しと`strstreambuf`( `ptr`, `count`, `ptr` + `strlen`( `ptr`) ).

## <a name="see-also"></a>関連項目

[iostream](../standard-library/istream-typedefs.md#iostream)<br/>
[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[iostream プログラミング](../standard-library/iostream-programming.md)<br/>
[iostreams の規則](../standard-library/iostreams-conventions.md)<br/>
