---
title: istrstream クラス | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- strstream/std::istrstream::rdbuf
- strstream/std::istrstream::str
dev_langs:
- C++
helpviewer_keywords:
- istrstream class
ms.assetid: c2d41c75-bd2c-4437-bd77-5939ce1b97af
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d979cab4dc25898b772c434f5a50682573ce4016
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "44099539"
---
# <a name="istrstream-class"></a>istrstream クラス

クラス [strstreambuf](../standard-library/strstreambuf-class.md) のストリーム バッファーからの、要素とエンコードされたオブジェクトの抽出を制御するオブジェクトを表します。

## <a name="syntax"></a>構文

```cpp
class istrstream : public istream
```

## <a name="remarks"></a>Remarks

このオブジェクトは、クラス `strstreambuf` のオブジェクトを格納します。

> [!NOTE]
> このクラスは非推奨とされます。 代わりに、[istringstream](../standard-library/sstream-typedefs.md#istringstream) または [wistringstream](../standard-library/sstream-typedefs.md#wistringstream) を使用することを検討してください。

### <a name="constructors"></a>コンストラクター

|コンストラクター|説明|
|-|-|
|[istrstream](#istrstream)|`istrstream` 型のオブジェクトを構築します。|

### <a name="member-functions"></a>メンバー関数

|メンバー関数|説明|
|-|-|
|[rdbuf](#rdbuf)|ストリームの関連付けられた `strstreambuf` オブジェクトへのポインターを返します。|
|[str](#str)|[freeze](../standard-library/strstreambuf-class.md#freeze) を呼び出し、被制御シーケンスの先頭へのポインターを返します。|

## <a name="requirements"></a>要件

**ヘッダー:** \<strstream>

**名前空間:** std

## <a name="istrstream"></a>  istrstream::istrstream

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

*count*<br/>
バッファーの長さ (*ptr*)。

*ptr*<br/>
バッファーが初期化されているコンテンツ。

### <a name="remarks"></a>Remarks

すべてのコンス トラクターを呼び出して基底クラスを初期化する[istream](../standard-library/istream-typedefs.md#istream)(**sb**) ここで、`sb`クラスの格納されているオブジェクトは、 [strstreambuf](../standard-library/strstreambuf-class.md)します。 最初の 2 つのコンス トラクターの初期化も`sb`呼び出して`strstreambuf`(( **const** `char` \*) `ptr`, 0)。 残りの 2 つのコンストラクターは、代わりに `strstreambuf`( ( **const**`char` *) `ptr`, `count` ) を呼び出します。

## <a name="rdbuf"></a>  istrstream::rdbuf

ストリームの関連付けられた strstreambuf オブジェクトへのポインターを返します。

```cpp
strstreambuf *rdbuf() const
```

### <a name="return-value"></a>戻り値

ストリームの関連付けられた strstreambuf オブジェクトへのポインター。

### <a name="remarks"></a>Remarks

このメンバー関数は、ポインター型の格納されたストリーム バッファーのアドレスを [strstreambuf](../standard-library/strstreambuf-class.md) に返します。

### <a name="example"></a>例

`rdbuf` の使用例は、[strstreambuf::pcount](../standard-library/strstreambuf-class.md#pcount) を参照してください。

## <a name="str"></a>  istrstream::str

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

[istream](../standard-library/istream-typedefs.md#istream)<br/>
[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[iostream プログラミング](../standard-library/iostream-programming.md)<br/>
[iostreams の規則](../standard-library/iostreams-conventions.md)<br/>
