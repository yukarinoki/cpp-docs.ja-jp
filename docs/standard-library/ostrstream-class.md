---
title: ostrstream クラス | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- strstream/std::ostrstream::freeze
- strstream/std::ostrstream::pcount
- strstream/std::ostrstream::rdbuf
- strstream/std::ostrstream::str
dev_langs:
- C++
helpviewer_keywords:
- std::ostrstream [C++], freeze
- std::ostrstream [C++], pcount
- std::ostrstream [C++], rdbuf
- std::ostrstream [C++], str
ms.assetid: e2e34679-b266-4728-a8e1-8eda5d400e46
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 526ed4340446e78a723af97f43fbed401f574764
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "44106045"
---
# <a name="ostrstream-class"></a>ostrstream クラス

クラス [strstreambuf](../standard-library/strstreambuf-class.md) のストリーム バッファーへの、要素とエンコードされたオブジェクトの挿入を制御するオブジェクトを表します。

## <a name="syntax"></a>構文

```cpp
class ostrstream : public ostream
```

## <a name="remarks"></a>Remarks

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
|[freeze](#freeze)|ストリーム バッファーの操作により、ストリーム バッファーを使用不可にします。|
|[pcount](#pcount)|被制御シーケンスに書き込まれる要素の数を返します。|
|[rdbuf](#rdbuf)|ストリームの関連付けられた `strstreambuf` オブジェクトへのポインターを返します。|
|[str](#str)|[freeze](../standard-library/strstreambuf-class.md#freeze) を呼び出し、被制御シーケンスの先頭へのポインターを返します。|

## <a name="requirements"></a>要件

**ヘッダー:** \<strstream>

**名前空間:** std

## <a name="freeze"></a>  ostrstream::freeze

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

参照してください[strstream::freeze](../standard-library/strstreambuf-class.md#freeze)を使用する例については`freeze`します。

## <a name="ostrstream"></a>  ostrstream::ostrstream

`ostrstream` 型のオブジェクトを構築します。

```cpp
ostrstream();

ostrstream(char* ptr,
    streamsize count,
    ios_base::openmode _Mode = ios_base::out);
```

### <a name="parameters"></a>パラメーター

*ptr*<br/>
バッファー。

*count*<br/>
バッファーのサイズ (バイト単位)。

*モード (_m)*<br/>
バッファーの入出力モード。 詳細については、[ios_base::openmode](../standard-library/ios-base-class.md#openmode) をご覧ください。

### <a name="remarks"></a>Remarks

両方のコンス トラクターを呼び出して基底クラスを初期化する[ostream](../standard-library/ostream-typedefs.md#ostream)(**sb**) ここで、`sb`クラスの格納されているオブジェクトは、 [strstreambuf](../standard-library/strstreambuf-class.md)します。 最初のコンス トラクターによって初期化も`sb`呼び出して`strstreambuf`します。 2 番目のコンストラクターは、次のどちらかの方法で基本クラスを初期化します。

- 場合`_Mode`  &  **ios_base::app**し、0 を = =`ptr`の配列の最初の要素を指定する必要があります`count`要素、およびコンス トラクター呼び出し`strstreambuf`(`ptr`、 `count`, `ptr`).

- それ以外の場合、`ptr`配列の count 要素の C 文字列を含む最初の要素がで指定された最初の要素を指定する必要があります`ptr`、コンス トラクターの呼び出しと`strstreambuf`(`ptr`、 `count`、 `ptr` + `strlen`( `ptr`) ).

## <a name="pcount"></a>  ostrstream::pcount

被制御シーケンスに書き込まれる要素の数を返します。

```cpp
streamsize pcount() const;
```

### <a name="return-value"></a>戻り値

被制御シーケンスに書き込まれる要素の数。

### <a name="remarks"></a>Remarks

このメンバー関数は、[rdbuf](#rdbuf) -> [pcount](../standard-library/strstreambuf-class.md#pcount) を返します。

### <a name="example"></a>例

`pcount` の使用例は、[strstream::pcount](../standard-library/strstreambuf-class.md#pcount) をご覧ください。

## <a name="rdbuf"></a>  ostrstream::rdbuf

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

## <a name="str"></a>  ostrstream::str

[freeze](../standard-library/strstreambuf-class.md#freeze) を呼び出し、被制御シーケンスの先頭へのポインターを返します。

```cpp
char *str();
```

### <a name="return-value"></a>戻り値

被制御シーケンスの先頭へのポインター。

### <a name="remarks"></a>Remarks

このメンバー関数は、[rdbuf](#rdbuf) -> [str](../standard-library/strstreambuf-class.md#str) を返します。

### <a name="example"></a>例

参照してください[strstream::str](../standard-library/strstreambuf-class.md#str)を使用するサンプルの`str`します。

## <a name="see-also"></a>関連項目

[ostream](../standard-library/ostream-typedefs.md#ostream)<br/>
[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[iostream プログラミング](../standard-library/iostream-programming.md)<br/>
[iostreams の規則](../standard-library/iostreams-conventions.md)<br/>
