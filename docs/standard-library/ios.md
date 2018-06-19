---
title: '&lt;ios&gt; | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- <ios>
- ios/std::<ios>
dev_langs:
- C++
helpviewer_keywords:
- ios header
ms.assetid: d3d4c161-2f37-4f04-93cc-0a2a89984a9c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5e7ae83cd92ac8441d842e704446d519f57d4f65
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
ms.locfileid: "33847729"
---
# <a name="ltiosgt"></a>&lt;ios&gt;

iostream 操作の基礎となる型と関数を定義します。 このヘッダーは通常、別の iostream ヘッダーによってインクルードされており、ユーザーが直接インクルードすることはほとんどありません。

## <a name="syntax"></a>構文

```cpp
#include <ios>

```

## <a name="remarks"></a>コメント

マニピュレーターとは、多種類の関数のグループです。 \<ios> 内で宣言されたマニピュレーターは、[ios_base](../standard-library/ios-base-class.md) クラスの引数オブジェクトに格納された値を変更します。 その他のマニピュレーターは、[basic_istream](../standard-library/basic-istream-class.md) と [basic_ostream](../standard-library/basic-ostream-class.md) のいずれかのテンプレート クラスの特殊化など、ios_base クラスから派生した型のオブジェクトによって制御されるストリームに対して操作を実行します。 たとえば、[noskipws](../standard-library/ios-functions.md#noskipws)(**str**) は、ios_base クラスから派生する型の 1 つであり、**str** オブジェクトの書式フラグ `ios_base::skipws` をオフにします。

マニピュレーターは、出力ストリームに挿入したり、入力ストリームから抽出したりすることでも呼び出すことができます。これは、`ios_base` から派生したクラスに特殊な挿入演算子と抽出演算子が指定されるためです。 例えば:

```cpp
istr>> noskipws;
```

[noskipws](../standard-library/ios-functions.md#noskipws)(**istr**) を呼び出します。

### <a name="typedefs"></a>Typedefs

|型名|説明|
|-|-|
|[ios](../standard-library/ios-typedefs.md#ios)|従来の iostream ライブラリの ios クラスをサポートします。|
|[streamoff](../standard-library/ios-typedefs.md#streamoff)|内部操作をサポートします。|
|[streampos](../standard-library/ios-typedefs.md#streampos)|バッファー ポインターまたはファイル ポインターの現在の位置を保持します。|
|[streamsize](../standard-library/ios-typedefs.md#streamsize)|ストリームのサイズを指定します。|
|[wios](../standard-library/ios-typedefs.md#wios)|従来の iostream ライブラリの wios クラスをサポートします。|
|[wstreampos](../standard-library/ios-typedefs.md#wstreampos)|バッファー ポインターまたはファイル ポインターの現在の位置を保持します。|

### <a name="manipulators"></a>マニピュレーター

|||
|-|-|
|[boolalpha](../standard-library/ios-functions.md#boolalpha)|[bool](../cpp/bool-cpp.md) 型の変数をストリームで **true** または **false** として表示するように指定します。|
|[dec](../standard-library/ios-functions.md#dec)|整数変数を 10 進表記で表示するように指定します。|
|[defaultfloat](../standard-library/ios-functions.md#ios_defaultfloat)|浮動小数値に既定の表示形式を使用するように、`ios_base` オブジェクトのフラグを構成します。|
|[fixed](../standard-library/ios-functions.md#fixed)|浮動小数点数を固定 10 進表記で表示するように指定します。|
|[hex](../standard-library/ios-functions.md#hex)|整数変数を 16 進表記で表示するように指定します。|
|[internal](../standard-library/ios-functions.md#internal)|数値の符号を左揃え、数値を右揃えにします。|
|[left](../standard-library/ios-functions.md#left)|出力幅に満たないテキストをストリーム フラッシュで左揃えに表示します。|
|[noboolalpha](../standard-library/ios-functions.md#noboolalpha)|[bool](../cpp/bool-cpp.md) 型の変数をストリームで 1 または 0 として表示するように指定します。|
|[noshowbase](../standard-library/ios-functions.md#noshowbase)|指定している数値表記の基底の設定をオフにします。|
|[noshowpoint](../standard-library/ios-functions.md#noshowpoint)|小数部分が 0 の浮動小数点数の整数部分のみを表示します。|
|[noshowpos](../standard-library/ios-functions.md#noshowpos)|正の数値に明示的に符号を付けないようにします。|
|[noskipws](../standard-library/ios-functions.md#noskipws)|入力ストリームで空白を読み取るようにします。|
|[nounitbuf](../standard-library/ios-functions.md#nounitbuf)|出力をバッファーし、バッファーが一杯になると、出力を処理します。|
|[nouppercase](../standard-library/ios-functions.md#nouppercase)|16 進数と指数表記の指数を小文字で表示します。|
|[oct](../standard-library/ios-functions.md#oct)|整数変数を 8 進表記で表示するように指定します。|
|[right](../standard-library/ios-functions.md#right)|出力幅に満たないテキストをストリーム フラッシュで右揃えに表示します。|
|[scientific](../standard-library/ios-functions.md#scientific)|浮動小数点数値を指数表記を使用して表示します。|
|[showbase](../standard-library/ios-functions.md#showbase)|数値表記の基底を指定します。|
|[showpoint](../standard-library/ios-functions.md#showpoint)|小数部分が 0 のときも浮動小数点数の整数部分と小数点の右側にある数字を表示します。|
|[showpos](../standard-library/ios-functions.md#showpos)|正の数値に明示的に符号を付けます。|
|[skipws](../standard-library/ios-functions.md#skipws)|入力ストリームで空白を読み飛ばします。|
|[unitbuf](../standard-library/ios-functions.md#unitbuf)|バッファーが空ではないときに、出力を処理します。|
|[uppercase](../standard-library/ios-functions.md#uppercase)|16 進数と指数表記の指数を大文字で表示します。|

### <a name="classes"></a>クラス

|クラス|説明|
|-|-|
|[basic_ios](../standard-library/basic-ios-class.md)|このテンプレート クラスは、テンプレート パラメーターに依存する、入力ストリーム([basic_istream](../standard-library/basic-istream-class.md) テンプレート クラス) と出力ストリーム ([basic_ostream](../standard-library/basic-ostream-class.md) テンプレート クラス) の両方に共通のストレージとメンバー関数を表します。|
|[fpos](../standard-library/fpos-class.md)|このテンプレート クラスは、システム内の任意のファイル位置インジケーターを復元するために必要なすべての情報を格納できるオブジェクトを表します。|
|[ios_base](../standard-library/ios-base-class.md)|このクラスは、テンプレート パラメーターに依存しない、入力ストリームと出力ストリームの両方に共通のストレージとメンバー関数を表します。|

## <a name="see-also"></a>関連項目

[ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)<br/>
[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[iostream プログラミング](../standard-library/iostream-programming.md)<br/>
[iostreams の規則](../standard-library/iostreams-conventions.md)<br/>
