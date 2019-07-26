---
title: '&lt;fstream&gt;'
ms.date: 11/04/2016
f1_keywords:
- <fstream>
helpviewer_keywords:
- fstream header
ms.assetid: 660de351-0489-41df-b239-40e0cdcab46b
ms.openlocfilehash: ba6a4152b8d37f5b0186f9d05c6ba850e8c2e54c
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2019
ms.locfileid: "68454020"
---
# <a name="ltfstreamgt"></a>&lt;fstream&gt;

外部ファイルに格納されているシーケンスの iostream の操作をサポートする複数のクラスを定義します。

## <a name="syntax"></a>構文

```cpp
#include <fstream>
```

### <a name="typedefs"></a>Typedef

|型名|説明|
|-|-|
|[filebuf](../standard-library/fstream-typedefs.md#filebuf)|Char テンプレート`basic_filebuf`パラメーターに特殊化された型。|
|[fstream](../standard-library/fstream-typedefs.md#fstream)|Char テンプレート`basic_fstream`パラメーターに特殊化された型。|
|[ifstream](../standard-library/fstream-typedefs.md#ifstream)|Char テンプレート`basic_ifstream`パラメーターに特殊化された型。|
|[ofstream](../standard-library/fstream-typedefs.md#ofstream)|Char テンプレート`basic_ofstream`パラメーターに特殊化された型。|
|[wfstream](../standard-library/fstream-typedefs.md#wfstream)|Wchar_t テンプレート`basic_fstream`パラメーターに特化した型。|
|[wifstream](../standard-library/fstream-typedefs.md#wifstream)|Wchar_t テンプレート`basic_ifstream`パラメーターに特化した型。|
|[wofstream](../standard-library/fstream-typedefs.md#wofstream)|Wchar_t テンプレート`basic_ofstream`パラメーターに特化した型。|
|[wfilebuf](../standard-library/fstream-typedefs.md#wfilebuf)|Wchar_t テンプレート`basic_filebuf`パラメーターに特化した型。|

### <a name="classes"></a>クラス

|クラス|説明|
|-|-|
|[basic_filebuf](../standard-library/basic-filebuf-class.md)|このテンプレート クラスは、文字の特徴がクラス `Tr` によって決まる型 `Elem` の要素と、外部ファイルに格納されている要素のシーケンスとの間でやり取りされる転送を制御するストリーム バッファーを記述します。|
|[basic_fstream](../standard-library/basic-fstream-class.md)|このテンプレートクラスは、要素とエンコードされたオブジェクトの挿入と抽出を制御するオブジェクトを記述します。 これは、型`Elem`の要素を使用して、 [basic_filebuf](../standard-library/basic-filebuf-class.md)\<**Elem**, Tr > クラスのストリームバッファーを使用します。文字の特徴はクラス`Tr`によって決まります。|
|[basic_ifstream](../standard-library/basic-ifstream-class.md)|このテンプレートクラスは、文字の特徴を持つ`Elem`型の要素を使用して、クラス[basic_filebuf](../standard-library/basic-filebuf-class.md)\<**Elem**, **Tr**> のストリームバッファーからの要素とエンコードされたオブジェクトの抽出を制御するオブジェクトを表します。は、クラス`Tr`によって決定されます。|
|[basic_ofstream](../standard-library/basic-ofstream-class.md)|このテンプレートクラスは、要素とエンコードされたオブジェクトの挿入を制御するオブジェクトを記述します。 これは、文字の特徴を`Elem`持つ型の要素を使用して、 [basic_filebuf](../standard-library/basic-filebuf-class.md)\<**Elem**, Tr > クラスのストリームバッファーへの挿入を制御します。は、クラス`Tr`によって決定されます。|

## <a name="see-also"></a>関連項目

[ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)\
[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[iostream プログラミング](../standard-library/iostream-programming.md)\
[iostreams の規則](../standard-library/iostreams-conventions.md)
