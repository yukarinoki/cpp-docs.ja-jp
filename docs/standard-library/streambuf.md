---
description: 詳細については、「streambuf」を参照してください。 &lt;&gt;
title: '&lt;streambuf&gt;'
ms.date: 11/04/2016
f1_keywords:
- <streambuf>
helpviewer_keywords:
- streambuf header
ms.assetid: 4365b25c-5831-488b-b9c2-867bfe961b89
ms.openlocfilehash: 417b31b919c95d8aef741b2988c576ff6454ce4a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97183764"
---
# <a name="ltstreambufgt"></a>&lt;streambuf&gt;

Iostreams の標準ヘッダーをインクルードして \<streambuf> クラステンプレート [basic_streambuf](../standard-library/basic-streambuf-class.md)を定義します。これは iostreams クラスの操作の基本となります。 通常、このヘッダーは別の iostream ヘッダーにインクルードされているため、ユーザーが直接インクルードする必要はありません。

## <a name="syntax"></a>構文

```cpp
#include <streambuf>
```

### <a name="typedefs"></a>Typedefs

|型名|説明|
|-|-|
|[streambuf](../standard-library/streambuf-typedefs.md#streambuf)|`basic_streambuf` **`char`** テンプレートパラメーターとしてを使用するの特殊化。|
|[wstreambuf](../standard-library/streambuf-typedefs.md#wstreambuf)|`basic_streambuf` **`wchar_t`** テンプレートパラメーターとしてを使用するの特殊化。|

### <a name="classes"></a>クラス

|クラス|説明|
|-|-|
|[basic_streambuf クラス](basic-streambuf-class.md)|クラステンプレートは、ストリームの特定の表現との間での要素の伝送を制御する、ストリームバッファーを派生させるための抽象基本クラスを記述します。|

## <a name="see-also"></a>関連項目

[ヘッダーファイルのリファレンス](../standard-library/cpp-standard-library-header-files.md)\
[C++ 標準ライブラリのスレッドセーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[iostream プログラミング](../standard-library/iostream-programming.md)\
[iostreams の規則](../standard-library/iostreams-conventions.md)
