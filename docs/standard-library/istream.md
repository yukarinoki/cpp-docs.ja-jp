---
title: '&lt;istream&gt;'
ms.date: 11/04/2016
f1_keywords:
- istream/std::<istream>
- <istream>
- std::<istream>
helpviewer_keywords:
- istream header
ms.assetid: efcf24e4-05d1-4719-ab0b-9e7ebe845d89
ms.openlocfilehash: 2e39c0de5b11c9aa0a4c69f0142841469ef798c7
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/10/2018
ms.locfileid: "51521883"
---
# <a name="ltistreamgt"></a>&lt;istream&gt;

iostream の抽出を仲介するテンプレート クラス basic_istream と、挿入と抽出の両方を仲介するテンプレート クラス basic_iostream を定義します。 ヘッダーは、関連するマニピュレーターも定義します。 このヘッダー ファイルは通常、別の iostream ヘッダーに含まれているため、ほとんどの場合、直接含める必要はありません。

## <a name="syntax"></a>構文

```cpp
#include <istream>
```

### <a name="typedefs"></a>Typedef

|型名|説明|
|-|-|
|[iostream](../standard-library/istream-typedefs.md#iostream)|型`basic_iostream`に特殊化された**char**します。|
|[istream](../standard-library/istream-typedefs.md#istream)|型`basic_istream`に特殊化された**char**します。|
|[wiostream](../standard-library/istream-typedefs.md#wiostream)|**wchar** に特殊化された型 `basic_iostream`。|
|[wistream](../standard-library/istream-typedefs.md#wistream)|**wchar** に特殊化された型 `basic_istream`。|

### <a name="manipulators"></a>マニピュレーター

|||
|-|-|
|[ws](../standard-library/istream-functions.md#ws)|ストリーム内の空白をスキップします。|
|[swap](../standard-library/istream-functions.md#istream_swap)|2 つのストリーム オブジェクトを交換します。|

### <a name="operators"></a>演算子

|演算子|説明|
|-|-|
|[operator>>](../standard-library/istream-operators.md#op_gt_gt)|ストリームから文字と文字列を抽出します。|

### <a name="classes"></a>クラス

|クラス|説明|
|-|-|
|[basic_iostream](../standard-library/basic-iostream-class.md)|入力と出力の両方を行うことができるストリーム クラス。|
|[basic_istream](../standard-library/basic-istream-class.md)|テンプレート クラスは、型の要素を含むストリーム バッファーからエンコードされたオブジェクトと要素の抽出を制御するオブジェクトについて説明します`Elem`とも呼ばれる、 [char_type](../standard-library/basic-ios-class.md#char_type)、その文字特性はクラスによって決まります。`Tr`とも呼ばれる、 [traits_type](../standard-library/basic-ios-class.md#traits_type)します。|

## <a name="see-also"></a>関連項目

[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[iostream プログラミング](../standard-library/iostream-programming.md)<br/>
[iostreams の規則](../standard-library/iostreams-conventions.md)<br/>
