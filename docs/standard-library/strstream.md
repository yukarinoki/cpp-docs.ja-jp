---
title: '&lt;strstream&gt;'
ms.date: 11/04/2016
f1_keywords:
- <strstream>
helpviewer_keywords:
- strstream header
ms.assetid: eaa9d0d4-d217-4f28-8a68-9b9ad7b1c0f5
ms.openlocfilehash: 212223f98db09097e596fc6fe2ddd31bbe16e6b7
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/16/2019
ms.locfileid: "68245372"
---
# <a name="ltstrstreamgt"></a>&lt;strstream&gt;

割り当てられた配列に格納されているシーケンスの iostreams 操作をサポートするクラスがいくつか定義**char**オブジェクト。 このようなシーケンスは、C 文字列と簡単に相互変換できます。

## <a name="requirements"></a>必要条件

**ヘッダー:** \<strstream>

**名前空間:** std

## <a name="remarks"></a>Remarks

型 `strstream` のオブジェクトは C 文字列の `char` * を使用します。 [\<sstream](../standard-library/sstream.md) は、型 [basic_string](../standard-library/basic-string-class.md) のオブジェクトを操作するために使用します。

> [!NOTE]
> クラスは、 \<strstream > は非推奨とされます。 クラスの使用を検討\<sstream > 代わりにします。

## <a name="members"></a>メンバー

### <a name="classes"></a>クラス

|||
|-|-|
|[strstreambuf クラス](../standard-library/strstreambuf-class.md)|クラスが要素に格納されている要素のシーケンスとの間の転送を制御するストリーム バッファーについて説明します、 **char**配列オブジェクト。|
|[istrstream クラス](../standard-library/istrstream-class.md)|このクラスは、クラス [strstreambuf](../standard-library/strstreambuf-class.md) のストリーム バッファーからの、要素とエンコードされたオブジェクトの抽出を制御するオブジェクトを表します。|
|[ostrstream クラス](../standard-library/ostrstream-class.md)|このクラスは、クラス [strstreambuf](../standard-library/strstreambuf-class.md) のストリーム バッファーへの、要素とエンコードされたオブジェクトの挿入を制御するオブジェクトを表します。|
|[strstream クラス](../standard-library/strstream-class.md)|このクラスは、クラス [strstreambuf](../standard-library/strstreambuf-class.md) のストリーム バッファーを使用して要素とエンコードされたオブジェクトの挿入と抽出を制御するオブジェクトを表します。|

### <a name="functions"></a>関数

```cpp
void freeze(bool freezefl = true);
char* str();
int pcount();
```

## <a name="see-also"></a>関連項目

[\<sstream>](../standard-library/strstream.md)<br/>
[ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)<br/>
[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[iostream プログラミング](../standard-library/iostream-programming.md)<br/>
[iostreams の規則](../standard-library/iostreams-conventions.md)<br/>
