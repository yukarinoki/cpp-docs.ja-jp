---
title: '&lt;fstream&gt; | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- <fstream>
dev_langs:
- C++
helpviewer_keywords:
- fstream header
ms.assetid: 660de351-0489-41df-b239-40e0cdcab46b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3d2fa3ef6113add6bcf72f85f74b8722033cb8d5
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
ms.locfileid: "33846611"
---
# <a name="ltfstreamgt"></a>&lt;fstream&gt;

外部ファイルに格納されているシーケンスの iostream の操作をサポートする複数のクラスを定義します。

## <a name="syntax"></a>構文

```cpp
#include <fstream>

```

### <a name="typedefs"></a>Typedefs

|型名|説明|
|-|-|
|[filebuf](../standard-library/fstream-typedefs.md#filebuf)|`char` テンプレート パラメーターに特殊化された型 `basic_filebuf`。|
|[fstream](../standard-library/fstream-typedefs.md#fstream)|`char` テンプレート パラメーターに特殊化された型 `basic_fstream`。|
|[ifstream](../standard-library/fstream-typedefs.md#ifstream)|`char` テンプレート パラメーターに特殊化された型 `basic_ifstream`。|
|[ofstream](../standard-library/fstream-typedefs.md#ofstream)|`char` テンプレート パラメーターに特殊化された型 `basic_ofstream`。|
|[wfstream](../standard-library/fstream-typedefs.md#wfstream)|`wchar_t` テンプレート パラメーターに特殊化された型 `basic_fstream`。|
|[wifstream](../standard-library/fstream-typedefs.md#wifstream)|`wchar_t` テンプレート パラメーターに特殊化された型 `basic_ifstream`。|
|[wofstream](../standard-library/fstream-typedefs.md#wofstream)|`wchar_t` テンプレート パラメーターに特殊化された型 `basic_ofstream`。|
|[wfilebuf](../standard-library/fstream-typedefs.md#wfilebuf)|`wchar_t` テンプレート パラメーターに特殊化された型 `basic_filebuf`。|

### <a name="classes"></a>クラス

|クラス|説明|
|-|-|
|[basic_filebuf](../standard-library/basic-filebuf-class.md)|このテンプレート クラスは、**Elem** 型の要素と外部ファイルに格納されている要素のシーケンスとの間でやり取りされる転送を制御するストリーム バッファーを記述します。Elem 型の特性は **Tr** クラスによって決められます。|
|[basic_fstream](../standard-library/basic-fstream-class.md)|このテンプレート クラスは、**Elem** 型の要素を含む [basic_filebuf](../standard-library/basic-filebuf-class.md)\<**Elem**, **Tr**> クラスのストリーム バッファーを使用して要素とエンコードされたオブジェクトを挿入または抽出する際に、その処理を制御するオブジェクトを記述します。Elem 型の特性は **Tr** クラスによって決められます。|
|[basic_ifstream](../standard-library/basic-ifstream-class.md)|このテンプレート クラスは、**Elem** 型の要素を含む [basic_filebuf](../standard-library/basic-filebuf-class.md)\<**Elem**, **Tr**> クラスのストリーム バッファーから要素とエンコードされたオブジェクトを抽出する処理を制御するオブジェクトを記述します。Elem 型の特性は **Tr** クラスによって決められます。|
|[basic_ofstream](../standard-library/basic-ofstream-class.md)|このテンプレート クラスは、**Elem** 型の要素を含む [basic_filebuf](../standard-library/basic-filebuf-class.md)\<**Elem**, **Tr**> クラスのストリーム バッファーに要素とエンコードされたオブジェクトを挿入する処理を制御するオブジェクトを記述します。Elem 型の特性は **Tr** クラスによって決められます。|

## <a name="see-also"></a>関連項目

[ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)<br/>
[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[iostream プログラミング](../standard-library/iostream-programming.md)<br/>
[iostreams の規則](../standard-library/iostreams-conventions.md)<br/>
