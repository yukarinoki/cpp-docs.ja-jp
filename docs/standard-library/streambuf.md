---
title: '&lt;streambuf&gt;'
ms.date: 11/04/2016
f1_keywords:
- <streambuf>
helpviewer_keywords:
- streambuf header
ms.assetid: 4365b25c-5831-488b-b9c2-867bfe961b89
ms.openlocfilehash: 87fb74f62abffdd62b8c0179b13f53d96439d6c6
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2019
ms.locfileid: "68449575"
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
|[streambuf](../standard-library/streambuf-typedefs.md#streambuf)|テンプレートパラメーターと`basic_streambuf`して**char**を使用するの特殊化。|
|[wstreambuf](../standard-library/streambuf-typedefs.md#wstreambuf)|テンプレートパラメーターと`basic_streambuf`して**wchar_t**を使用するの特殊化。|

### <a name="classes"></a>クラス

|クラス|説明|
|-|-|
|[basic_streambuf クラス](basic-streambuf-class.md)|このテンプレート クラスは、ストリームの特定の表現との相互間での要素の伝送を制御する、ストリーム バッファーを派生させるための抽象基底クラスについて説明します。|

## <a name="see-also"></a>関連項目

[ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)\
[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[iostream プログラミング](../standard-library/iostream-programming.md)\
[iostreams の規則](../standard-library/iostreams-conventions.md)
