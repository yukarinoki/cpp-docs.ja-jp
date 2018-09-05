---
title: '&lt;streambuf&gt; | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- <streambuf>
dev_langs:
- C++
helpviewer_keywords:
- streambuf header
ms.assetid: 4365b25c-5831-488b-b9c2-867bfe961b89
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 25ec172fb38fb3b200086c5f9317ccd8e5e54281
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2018
ms.locfileid: "43691481"
---
# <a name="ltstreambufgt"></a>&lt;streambuf&gt;

テンプレート クラス [basic_streambuf](../standard-library/basic-streambuf-class.md) を定義する iostreams の標準ヘッダー \<streambuf> を含みます。このテンプレート クラスは iostreams クラスの操作の基本になります。 通常、このヘッダーは別の iostream ヘッダーにインクルードされているため、ユーザーが直接インクルードする必要はありません。

## <a name="syntax"></a>構文

```cpp
#include <streambuf>

```

### <a name="typedefs"></a>Typedefs

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
