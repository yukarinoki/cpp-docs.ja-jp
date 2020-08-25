---
title: '&lt;strstream&gt;'
ms.date: 11/04/2016
f1_keywords:
- <strstream>
helpviewer_keywords:
- strstream header
ms.assetid: eaa9d0d4-d217-4f28-8a68-9b9ad7b1c0f5
ms.openlocfilehash: 13eea1101abca0f79f0d7c15405ceb3118707b67
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88845654"
---
# <a name="ltstrstreamgt"></a>&lt;strstream&gt;

オブジェクトの割り当てられた配列に格納されているシーケンスに対して iostreams 操作をサポートする複数のクラスを定義 **`char`** します。 このようなシーケンスは、C 文字列と簡単に相互変換できます。

## <a name="requirements"></a>必要条件

**ヘッダー:**\<strstream>

**名前空間:** std

## <a name="remarks"></a>解説

型のオブジェクト `strstream` **`char`** は、C 文字列である * を使用して処理されます。 [\<sstream>](../standard-library/sstream.md) [Basic_string](../standard-library/basic-string-class.md)型のオブジェクトを操作するために使用します。

> [!NOTE]
> \<strstream> のクラスの使用は非推奨とされます。 代わりに、\<sstream> のクラスの使用を検討してください。

## <a name="members"></a>メンバー

### <a name="classes"></a>クラス

|名前|説明|
|-|-|
|[strstreambuf クラス](../standard-library/strstreambuf-class.md)|クラスは、配列オブジェクトに格納されている要素のシーケンスとの間での要素の転送を制御するストリームバッファーを記述し **`char`** ます。|
|[istrstream クラス](../standard-library/istrstream-class.md)|このクラスは、クラス [strstreambuf](../standard-library/strstreambuf-class.md) のストリーム バッファーからの、要素とエンコードされたオブジェクトの抽出を制御するオブジェクトを表します。|
|[ostrstream クラス](../standard-library/ostrstream-class.md)|このクラスは、クラス [strstreambuf](../standard-library/strstreambuf-class.md) のストリーム バッファーへの、要素とエンコードされたオブジェクトの挿入を制御するオブジェクトを表します。|
|[strstream クラス](../standard-library/strstream-class.md)|このクラスは、クラス [strstreambuf](../standard-library/strstreambuf-class.md) のストリーム バッファーを使用して要素とエンコードされたオブジェクトの挿入と抽出を制御するオブジェクトを表します。|

### <a name="functions"></a>Functions

```cpp
void freeze(bool freezefl = true);
char* str();
int pcount();
```

## <a name="see-also"></a>関連項目

[\<strstream>](../standard-library/strstream.md)\
[ヘッダーファイルのリファレンス](../standard-library/cpp-standard-library-header-files.md)\
[C++ 標準ライブラリのスレッドセーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[iostream プログラミング](../standard-library/iostream-programming.md)\
[iostreams の規則](../standard-library/iostreams-conventions.md)
