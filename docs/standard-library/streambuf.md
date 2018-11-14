---
title: '&lt;streambuf&gt;'
ms.date: 11/04/2016
f1_keywords:
- <streambuf>
helpviewer_keywords:
- streambuf header
ms.assetid: 4365b25c-5831-488b-b9c2-867bfe961b89
ms.openlocfilehash: 15bfa86a3c697442b66a5f77aa6ea7a9aba5643c
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/10/2018
ms.locfileid: "51521032"
---
# <a name="ltstreambufgt"></a>&lt;streambuf&gt;

テンプレート クラス [basic_streambuf](../standard-library/basic-streambuf-class.md) を定義する iostreams の標準ヘッダー \<streambuf> を含みます。このテンプレート クラスは iostreams クラスの操作の基本になります。 通常、このヘッダーは別の iostream ヘッダーにインクルードされているため、ユーザーが直接インクルードする必要はありません。

## <a name="syntax"></a>構文

```cpp
#include <streambuf>
```

### <a name="typedefs"></a>Typedef

|型名|説明|
|-|-|
|[streambuf](../standard-library/streambuf-typedefs.md#streambuf)|特殊化`basic_streambuf`を使用して**char**テンプレート パラメーターとして。|
|[wstreambuf](../standard-library/streambuf-typedefs.md#wstreambuf)|特殊化`basic_streambuf`を使用して**wchar_t**テンプレート パラメーターとして。|

### <a name="classes"></a>クラス

|クラス|説明|
|-|-|
|[basic_streambuf クラス](basic-streambuf-class.md)|このテンプレート クラスは、ストリームの特定の表現との相互間での要素の伝送を制御する、ストリーム バッファーを派生させるための抽象基底クラスについて説明します。|

## <a name="see-also"></a>関連項目

[ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)<br/>
[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[iostream プログラミング](../standard-library/iostream-programming.md)<br/>
[iostreams の規則](../standard-library/iostreams-conventions.md)<br/>
