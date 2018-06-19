---
title: strstream クラス | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- strstream/std::strstream::freeze
- strstream/std::strstream::pcount
- strstream/std::strstream::rdbuf
- strstream/std::strstream::str
dev_langs:
- C++
helpviewer_keywords:
- std::strstream [C++], freeze
- std::strstream [C++], pcount
- std::strstream [C++], rdbuf
- std::strstream [C++], str
ms.assetid: 63f3be31-9e36-42b1-9715-a474a5997e2a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 245391a0625d94fee0a4457f87e7b633ba3d03ca
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33859827"
---
# <a name="strstream-class"></a>strstream クラス

クラス [strstreambuf](../standard-library/strstreambuf-class.md) のストリーム バッファーを使用して、要素とエンコードされたオブジェクトの挿入と抽出を制御するオブジェクトを表します。

## <a name="syntax"></a>構文

```cpp
class strstream : public iostream
```

## <a name="remarks"></a>コメント

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

## <a name="requirements"></a>要件

**ヘッダー:** \<strstream>

**名前空間:** std

## <a name="freeze"></a>  strstream::freeze

ストリーム バッファーの操作により、ストリーム バッファーを使用不可にします。

```cpp
void freeze(bool _Freezeit = true);
```

### <a name="parameters"></a>パラメーター

`_Freezeit` A`bool`は固定表示をストリームするかどうかを示すです。

### <a name="remarks"></a>コメント

メンバー関数は [rdbuf](#rdbuf) -> [freeze](../standard-library/strstreambuf-class.md#freeze)(_ *Freezeit*) を呼び出します。

### <a name="example"></a>例

**freeze** の使用例は、[strstreambuf::freeze](../standard-library/strstreambuf-class.md#freeze) をご覧ください。

## <a name="pcount"></a>  strstream::pcount

被制御シーケンスに書き込まれる要素の数を返します。

```cpp
streamsize pcount() const;
```

### <a name="return-value"></a>戻り値

被制御シーケンスに書き込まれる要素の数。

### <a name="remarks"></a>コメント

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

### <a name="remarks"></a>コメント

このメンバー関数は **pointer** 型の格納されたストリーム バッファーのアドレスを [strstreambuf](../standard-library/strstreambuf-class.md) に返します。

### <a name="example"></a>例

`rdbuf` の使用例は、[strstreambuf::pcount](../standard-library/strstreambuf-class.md#pcount) をご覧ください。

## <a name="str"></a>  strstream::str

[freeze](../standard-library/strstreambuf-class.md#freeze) を呼び出し、被制御シーケンスの先頭へのポインターを返します。

```cpp
char *str();
```

### <a name="return-value"></a>戻り値

被制御シーケンスの先頭へのポインター。

### <a name="remarks"></a>コメント

このメンバー関数は、[rdbuf](#rdbuf) -> [str](../standard-library/strstreambuf-class.md#str) を返します。

### <a name="example"></a>例

**str** の使用例は、[strstreambuf::str](../standard-library/strstreambuf-class.md#str) をご覧ください。

## <a name="strstream"></a>  strstream::strstream

`strstream` 型のオブジェクトを構築します。

```cpp
strstream();

strstream(char* ptr,
    streamsize count,
    ios_base::openmode _Mode = ios_base::in | ios_base::out);
```

### <a name="parameters"></a>パラメーター

`count` バッファーのサイズ。

`_Mode` バッファーの入力と出力モードです。 詳細については、[ios_base::openmode](../standard-library/ios-base-class.md#openmode) をご覧ください。

`ptr` バッファーです。

### <a name="remarks"></a>コメント

両方のコンストラクターは、[streambuf](../standard-library/streambuf-typedefs.md#streambuf)( **sb**) を呼び出すことにより基本クラスを初期化します。ここで、**sb** は [strstreambuf](../standard-library/strstreambuf-class.md) 型の格納されているオブジェクトです。 最初のコンストラクターはまた、[strstreambuf](../standard-library/strstreambuf-class.md#strstreambuf) を呼び出して **sb** を初期化します。 2 番目のコンストラクターは、次のどちらかの方法で基本クラスを初期化します。

- `_Mode` & **ios_base::app**== 0 の場合、`ptr` は `count` 要素の配列の最初の要素を指定する必要があり、コンストラクターは `strstreambuf`(`ptr`, `count`, `ptr`) を呼び出します。

- それ以外の場合、`ptr` は count 要素の配列の最初の要素を指定する必要があります。この count 要素は C 文字列を含み、最初の要素が `ptr` によって指定されるものです。そしてコンストラクターは `strstreambuf`(`ptr`, `count`, `ptr` + `strlen`(`ptr`)) を呼び出します。

## <a name="see-also"></a>関連項目

[iostream](../standard-library/istream-typedefs.md#iostream)<br/>
[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[iostream プログラミング](../standard-library/iostream-programming.md)<br/>
[iostreams の規則](../standard-library/iostreams-conventions.md)<br/>
