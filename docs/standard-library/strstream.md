---
title: '&lt;strstream&gt;'
ms.date: 11/04/2016
f1_keywords:
- <strstream>
helpviewer_keywords:
- strstream header
ms.assetid: eaa9d0d4-d217-4f28-8a68-9b9ad7b1c0f5
ms.openlocfilehash: 72b96c300aba1729823462ce6671e2f9a5285761
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/10/2018
ms.locfileid: "51523716"
---
# <a name="ltstrstreamgt"></a>&lt;strstream&gt;

割り当てられた配列に格納されているシーケンスの iostreams 操作をサポートするクラスがいくつか定義**char**オブジェクト。 このようなシーケンスは、C 文字列と簡単に相互変換できます。

## <a name="syntax"></a>構文

```cpp
#include <strstream>
```

## <a name="remarks"></a>Remarks

型 `strstream` のオブジェクトは C 文字列の `char` * を使用します。 [\<sstream](../standard-library/sstream.md) は、型 [basic_string](../standard-library/basic-string-class.md) のオブジェクトを操作するために使用します。

> [!NOTE]
> クラスは、 \<strstream > は非推奨とされます。 クラスの使用を検討\<sstream > 代わりにします。

### <a name="classes"></a>クラス

|クラス|説明|
|-|-|
|[strstreambuf クラス](../standard-library/strstreambuf-class.md)|クラスが要素に格納されている要素のシーケンスとの間の転送を制御するストリーム バッファーについて説明します、 **char**配列オブジェクト。|
|[istrstream クラス](../standard-library/istrstream-class.md)|このクラスは、クラス [strstreambuf](../standard-library/strstreambuf-class.md) のストリーム バッファーからの、要素とエンコードされたオブジェクトの抽出を制御するオブジェクトを表します。|
|[ostrstream クラス](../standard-library/ostrstream-class.md)|このクラスは、クラス [strstreambuf](../standard-library/strstreambuf-class.md) のストリーム バッファーへの、要素とエンコードされたオブジェクトの挿入を制御するオブジェクトを表します。|
|[strstream クラス](../standard-library/strstream-class.md)|このクラスは、クラス [strstreambuf](../standard-library/strstreambuf-class.md) のストリーム バッファーを使用して要素とエンコードされたオブジェクトの挿入と抽出を制御するオブジェクトを表します。|

## <a name="see-also"></a>関連項目

[\<sstream>](../standard-library/strstream.md)<br/>
[ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)<br/>
[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[iostream プログラミング](../standard-library/iostream-programming.md)<br/>
[iostreams の規則](../standard-library/iostreams-conventions.md)<br/>
