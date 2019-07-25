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
ms.openlocfilehash: 0ad27bf849e8d4b9188868b9a29bf423b4cafafa
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2019
ms.locfileid: "68458741"
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
|[iostream](../standard-library/istream-typedefs.md#iostream)|Char に`basic_iostream`特化した型。|
|[istream](../standard-library/istream-typedefs.md#istream)|Char に`basic_istream`特化した型。|
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
|[basic_istream](../standard-library/basic-istream-class.md)|このテンプレートクラスは、型`Elem`の要素を含むストリームバッファーからの要素とエンコードされたオブジェクトの抽出を制御するオブジェクトを表します。これは、 [char_type](../standard-library/basic-ios-class.md#char_type)と`Tr`も呼ばれ、その文字特性はクラスによって決定されます。[traits_type](../standard-library/basic-ios-class.md#traits_type)として知られています。|

## <a name="see-also"></a>関連項目

[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[iostream プログラミング](../standard-library/iostream-programming.md)\
[iostreams の規則](../standard-library/iostreams-conventions.md)
